# Manual de Usuario: Ejecuciones Masivas

| Campo       | Valor                                          |
|-------------|------------------------------------------------|
| **Módulo**  | Mantenimiento > Tareas > Ejecuciones Masivas   |
| **Versión** | 1.2                                            |
| **Fecha**   | Abril 2026                                     |
| **Para**    | Administradores de dominio del CGE SERGAS      |

---

## 1. Qué hace este módulo

Permite enviar **comandos arbitrarios** vía SSH a un conjunto **dinámico** de equipos de planta (Cisco / Teldat / Fortinet / Juniper) y, opcionalmente, **extraer valores concretos** de la salida (potencia óptica, SIM Card ID, versión IOS, etc.) que quedan disponibles en una tabla exportable a CSV / Excel.

Casos de uso típicos:

- Cambiar el usuario/contraseña local en todos los routers de un área sanitaria.
- Añadir una ACE a una ACL estándar en todos los Teldat M2 de la planta.
- Recolectar la potencia óptica del SFP+ de los Cisco 5G.
- Recolectar el SIM Card ID de los Teldat 5G por provincia.

Sustituye la antigua "Tarea Gentest" en SecureCRT (VBS), pero **full-web** y **escalable**: filtros sobre la BDU, sin subir ficheros por SSH al servidor.

---

## 2. Acceso

Esta herramienta es muy potente y un comando inocuo mal escrito puede tirar la planta. Por eso el acceso está restringido a **miembros del grupo AD "Admins. del dominio"**.

Si no perteneces a ese grupo, al pulsar la entrada del menú verás:

> ⛔ Esta herramienta es muy potente y está restringida a administradores del dominio SERGASCGE. Si necesitas acceso, contacta con el equipo de administración.

Si crees que deberías tenerlo, contacta con el equipo de administración del CGE SERGAS.

---

## 3. Flujo en 4 pasos

> **Mantenimiento → Tareas → 🚀 Ejecuciones Masivas**

### Paso 1 — Seleccionar equipos

Bloque *① Selección de equipos*. Hay **dos modos** (excluyentes):

#### A) Por filtros (lo habitual)

Tres grupos de filtros:

| Grupo | Filtros |
|---|---|
| **Equipo** | Marca, Modelo, Tipo equipo, VLANs activas (10/12/37/38/39/40/60) |
| **Centro** | Búsqueda libre por nombre/IdCliente, Área Sanitaria, Provincia, FlexWAN (5G), Crítica |
| **Línea**  | Tipo línea (datos/voz), Función, Tipo acceso |

Cada filtro multi-valor es un desplegable con checkboxes (mantén pulsado para elegir varios).

#### B) Por lista de nemónicos

Pega los nemónicos uno por línea en el textarea **"O por lista de nemónicos"**. Si rellenas esto, los filtros de arriba **se ignoran** y se buscan exactamente esos nemónicos (acepta `NemonicoCliente` o `NemonicoTelefonica`). Líneas vacías y `#comentarios` se ignoran.

Si alguno no se encuentra (no existe, dado de baja, centro cerrado, no gestionable), aparecerá listado en un panel "⚠️ N nemónicos no encontrados" sobre la tabla de resultados.

#### Búsqueda y resultados

Al pulsar **🔍 Buscar equipos** aparece la tabla *② Equipos seleccionados* con el detalle (Centro, Nemónico, Marca/Modelo, IPs, Área, Provincia).

> Filtros forzados (siempre activos en ambos modos): equipo gestionable, no dado de baja, centro abierto y línea activa.

### Paso 2 — Escribir los comandos

Bloque *③ Comandos a ejecutar*. **Cuatro cajas** (2x2), una por familia:

- **Cisco** — comandos IOS/IOS-XE. Botón **"Insertar Enter"** que añade `(enter)` (responde a `[confirm]`).
- **Teldat** — comandos del CLI Teldat. Dos botones:
  - **"Insertar Ctrl+P"** → añade `(ctrlp)` (vuelve al menú raíz `*`).
  - **"Insertar Enter"** → añade `(enter)` (responde a `(Yes/No)` con un Enter).
- **Fortinet** — comandos del CLI FortiGate. **Solo funciona en modo Pasarela** (los Fortinet no son accesibles por LAN2LAN). Si lanzas en LAN2LAN con comandos Fortinet, los equipos Fortinet saldrán en el log con `STATUS=PASARELA_REQUIRED` y se saltarán.
- **Juniper** — comandos Junos. Funciona en LAN2LAN o Pasarela.

Solo es obligatorio rellenar **una** caja: las familias que no tengan comandos se saltan automáticamente.

Convenciones:

- Líneas vacías o que empiezan por `#` se ignoran (sirven para comentar).
- **No hace falta** escribir el cierre (`exit`, `logout`, etc.) — el sistema lo añade automáticamente al final de la sesión.
- En Cisco se ejecuta `terminal length 0` automáticamente al inicio para evitar paginación.

#### Manejo de prompts interactivos

Cuando un comando en Cisco dispara `[confirm]` (ej: `no username admin` cuando tiene config asociada), o un comando Teldat dispara `(Yes/No)`, el SEM **no se queda colgado**: la captura de ese comando termina ahí y el siguiente comando del fichero responde a la pregunta. Ejemplos:

```
# Cisco — borrar usuario que pide [confirm]:
no username admin
(enter)

# Teldat — algún comando que pregunta (Yes/No):
algun_comando
Yes
```

### Paso 3 — Definir extracciones (opcional)

Bloque *④ Extracciones*. Solo si quieres **sacar un valor concreto** de la salida de un comando y que aparezca como **columna** en la tabla del Monitor y la exportación CSV/Excel.

Cada fila tiene 4 campos:

| Campo | Significado | Ejemplo |
|---|---|---|
| Comando origen | El comando exacto cuya salida se examina | `show hw-module subslot 0/0 transceiver 13 status` |
| Buscar línea con | Subcadena que debe contener la línea (filtro) | `Rx optical power` |
| Regex (opcional) | Expresión regular para sacar el valor numérico | `-?\d+\.\d+` |
| Etiqueta (columna) | Nombre de la columna en la tabla y CSV/Excel | `Rx_dBm` |

**Cómo encajan los 4 campos:**

1. El sistema busca el bloque de salida del **Comando origen** (debe coincidir letra a letra con un comando que escribiste en la caja Cisco/Teldat).
2. Filtra la **primera línea** que contenga la cadena de **Buscar línea con** (subcadena literal, no regex).
3. Aplica la **Regex** sobre esa línea y devuelve el primer valor que matchea.
4. Lo guarda en una columna llamada **Etiqueta**.

Si dejas **Regex** vacía, devuelve la línea filtrada limpia (sin saltos ni dobles espacios). Si dejas **Buscar línea con** vacío, aplica la regex sobre toda la salida del comando.

Pulsa **+ Añadir extracción** para más filas (puedes definir las que quieras, una por columna). La **✕** quita la fila.

> 📖 Si no controlas regex, mira la **sección 7** abajo: explicación corta + recetas listas para copiar.

### Paso 4 — Lanzar

Bloque *⑤ Lanzamiento*. Solo aparece tras buscar equipos.

| Campo | Significado |
|---|---|
| **Modo** | **LAN2LAN** (IP cliente, sin TOTP) o **Pasarela** (IP Telefónica + TOTP). |
| **Usuario EDOMUS/SERGAS** | Tu usuario LDAP (vacío por defecto, lo escribes cada vez). |
| **Password** | Tu password LDAP. |
| **TOTP** | Solo en modo Pasarela: 6 dígitos del autenticador. |

Pulsa **🚀 Lanzar ejecución**. La pantalla salta automáticamente al **Monitor** y la tarea se procesa en el worker.

---

## 4. Monitor / histórico

> **Mantenimiento → Tareas → 📊 Monitor Ejecuciones**

- **Selector "Run"** — ordenado por fecha, el más reciente arriba.
- **🔄 Refrescar** — recarga la página (la tarea sigue en background; cada equipo añade una fila al log).
- **📥 CSV** — descarga del log en CSV (separador `;`, BOM UTF-8).
- **📊 Excel** — descarga XLSX. Las columnas de extracción están **forzadas a tipo texto** para evitar que Excel convierta SIMs / IMEIs a notación científica.

La tabla muestra: Centro, IP, Modelo, Host, Estado, [Extracciones], y un botón **RAW** por equipo que abre la salida cruda completa del SSH (para diagnóstico fino).

### Estados posibles

| Estado | Significado |
|---|---|
| `OK` | Sesión completa, todos los comandos correctos. |
| `ERROR` | Algún comando devolvió error. La fila incluye `ERR=...` con la línea exacta del equipo. La sesión se aborta y se cierra limpiamente; **el resto de comandos NO se ejecutan**. |
| `AUTH_FAIL` | Credenciales rechazadas. |
| `NO_PING` / `NO_CONNECT` | Equipo inalcanzable (ICMP en LAN2LAN, TCP/22 en pasarela). |
| `UNKNOWN_MODEL` | Banner SSH no encaja con ningún modelo soportado. |
| `NO_CMDS` | No se proporcionó fichero de comandos para esa familia. |
| `PASARELA_REQUIRED` | Equipo requiere modo Pasarela (Fortinet) y se lanzó en LAN2LAN. |
| `TIMEOUT` | El equipo no respondió en el tiempo esperado a un comando. |

---

## 5. Buenas prácticas

- **Prueba siempre con una lista pequeña** (filtra por un centro o un nemónico concreto) antes de lanzar sobre toda la planta.
- **Empieza con comandos de solo lectura** (`show ...`, `configuration`...) para verificar la sintaxis antes de hacer cambios.
- Si un comando falla **en el primer equipo**, cancela mentalmente y revisa el log. El sistema ya aborta esa sesión, pero seguirá probando en los siguientes equipos.
- Si vas a cambiar configuración, **incluye los comandos de salvado** al final (`save yes`, `confirm-cfg`, `wr mem`...) o NO se persistirán los cambios al reinicio.
- **No hace falta `exit`/`logout`** al final — el sistema cierra la sesión automáticamente.

---

## 6. Limitaciones conocidas

- **Una tarea a la vez** — el worker tiene mutex global; si hay otra tarea SSH en curso (Config Planta, Gentest, etc.) habrá que esperar.
- **Sin auto-refresh** del monitor — pulsa F5 o el botón Refrescar.
- **Sin botón Cancelar** — el worker corre en contenedor externo y no es trivial detener una tarea en marcha. Si te equivocaste, espera a que acabe.
- **Fortinet solo por Pasarela** — los Fortinet no son alcanzables por LAN2LAN.

---

## 7. Guía de regex (para extracciones)

Una **regex** (expresión regular) es un patrón que describe texto: en vez de decir "quiero la línea con `10.7.45.3`", describes "quiero un grupo de cuatro números separados por puntos". Así la misma extracción funciona para todos los equipos aunque la IP sea distinta en cada uno.

El SEM usa el motor **PCRE** (Perl-compatible) a través de `grep -oP`.

### 7.1 Símbolos básicos

| Símbolo | Significa | Ejemplo |
|---|---|---|
| `\d` | Un dígito (0-9) | `\d` matchea `7` |
| `\d+` | Uno o más dígitos | `\d+` matchea `2026` |
| `\d{N}` | Exactamente N dígitos | `\d{19}` matchea `8934075700093511035` |
| `\d{N,M}` | Entre N y M dígitos | `\d{1,3}` matchea `1`, `12` o `123` |
| `\.` | Un punto literal | `\.` matchea `.` |
| `\s` | Un espacio (incluye tab) | `\s+` matchea cualquier separador |
| `\S` | Un carácter NO-espacio | `\S+` matchea una "palabra" sin espacios |
| `[abc]` | Cualquiera de a, b o c | `[YN]` matchea `Y` o `N` |
| `[a-z]` | Cualquier letra minúscula | `[A-Z0-9]` matchea letra mayúscula o dígito |
| `?` | El anterior es opcional | `-?\d+` matchea con o sin signo: `5` o `-5` |
| `+` | Uno o más del anterior | `\d+` uno o más dígitos |
| `*` | Cero o más | `\s*` ningún o varios espacios |
| `\|` | O lógico | `up\|down` matchea `up` o `down` |
| `^` | Inicio de línea | `^%` línea que empieza por `%` |
| `$` | Final de línea | `\S+$` el último "trozo" sin espacios |
| `(...)` | Grupo (no influye en el match con `-oP`) | |

### 7.2 Recetas frecuentes

| Si quieres extraer... | Regex | Ejemplo de línea | Saca |
|---|---|---|---|
| Una IP | `\d+\.\d+\.\d+\.\d+` | ` ip address 10.7.45.3 255.255...` | `10.7.45.3` |
| Una IP/CIDR | `\d+\.\d+\.\d+\.\d+/\d+` | `loopback600  10.221.21.72/32` | `10.221.21.72/32` |
| IP y máscara | `\d+\.\d+\.\d+\.\d+\s+\d+\.\d+\.\d+\.\d+` | ` ip address 10.7.45.3 255.255.255.0` | `10.7.45.3 255.255.255.0` |
| Una MAC | `([0-9a-f]{2}[:.-]){5}[0-9a-f]{2}` | `Hardware is GigE, address is 0011.22aa.bbcc` | `0011.22aa.bbcc` |
| Un decimal con signo | `-?\d+\.\d+` | ` Rx optical power = -6.4 dBm` | `-6.4` |
| Un entero | `\d+` | `CPU temperature: 61 C` | `61` (el primer número) |
| Un SIM (19 dígitos) | `\d{19}` | `SIM Card ID = 8934075700093511035` | `8934075700093511035` |
| Un IMEI (15 dígitos) | `\d{15}` | `IMEI: 351234567890123` | `351234567890123` |
| Lo último de la línea | `\S+$` | `SIM Card ID                  = 8934...` | `8934...` |
| Hostname (alfanumérico+.-_) | `[A-Za-z0-9._-]+` | `Hostname: FFONMA00R` | el primer "palabra" |
| Un porcentaje | `\d+\s*%` | `Memory used: 45 %` | `45 %` |
| Una versión (formato X.Y.Z.W) | `\d+(\.\d+){3}` | `Software release: 11.02.01.20` | `11.02.01.20` |
| Estado up/down | `up\|down` | `Status: up` | `up` |

### 7.3 Cómo construir una regex desde cero

Imagina que tu salida tiene esta línea y quieres sacar la temperatura `61`:

```
CPU temperature: 61 C
```

Pasos:

1. **Identifica qué hay siempre alrededor del valor**: `CPU temperature: ` antes y ` C` después.
2. **Decide qué nivel de "anclaje" quieres**:
   - Permisivo: solo `\d+` — el primer número de la línea.
   - Anclado: `temperature:\s*\d+` — fuerza a estar tras `temperature:`.
3. **Define el valor con la regex apropiada**: aquí entero `\d+`.
4. **Pruébala**: si pones `LINE_MATCH = CPU temperature` la línea ya está filtrada. La regex `\d+` matchea `61`. Si más adelante hay otra línea con `CPU temperature: -10 C`, te interesará `-?\d+` para incluir el signo.

### 7.4 Trucos útiles

- `LINE_MATCH` es **subcadena literal**, no regex. Solo dice "que la línea contenga este texto". Si quieres que la línea matchee un patrón, déjalo vacío y mete todo el patrón en la regex.
- Si dudas qué línea coge, pulsa el botón **RAW** del Monitor en un equipo concreto: ahí ves la salida completa del comando y puedes probar tu regex mentalmente.
- Caracteres que hay que **escapar con `\`** en regex: `. + * ? ( ) [ ] { } | \ ^ $`. Si quieres un punto literal, pon `\.`.
- En Cisco las salidas vienen con `\r` ocultos al final. El SEM ya los limpia antes de aplicar la regex; tu regex no tiene que preocuparse de ellos.
- Si la regex no matchea nada, la celda queda **vacía** (no es un error).

---

## 8. Recetas listas para copiar/pegar

### 8.1 Sacar potencia óptica del SFP+ (Cisco)

**Comandos Cisco:**
```
show hw-module subslot 0/0 transceiver 13 status
```

**Extracciones:**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `show hw-module subslot 0/0 transceiver 13 status` | `Tx optical power` | `-?\d+\.\d+` | `Tx_dBm` |
| `show hw-module subslot 0/0 transceiver 13 status` | `Rx optical power` | `-?\d+\.\d+` | `Rx_dBm` |
| `show hw-module subslot 0/0 transceiver 13 status` | `Module temperature` | `\d+\.\d+` | `Modulo_Temp_C` |

### 8.2 Sacar SIM Card ID (Teldat 5G)

**Comandos Teldat** (desde el menú de monitorización):
```
p 3
network cellular1/0
sim-info
```

**Extracciones:**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `sim-info` | `SIM Card ID` | `\d{19}` | `ICC` |
| `sim-info` | `IMEI` | `\d{15}` | `IMEI` |
| `sim-info` | `IMSI` | `\d{15}` | `IMSI` |

### 8.3 Sacar IPs de las VLANs estándar (Teldat)

**Comandos Teldat:**
```
p 3
protocol ip
interface-addresses
```

**Extracciones (una por VLAN):**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `interface-addresses` | `ethernet0/0.10` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan10` |
| `interface-addresses` | `ethernet0/0.12` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan12` |
| `interface-addresses` | `ethernet0/0.37` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan37` |
| `interface-addresses` | `ethernet0/0.38` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan38` |
| `interface-addresses` | `ethernet0/0.39` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan39` |
| `interface-addresses` | `ethernet0/0.60` | `\d+\.\d+\.\d+\.\d+/\d+` | `Vlan60` |

### 8.4 Sacar IPs de las BDIs (Cisco) — sin error si la VLAN no existe

`show ip interface BDI<N>` da `% Invalid input` si la BDI no existe → aborta la sesión. La alternativa robusta usa `section`, que devuelve vacío si no existe (sin error). El precio es que solo devuelve **IP + máscara** (no CIDR); puedes convertir a CIDR luego con un script o fórmula Excel.

**Comandos Cisco:**
```
sh running | section interface BDI10
sh running | section interface BDI12
sh running | section interface BDI37
sh running | section interface BDI38
sh running | section interface BDI39
sh running | section interface BDI60
```

**Extracciones (una por VLAN):**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `sh running \| section interface BDI10` | `ip address` | `\d+\.\d+\.\d+\.\d+\s+\d+\.\d+\.\d+\.\d+` | `Vlan10` |
| `sh running \| section interface BDI12` | `ip address` | `\d+\.\d+\.\d+\.\d+\s+\d+\.\d+\.\d+\.\d+` | `Vlan12` |
| ... (idem 37/38/39/60) | | | |

### 8.5 Cambiar usuario local + verificar (Teldat)

**Comandos Teldat** (necesita salvar para persistir):
```
p 5
no user antiguo
user nuevo password CONTRASENA_NUEVA
save yes
end
p 4
confirm-cfg
sh config | include hash-password
```

**Extracción** (verificar que el user nuevo está en la config):

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `sh config \| include hash-password` | `user nuevo` | (vacío — devuelve la línea limpia) | `Hash_user_nuevo` |

### 8.6 Borrar usuario local con [confirm] (Cisco)

**Comandos Cisco** (la `[confirm]` sale automáticamente):
```
configure terminal
no username antiguo
(enter)
end
write memory
```

El `(enter)` (botón "Insertar Enter" sobre la caja Cisco) responde al `[confirm]` que dispara `no username` cuando hay configuración asociada. Sin extracciones, solo `STATUS=OK` confirma que se ejecutó.

### 8.7 Inventario de versión IOS (Cisco)

**Comandos Cisco:**
```
show versión | include uptime|Software release|System
```

**Extracciones:**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `show version \| include uptime\|Software release\|System` | `uptime is` | `\d+\s+(years?\|weeks?\|days?\|hours?)[^,]+` | `Uptime` |
| `show version \| include uptime\|Software release\|System` | `Software release` | `\d+(\.\d+){3,4}` | `IOS_Version` |

### 8.8 Inventario Fortinet (FortiGate, solo Pasarela)

**Comandos Fortinet:**
```
get system status
```

**Extracciones:**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `get system status` | `Version:` | `FortiGate-\S+` | `Modelo` |
| `get system status` | `Version:` | `v\d+\.\d+\.\d+,build\d+` | `Firmware` |
| `get system status` | `Serial-Number:` | `\S+$` | `SerialNumber` |
| `get system status` | `Cluster uptime:` | `\d+\s+days` | `Uptime_dias` |

### 8.9 Inventario Juniper (Junos)

**Comandos Juniper:**
```
show versión
show interfaces terse | match "Local"
```

**Extracciones:**

| CMD origen | Buscar línea con | Regex | Etiqueta |
|---|---|---|---|
| `show version` | `Hostname:` | `\S+$` | `Host` |
| `show version` | `Model:` | `\S+$` | `Modelo` |
| `show version` | `Junos:` | `\S+$` | `Junos_Version` |
