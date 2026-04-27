# Manual de Usuario: Módulo BTPs

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > BTPs               |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo BTPs permite gestionar los **Boletines de Trabajo Planificado** de Telefónica: importarlos desde Excel, consultarlos por estado o por número, crear BTPs manuales, y controlar cuáles están pendientes de informar al cliente.

---

## 2. Importar BTPs desde Excel

Desde el menú de Mantenimiento, pulsa la tarjeta **BTPs** y selecciona **Importación BTPs**.

Verás dos paneles de importación:

### 2.1. Importar Excel completo de Telefónica

Este método importa el fichero Excel diario completo de Telefónica. Inserta los BTPs nuevos y **actualiza** los que ya existían si hay cambios.

1. Pulsa **Seleccionar archivo** y elige el fichero `.xlsx` de Telefónica.
2. Pulsa **Importar**.
3. Espera a que se procese. Al terminar verás un resumen con:
   - Registros **insertados** (nuevos)
   - Registros **actualizados** (ya existían pero tenían cambios)
   - Registros **sin cambios** (ya estaban al día)

[CAPTURA: Panel de importación Excel completo con el botón de seleccionar archivo y el botón Importar]

### 2.2. Importar BTPs del día

Este método importa solo los BTPs nuevos del día. Si un BTP ya existe, **no lo modifica**.

1. Pulsa **Seleccionar archivo** y elige el fichero `.xlsx`.
2. Pulsa **Importar**.
3. Al terminar verás un resumen con:
   - Registros **insertados**
   - Registros **omitidos** (ya existían)
   - Registros **ignorados** (de otro CIF, no son de SERGAS)
   - **Errores** (si los hubiera)

> **Diferencia clave:** La importación completa actualiza BTPs existentes; la del día solo inserta nuevos.

---

## 3. Consulta por estado

Desde el menú BTPs, selecciona **Consulta Estado**.

### 3.1. Buscar BTPs por estado

1. Selecciona un **estado** en el desplegable:
   - AUTORIZADO
   - PTE AUTORIZACIÓN
   - CIERRE DE OBRA
   - CANCELADO
   - SUSPENDIDO
   - RECHAZADO
2. Se mostrará la tabla con todos los BTPs en ese estado.

[CAPTURA: Desplegable de estados con la tabla de resultados debajo]

### 3.2. Buscar dentro de los resultados

- Usa el **campo de búsqueda** encima de la tabla para filtrar por cualquier dato (centro, BTP, motivo, etc.).

### 3.3. Navegar por páginas

- La tabla muestra **50 registros por página**.
- Usa los **números de página** en la parte inferior para navegar.

### 3.4. Cambiar el estado de un BTP

1. En la columna **Estado** de cada fila, verás un desplegable.
2. Selecciona el nuevo estado.
3. La fila desaparecerá con una animación (ya no pertenece al estado que estás consultando).

[CAPTURA: Fila de un BTP con el desplegable de estado abierto mostrando las opciones]

### 3.5. Exportar resultados

- Con un estado seleccionado, aparecen botones para exportar a **CSV**, **PDF** o **Excel**.
- Pulsa el formato deseado para descargar el fichero.

### 3.6. Colores de las filas

- **Fila con fondo verde claro**: BTP ya informado al cliente.
- **Fila con fondo amarillo claro**: BTP autorizado pero pendiente de informar.

---

## 4. Consulta por número de BTP

Desde el menú BTPs, selecciona **Consulta N BTP**.

### 4.1. Buscar un BTP

1. Escribe el **número de BTP** en el campo de búsqueda (mínimo 2 caracteres).
2. Aparecerá un **desplegable de sugerencias** con los BTPs que coinciden.
3. Pulsa sobre el BTP deseado.
4. Se mostrará la tabla con todas las líneas de ese BTP.

[CAPTURA: Campo de búsqueda con el desplegable de sugerencias de BTPs]

### 4.2. Copiar tabla y enviar por correo

1. Pulsa el botón **Copiar**.
   - El botón será **rojo** si el BTP tiene afectación al servicio, o **azul** si no la tiene.
2. La tabla se copia al portapapeles.
3. Automáticamente se marca el BTP como **informado al cliente**.
4. Se abrirá tu cliente de correo con un mensaje preparado:
   - **Destinatarios** ya rellenados (soporte.comunicacions@sergas.es, soporte.voz@sergas.es, etc.)
   - **Asunto** con la fecha, número de BTP y si tiene o no afectación.
5. **Pega** la tabla (Ctrl+V) en el cuerpo del correo y envía.

[CAPTURA: Botón Copiar (rojo o azul) junto a la tabla de resultados del BTP]

### 4.3. Editar un BTP en el modal

1. Pulsa el **icono del lápiz** en la columna de edición de la fila que quieras modificar.
2. Se abrirá una ventana modal con los campos editables:
   - Estado, Afectación al servicio, Fechas (inicio/fin trabajo, inicio/fin corte)
   - Duración prevista, Criticidad, Motivo, Equipo, Provincia, Dirección, Descripción
3. Modifica los campos necesarios.
4. Pulsa **Guardar**.
5. La página se recargará con los datos actualizados.

> **Nota:** El número de BTP no se puede modificar.

[CAPTURA: Modal de edición de BTP con los campos rellenados y el botón Guardar]

---

## 5. BTP Manual

Desde el menú BTPs, selecciona **BTP Manual**.

### 5.1. Importación masiva por plantilla

1. Pulsa **Descargar plantilla** para obtener un fichero Excel con el formato correcto.
2. Rellena la plantilla con los datos de los BTPs.
   - Los campos Afectación (SI/NO) y Estado tienen desplegables en el Excel.
3. Pulsa **Seleccionar archivo** y elige la plantilla rellenada.
4. Pulsa **Importar**.

### 5.2. Alta individual (formulario)

1. Rellena los campos del formulario:
   - **BTP** (número), **Fecha inicio**, **Fecha fin**, **Fecha corte**, **Duración**
   - **Centro**, **Administrativo**, **Tipo línea**, **Rol**, **Nemónico**, **Velocidad**
   - **Equipo**, **Afectación**, **Estado**, **Motivo**, **Descripción**
2. Tienes dos opciones:
   - **Generar tabla**: muestra una vista previa del BTP en formato tabla (sin guardarlo aún).
   - **Insertar en BBDD**: guarda el BTP en la base de datos (te pedirá confirmación).

[CAPTURA: Formulario de alta manual de BTP con los campos rellenados y los dos botones: Generar tabla e Insertar en BBDD]

### 5.3. Copiar y enviar desde la vista previa

- Tras pulsar "Generar tabla", aparece la tabla con un botón **Copiar** (rojo o azul según afectación).
- Funciona igual que en la consulta por número: copia la tabla y abre el correo.

> **Importante:** Si ya existe un BTP con el mismo número, no se permitirá insertarlo de nuevo.

---

## 6. BTPs Pendientes

Desde el menú BTPs, selecciona **BTPs Pendientes**.

Esta vista muestra todos los BTPs con estado **AUTORIZADO** que aún **no se han informado al cliente**.

- La tabla muestra: Centro, Fecha de corte, Duración, Administrativo, BTP, Motivo.
- Están ordenados por fecha de corte (los más próximos primero).
- Pulsa **Abrir** para ir a la consulta por número de ese BTP, donde podrás copiarlo y enviarlo.

[CAPTURA: Tabla de BTPs pendientes de informar con la columna Abrir]

---

## 7. Revisión diaria

En el acordeón de BTPs hay un **botón morado** llamado **Revisión diaria**.

- Al pulsarlo, se abre tu cliente de correo con un mensaje predefinido dirigido a cgp.sergas@telefonica.com.
- El asunto incluye la fecha del día.
- El cuerpo contiene la plantilla de revisión diaria de BTPs.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
