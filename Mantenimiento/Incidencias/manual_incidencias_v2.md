# Manual de Usuario: Módulo Incidencias

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > Incidencias        |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo Incidencias permite gestionar las incidencias de red del CGE: crear nuevas, editarlas, cerrarlas, aplicar cambios masivos y consultar las ya cerradas. La pantalla principal tiene un diseño de **barra lateral** (sidebar) con tarjetas de incidencias activas y un **panel de detalle** a la derecha.

---

## 2. Ver incidencias abiertas (sidebar)

Al entrar en Incidencias verás la pantalla dividida en dos partes:

- **Izquierda (sidebar):** Lista de tarjetas con las incidencias activas.
- **Derecha (panel de detalle):** Vacío hasta que selecciones una incidencia.

Cada tarjeta muestra:
- **Tipo** (etiqueta de color: VOZ, DATOS, L1, L3, MODIF)
- **Centro**
- **SIXPI** (ticket del cliente)
- **GDIA** (ticket interno)
- **Última actuación**
- **Hora**

![Pantalla de Incidencias con el sidebar de tarjetas a la izquierda y el panel vacío a la derecha con el mensaje "Selecciona una incidencia"](./imagenes/captura-01-pantalla-de-incidencias-con-el-sidebar-d.png)

### 2.1. Filtrar por tipo

- Encima de la lista de tarjetas hay botones de filtro: **Todas**, **VOZ**, **DATOS**, **SOP L1**, **SOP L3**, **MODIF**.
- Pulsa el tipo que quieras ver. Solo se mostrarán las incidencias de ese tipo.

### 2.2. Buscar incidencias

- Usa el **campo de búsqueda** del sidebar para filtrar por centro, SIXPI o GDIA.
- Se filtran en tiempo real mientras escribes.

### 2.3. Contador

- Junto a los filtros verás un **contador** con el número de incidencias visibles.

---

## 3. Seleccionar varias incidencias (acción masiva)

### 3.1. Selección

1. Marca el **checkbox** de la esquina de cada tarjeta que quieras seleccionar.
2. O pulsa el checkbox **"Todas"** para seleccionar todas las visibles.
3. El botón **Masivo** mostrará el número de incidencias seleccionadas.

### 3.2. Aplicar acción masiva

1. Con incidencias seleccionadas, pulsa el botón **Masivo**.
2. Se abrirá un modal con los campos que puedes modificar en bloque:
   - **Estado**, **Urgencia** (1-3), **Responsable** (T/C)
   - **Fechas**: Respuesta, Solución, Cierre (pulsa en el campo de fecha para poner la fecha y hora actual)
   - **Añadir GDIA**: ticket + fecha
   - **Añadir actuación**: tipo + ticket + fecha
   - **Comentario** (sobreescribe el existente)
   - **Observaciones** (se añaden al final de las existentes)
   - **Incomunicado**, **Masiva**, **Local**, **Reposición** (solo VOZ)
3. Rellena solo los campos que quieras cambiar. Los campos vacíos no se modifican.
4. Pulsa **Aplicar**.

![Modal de edición masiva con los campos rellenables y el botón Aplicar](./imagenes/captura-02-modal-de-edicion-masiva-con-los-campos-r.png)

> **Importante para cerrar en bloque:** Si pones el estado CERRADA, debes rellenar obligatoriamente las fechas de Respuesta, Solución y Cierre.

---

## 4. Ver incidencias cerradas

1. Pulsa el botón **Ver cerradas** en la barra superior.
2. Se mostrará una **tabla** con todas las incidencias cerradas, ordenadas por fecha de cierre (más recientes primero).
3. Puedes:
   - **Filtrar por tipo** con los botones (VOZ, DATOS, etc.)
   - **Buscar** con el campo de búsqueda
   - **Editar** pulsando el icono del lápiz de cualquier fila

![Vista de incidencias cerradas en formato tabla con las columnas Centro, Tipo, SIXPI, GDIA, Asunto, fechas y Responsable](./imagenes/captura-03-vista-de-incidencias-cerradas-en-formato.png)

---

## 5. Crear una nueva incidencia

1. Pulsa el botón **Nueva incidencia** en la barra superior.
2. Se cargará el formulario de creación en el panel de detalle.

### 5.1. Centro y horario

1. Escribe el nombre del centro en el buscador. Aparecerán sugerencias.
2. Selecciona el centro. Se cargará automáticamente su **horario**.
3. Puedes modificar el **Horario de atención** si es diferente.

![Campo de búsqueda de centro con desplegable de sugerencias y el campo de horario autorellenado](./imagenes/captura-04-campo-de-busqueda-de-centro-con-desplega.png)

### 5.2. Tipo y subtipo

1. Selecciona el **Tipo de incidencia**: VOZ, DATOS, SOP TI L1, SOP TI L3, Modificaciones.
2. El desplegable de **Subtipo** se actualizará automáticamente con las opciones de ese tipo.

### 5.3. Modo línea (solo DATOS)

Si el tipo es **DATOS**, aparecerá un selector:
- **Sobre línea**: selecciona una o varias líneas del centro. Se creará una incidencia por cada línea.
- **General (sin línea)**: incidencia general sin asociar a una línea concreta.

### 5.4. GDIA

- Si seleccionaste **líneas**, puedes elegir:
  - **Un GDIA para todas las líneas**: un solo ticket GDIA.
  - **GDIA por línea**: un ticket GDIA diferente para cada línea.
- Si no hay líneas (VOZ u otros tipos), rellena el GDIA general.
- Introduce el **ticket** y la **fecha** del GDIA.

### 5.5. Resto de campos

| Campo                    | Descripción                                                    |
|--------------------------|----------------------------------------------------------------|
| SIXPI                    | Ticket del cliente                                             |
| Estado                   | EN SOLUCIÓN, OBSERVACIÓN, PTE CONFIRMACIÓN, CERRADA           |
| Urgencia                 | 1, 2 o 3                                                      |
| Responsable              | T (Telefónica) o C (Cliente)                                   |
| Fecha apertura cliente   | Obligatoria. Fecha en que el cliente abrió la incidencia       |
| Fecha respuesta cliente  | Pulsa en el campo para poner la fecha y hora actual            |
| Incomunicado             | Marcar si el centro está incomunicado (visible si DATOS)       |
| Masiva                   | Marcar si es incidencia masiva (visible si DATOS)              |
| Reposición               | NO / SI / AP (solo visible si VOZ)                             |
| Local                    | Marcar si es incidencia local                                  |

### 5.6. Actuaciones

1. Pulsa **+ Actuación** para añadir una fila.
2. Selecciona el **tipo** de actuación en el desplegable.
3. Introduce el **ticket** y la **fecha**.
4. Para añadir más actuaciones, pulsa de nuevo **+ Actuación**.
5. Para eliminar una, pulsa el botón de eliminar de esa fila.

### 5.7. Comentarios

- **Comentario**: información para el cliente.
- **Observaciones**: notas internas (no visibles para el cliente).

### 5.8. Guardar

1. Revisa todos los datos.
2. Pulsa **Guardar**.
3. Si hay errores de validación, se mostrarán mensajes indicando qué falta.
4. Si todo es correcto, se creará la incidencia y volverás a la lista.

> **Nota sobre líneas duplicadas:** Si intentas crear una incidencia sobre una línea que ya tiene otra incidencia activa con el mismo nemónico, esa línea se omitirá automáticamente.

---

## 6. Editar una incidencia

1. Pulsa sobre una **tarjeta** del sidebar (incidencias abiertas) o el **icono del lápiz** (incidencias cerradas).
2. Se cargará el formulario de edición con todos los datos de la incidencia.

### 6.1. Diferencias con la creación

- El **centro** no se puede cambiar.
- Aparecen campos adicionales de fecha: **Solución** y **Cierre** (pulsa para poner fecha actual).
- Los **GDIAs existentes** se muestran en una tabla editable (puedes modificar ticket y fecha).
- Las **actuaciones existentes** también son editables (ticket y fecha; el tipo no se puede cambiar).
- Puedes **añadir un nuevo GDIA** o una **nueva actuación** al final.

### 6.2. Copiar para GDIA

1. Pulsa el botón **Copiar para GDIA**.
2. Se copiará al portapapeles la información formateada del centro (centro, horario, asunto, SIXPI).
3. Aparecerá brevemente un mensaje de confirmación.
4. Pega esta información donde la necesites al abrir un GDIA.

![Botón "Copiar para GDIA" en la parte superior del formulario de edición](./imagenes/captura-05-boton-copiar-para-gdia-en-la-parte-super.png)

### 6.3. Validaciones al guardar

El sistema válida la **cadena de fechas**:
- La fecha de respuesta no puede ser anterior a la de apertura.
- La fecha del GDIA no puede ser anterior a la de apertura.
- La fecha de solución debe ser posterior a apertura, respuesta y GDIAs.
- La fecha de cierre debe ser posterior a todas las demás.

Si el estado es:
- **CERRADA**: obligatorias apertura, respuesta, solución y cierre.
- **OBSERVACIÓN o PTE CONFIRMACIÓN**: obligatorias apertura, respuesta y solución.

### 6.4. Guardar

1. Pulsa **Guardar**.
2. Si hay errores, se mostrarán los mensajes correspondientes.
3. Si todo es correcto, se guardarán los cambios.

---

## 7. Resumen de flujo habitual

1. Se recibe aviso de incidencia.
2. **Crear** la incidencia con los datos del centro, tipo, GDIA, etc.
3. Gestionar la incidencia: añadir actuaciones, modificar estado.
4. **Copiar para GDIA** cuando necesites abrir un ticket interno.
5. Cuando se resuelva, poner estado **CERRADA** con todas las fechas.
6. Para actualizaciones en bloque, usar **acción masiva**.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
