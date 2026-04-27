# Manual de Usuario: Módulo Nagios

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > Nagios             |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo Nagios permite consultar el estado de los equipos monitorizados, ver el historial de eventos (caídas y recuperaciones) y gestionar la planta Nagios (dar de alta o de baja equipos en la monitorización).

---

## 2. Ver estado de hosts

Al entrar en Nagios verás el **panel principal** con:

### 2.1. Hosts caídos (DOWN)

- Una tabla con los equipos que actualmente están **caídos**.
- Para cada host se muestra: nemónico, IP, tipo de equipo, centro y fecha de caída.

[CAPTURA: Panel principal de Nagios mostrando la tabla de hosts actualmente DOWN]

### 2.2. Qué significa cada estado

| Estado       | Significado                                                         |
|--------------|---------------------------------------------------------------------|
| **DOWN**     | El equipo está caído, no responde a la monitorización               |
| **RECOVERY** | El equipo se ha recuperado (antes estaba caído)                     |
| **ERROR**    | Hubo un error al intentar comprobar el estado del equipo            |

### 2.3. Log de eventos

- Debajo de la tabla de hosts DOWN hay un **historial de eventos**.
- Muestra los eventos DOWN, RECOVERY y ERROR con fecha y detalles.
- Se pagina de **25 en 25** registros.
- Puedes **filtrar** el log:
  - Por **texto** (nemónico, centro, etc.)
  - Por **tipo de evento** (DOWN, RECOVERY, ERROR)

[CAPTURA: Log de eventos de Nagios con los filtros de texto y tipo de evento]

### 2.4. Crear incidencias desde hosts DOWN

- Si hay hosts caídos que aún no tienen incidencia asociada, puedes pulsar el botón **Crear incidencias** para generarlas automáticamente.

### 2.5. Lanzar worker manualmente

- El botón **Lanzar worker** fuerza una sincronización manual del estado de los hosts.
- Normalmente esto se ejecuta automáticamente de forma periódica.

---

## 3. Planta Nagios (Alta y baja de hosts)

Desde el menú de Incidencias, pulsa **Planta Nagios** para acceder a la gestión de alta/baja de equipos.

### 3.1. Buscar un equipo

1. Escribe el **nemónico** del equipo en el campo de búsqueda.
2. Pulsa **Buscar**.
3. Se mostrará la **ficha del equipo** con toda su información:
   - Nemónico, IP, origen (DATOS o VOZ), tipo de línea
   - Administrativo, nodo, centro, horario, modelo

[CAPTURA: Ficha del equipo buscado mostrando todos sus datos]

### 3.2. Dar de alta un equipo

Si el equipo **no está** dado de alta en Nagios:

1. Se mostrará un formulario de alta con los campos **Alias** e **IP** (editables, prellenados).
2. Revisa los datos.
3. Pulsa **Dar de alta**.
4. El equipo se añadirá al fichero de configuración de Nagios correspondiente según su tipo:

| Tipo de línea | Fichero Nagios     |
|---------------|--------------------|
| MACROLAN      | macrolan.cfg       |
| FUSIÓN        | macrolan.cfg       |
| FTTH          | vpn-ip.cfg         |
| FTTO          | vpn-ip.cfg         |
| 4G            | 4g.cfg             |
| 5G            | 4g.cfg             |
| OXE           | alcatel.cfg        |
| CISCO         | cisco.cfg          |

5. Nagios se recargará automáticamente para aplicar el cambio.

[CAPTURA: Formulario de alta en Nagios con los campos Alias e IP y el botón Dar de alta]

### 3.3. Dar de baja un equipo

Si el equipo **ya está** dado de alta en Nagios:

1. Se mostrará un botón de **Dar de baja**.
2. Pulsa **Dar de baja**.
3. El equipo se eliminará del fichero de configuración de Nagios.
4. Nagios se recargará automáticamente.

> **Importante:** Dar de baja un equipo significa que Nagios dejará de monitorizarlo. Solo hazlo si el equipo ya no necesita supervisión.

---

## 4. Resumen del flujo habitual

1. Consultar el panel principal para ver hosts **DOWN**.
2. Revisar el **log de eventos** para entender qué ha pasado.
3. Si es necesario, **crear incidencias** desde los hosts caídos.
4. Para añadir nuevos equipos a la monitorización, usar **Planta Nagios > Alta**.
5. Para retirar equipos, usar **Planta Nagios > Baja**.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
