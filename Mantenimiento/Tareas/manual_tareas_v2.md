# Manual de Usuario: Módulo Tareas

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > Tareas             |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo Tareas permite ejecutar tareas de configuración y validación en equipos de planta de forma remota (vía SSH). Todas las tareas comparten el mismo patrón de uso: ejecutar, ver resultados, copiar tabla, relanzar fallidos y enviar por correo.

Las tareas disponibles son:
- **Config. Planta** (routers de datos)
- **Config. Planta Voz** (equipos de voz)
- **Gentest Routers 5G** (gentest en routers 5G)
- **Revisión Serial** (comprobación de números de serie)
- **Validación Logos-PT** (comparación Logos-PT vs BDU)
- **Test DCT Masivo** (envío #016# a los ~405 DCTs vía SMS)

---

## 2. Patrón común de las tareas SSH

Las cuatro primeras tareas (Config. Planta, Config. Planta Voz, Gentest 5G y Revisión Serial) funcionan exactamente igual. A continuación se explica el flujo completo.

### 2.1. Vistas disponibles

Al entrar en cualquiera de estas tareas, verás tres pestañas o vistas:

- **Equipos válidos**: equipos que cumplen los requisitos para ejecutar la tarea (IP correcta, modelo compatible, etc.).
- **Equipos excluidos**: equipos que no cumplen los requisitos.
- **Histórico**: resultados de ejecuciones anteriores.

![Vista de una tarea SSH mostrando la tabla de equipos válidos con las columnas de datos del equipo](./imagenes/captura-01-vista-de-una-tarea-ssh-mostrando-la-tabl.png)

### 2.2. Ejecutar una tarea

1. Pulsa el botón **Ejecutar tarea**.
2. Se abrirá una ventana pidiendo las **credenciales SSH**:
   - **Usuario**
   - **Contraseña**
   - **Confirmar contraseña** (debe coincidir con la anterior)
3. Pulsa **Ejecutar**.
4. La tarea se lanzará en segundo plano. El botón cambiará a **"Tarea en curso o en cola"** y quedará deshabilitado.
5. Espera a que termine. La página se actualiza automáticamente.

![Ventana emergente de credenciales SSH con los campos Usuario, Contraseña y Confirmar contraseña](./imagenes/captura-02-ventana-emergente-de-credenciales-ssh-co.png)

> **Importante:** Si las contraseñas no coinciden, aparecerá un mensaje de error y no se podrá ejecutar.

> **Nota:** Solo puede haber una tarea en ejecución a la vez. Si ya hay otra en curso, el botón aparecerá deshabilitado.

### 2.3. Ver resultados (histórico)

1. Pulsa **Histórico tareas**.
2. Selecciona un **fichero de log** en el desplegable (ordenados por fecha, el más reciente primero).
3. Verás una tabla con los resultados de cada equipo:

| Estado       | Significado                                        |
|--------------|----------------------------------------------------|
| **OK**       | La tarea se ejecutó correctamente                  |
| **FAIL**     | La tarea falló                                     |
| **NO_PING**  | No se pudo conectar al equipo (no responde a ping) |
| **AUTH_FAIL** | Las credenciales SSH fueron rechazadas             |
| **UNKNOWN**  | Estado desconocido                                 |
| **DISCREPANCIA** | El nemónico del log no coincide con la BDU     |

4. En la parte superior verás las **estadísticas**: total de equipos, cuántos OK, FAIL, etc., y el porcentaje de éxito.
5. Puedes **filtrar** por estado usando los botones: TODOS, OK, FAIL, AUTH_FAIL, NO_PING, UNKNOWN, DISCREPANCIA.

![Vista de histórico mostrando las estadísticas arriba y la tabla de resultados con colores por estado](./imagenes/captura-03-vista-de-historico-mostrando-las-estadis.png)

### 2.4. Copiar tabla

- Pulsa el botón **Copiar tabla** para copiar los resultados al portapapeles.
- Puedes pegar la tabla en un correo o documento.

### 2.5. Relanzar fallidos

1. Pulsa el botón **Relanzar fallidos**.
2. Se ejecutará la tarea solo sobre los equipos que tuvieron estado FAIL o AUTH_FAIL en la última ejecución.
3. Se te pedirán las credenciales SSH de nuevo.

### 2.6. Enviar por correo

- Pulsa el botón **Mail** para abrir tu cliente de correo con un mensaje preparado.
- El asunto incluye el nombre de la tarea y la fecha.
- Pega la tabla copiada en el cuerpo del correo.

---

## 3. Config. Planta (Datos)

- **Equipos incluidos:** Routers CISCO, TELDAT y JUNIPER gestionables con IP válida (rango 172.30.x.x o 10.x.x.x).
- **Propósito:** Verificar y recoger configuraciones de los routers de datos.
- **Flujo:** Igual al patrón común descrito arriba.

---

## 4. Config. Planta Voz

- **Equipos incluidos:** Equipos de voz (OXE, CISCO, etc.).
- **Propósito:** Verificar configuraciones de equipos de voz.
- **Flujo:** Idéntico a Config. Planta pero sobre equipos de voz.

---

## 5. Gentest Routers 5G

- **Equipos incluidos:** Routers con conexión 5G.
- **Propósito:** Ejecutar pruebas gentest en routers 5G.
- **Flujo:** Idéntico al patrón común.

---

## 6. Revisión Serial

- **Equipos incluidos:** Equipos de datos con número de serie registrado.
- **Propósito:** Comparar el número de serie almacenado en la BDU con el que realmente tiene el equipo (obtenido vía SSH).
- **Flujo:** Idéntico al patrón común, con estas acciones adicionales:

### 6.1. Simular

- Puedes ver los resultados de la comparación sin aplicar cambios a la base de datos.

### 6.2. Actualizar en BBDD

- Si hay discrepancias entre el serial de la BDU y el real, puedes actualizar los datos en la base de datos con los valores recogidos.

### 6.3. Enviar por correo

- Igual que en las demás tareas, puedes copiar la tabla y enviarla por correo.

---

## 7. Validación Logos-PT

Esta tarea es diferente a las anteriores. No se conecta por SSH sino que compara un fichero CSV exportado desde Logos-PT con los datos de la BDU.

### 7.1. Subir fichero CSV

1. Desde el menú Tareas, selecciona **Validación Logos-PT**.
2. Pulsa **Seleccionar archivo** y elige el fichero CSV exportado desde Logos-PT (separador `|`).
3. Pulsa **Comparar**.

![Formulario de subida del CSV de Logos-PT con el botón Comparar](./imagenes/captura-04-formulario-de-subida-del-csv-de-logos-pt.png)

### 7.2. Ver resultados

Tras la comparación, verás dos tablas:

- **Discrepancias**: líneas que existen en ambos sistemas pero con nemónico diferente.
  - Columnas: Centro, Administrativo, Nemónico Logos-PT, Nemónico BDU.
- **No encontrados**: líneas que están en el CSV de Logos-PT pero no se encontraron en la BDU.
  - Columnas: Administrativo, Nemónico Logos-PT.

Cada tabla tiene un botón **Copiar tabla** para copiar los datos al portapapeles.

![Resultados de la comparación mostrando la tabla de discrepancias y la tabla de no encontrados](./imagenes/captura-05-resultados-de-la-comparacion-mostrando-l.png)

### 7.3. Histórico

- Pulsa **Histórico** para ver los resultados de comparaciones anteriores.
- Selecciona un fichero de log en el desplegable.
- Se mostrarán las mismas tablas de discrepancias y no encontrados.

### 7.4. Nueva comparación

- Pulsa **Nueva comparación** para volver al formulario y subir otro fichero.

---

## 8. Test DCT Masivo

Esta tarea NO usa SSH. Envía por SMS el comando **#016#** a los ~405 DCTs (Dispositivos de Control de Tensión) del parque SERGAS. Cada DCT responde con otro SMS que incluye temperaturas y alarmas. La BDU asocia la respuesta al test pendiente y lo marca como OK.

**Propósito:** verificar semanalmente que todos los DCTs están vivos y responden al polling.

### 8.1. Cómo lanzarla

1. Entra en **Mantenimiento → Tareas → Test DCT**.
2. En la parte superior verás el botón **Lanzar tarea ahora**.
3. Pulsa. Aparece un prompt pidiendo escribir `MASIVO` como confirmación.
4. Teclea **MASIVO** (en mayúsculas, sin acentos).
5. Pulsa **Aceptar**.

Se encolan los ~405 SMS en gammu-smsd. El envío es escalonado en lotes de 20 cada 10 minutos (para no saturar la red de Movistar). El proceso tarda aproximadamente **5 horas** en completar los ~405.

> **Importante:** no hace falta que dejes la página abierta. Los SMS salen en segundo plano desde el contenedor gammu-smsd del servidor. Puedes cerrar el navegador.

### 8.2. Lotes (histórico)

En el panel principal de Test DCT ves la tabla de lotes anteriores, con columnas:

| Columna | Significado |
|---|---|
| Lote | Identificador único (ej. `masivo_20260421_130000`) |
| Fecha inicio / fin | Cuándo empezó y cuándo terminó el envío |
| Total / OK / Timeout / Pendientes | Contadores del lote |

Pulsa sobre un lote para ver el detalle.

### 8.3. Detalle de un lote

En el detalle verás todos los DCTs del lote con su estado individual:

| Estado | Significado |
|---|---|
| **✓ OK** | El DCT respondió al #016# |
| **⚠ Timeout** | Pasaron más de 7 min sin respuesta |
| **⏳ Pendiente** | Esperando respuesta (todavía dentro de la ventana de 7 min) |
| **✗ Error** | Fallo al encolar el SMS (raro) |

Puedes filtrar por estado con el desplegable.

### 8.4. Reintentar fallidos

En el detalle del lote, las filas con estado distinto de OK tienen un botón **🔍 Reintentar**. Pulsa → se envía #016# otra vez a ese DCT individual.

Útil cuando un DCT pierde cobertura momentáneamente y no respondió a tiempo en el lote inicial.

### 8.5. Exportar Excel

Dos botones en la cabecera del detalle:

- **⬇ Excel fallidos**: exporta solo los DCTs con estado Timeout.
- **⬇ Excel todos**: exporta los ~405 con todas las columnas.

Cada fila incluye: Centro, AS, Provincia, nº DCT, fecha envío, fecha respuesta, estado, temperatura externa, alarma de corte. Coloreado por estado.

### 8.6. Preguntas frecuentes

**¿Puedo lanzar dos tareas masivas seguidas?**
No tiene sentido — si la anterior aún tiene pendientes se solapan. Espera a que la primera termine (~5h) antes de lanzar otra. Si realmente es urgente, el botón no te lo impide físicamente, pero los resultados serán confusos.

**¿Puedo lanzar el test a un único DCT sin lanzar el masivo?**
Sí, desde **Mantenimiento → Preventivo → DCT**. En el buscador del panel principal escribes el centro, pulsas, y aparece el botón **🔍 Lanzar #016#**. Ese test individual también queda registrado pero no crea lote masivo.

**¿Los correos del CGE los recibe alguien al terminar?**
No, Test DCT Masivo NO envía correo. El correo automático solo se envía por los eventos reales de corte o recuperación. Para revisar resultados del test hay que entrar a la vista.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
