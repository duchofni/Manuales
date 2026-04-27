# Manual de Usuario: Módulo Visor de Correos

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Visor de Correos (MailViewer)      |
| **Versión** | 1.6                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El Visor de Correos permite buscar y consultar los correos electrónicos almacenados en el sistema. Los correos se agrupan automáticamente por **conversación** (mismo asunto) para facilitar el seguimiento de hilos. Puedes buscar por texto, remitente, carpeta y rango de fechas, y descargar correos como fichero `.eml`.

---

## 2. Buscar correos

Al entrar en el Visor de Correos verás un formulario de búsqueda con los siguientes campos:

| Campo         | Descripción                                                      |
|---------------|------------------------------------------------------------------|
| **Texto**     | Texto libre a buscar en los correos                              |
| **Campo**     | Dónde buscar: Todo, Asunto o Cuerpo                              |
| **Remitente** | Filtrar por dirección del remitente                               |
| **Carpeta**   | Filtrar por carpeta del buzón                                    |
| **Desde**     | Fecha de inicio del rango                                        |
| **Hasta**     | Fecha de fin del rango                                           |
| **Orden**     | Ordenar por: Fecha, Remitente o Asunto                           |

### 2.1. Realizar una búsqueda

1. Rellena los campos que necesites (no es obligatorio rellenar todos).
2. Pulsa **Buscar**.
3. Se mostrarán los resultados agrupados por conversación.

![Formulario de búsqueda con los 7 campos y los botones Buscar y Limpiar](./imagenes/captura-01-formulario-de-busqueda-con-los-7-campos.png)

### 2.2. Limpiar filtros

- Pulsa **Limpiar** para borrar todos los campos y volver al estado inicial.

> **Nota:** Sin filtros se muestran los **500 correos más recientes**. Con filtros se pueden mostrar hasta 10.000 resultados.

---

## 3. Ver conversaciones

Los resultados se muestran como una lista de conversaciones. Cada conversación muestra:

- **Asunto** del correo (con las palabras buscadas resaltadas en amarillo).
- **Badge** con el número de correos en la conversación (si hay más de uno).
- **Remitente**, **fecha** y **carpeta**.
- Enlace para **descargar** el correo en formato EML.

![Lista de resultados con varias conversaciones, mostrando el badge de conteo y los datos de cada correo](./imagenes/captura-02-lista-de-resultados-con-varias-conversac.png)

### 3.1. Ver un hilo de conversación

Si una conversación tiene **varios correos** (badge con número > 1):

1. Pulsa **"Ver conversación (N correos)"**.
2. Se desplegará la lista con todos los correos del hilo, ordenados cronológicamente.
3. Para cada correo verás: remitente, fecha, carpeta y enlace EML.
4. Pulsa de nuevo el título para cerrar el hilo.

![Conversación expandida mostrando la lista de correos del hilo](./imagenes/captura-03-conversacion-expandida-mostrando-la-list.png)

---

## 4. Ver el cuerpo de un correo

### 4.1. Correo individual (un solo correo en la conversación)

1. Pulsa **"Ver correo"**.
2. Se desplegará el cuerpo del correo directamente.

### 4.2. Correo dentro de un hilo

1. Expande la conversación.
2. En cada correo del hilo, pulsa **"Ver correo"**.
3. Se cargará el cuerpo de ese correo individual.
4. Si el término de búsqueda está presente, aparecerá **resaltado en amarillo**.

> **Nota:** Los cuerpos de los correos se cargan bajo demanda para optimizar la velocidad. La primera vez puede tardar un momento.

![Cuerpo de un correo expandido con el término de búsqueda resaltado en amarillo](./imagenes/captura-04-cuerpo-de-un-correo-expandido-con-el-ter.png)

---

## 5. Descargar correos como fichero .eml

1. Junto a cada correo verás un enlace **EML** (icono o texto).
2. Pulsa sobre él.
3. Se descargará un fichero `.eml` con el correo completo.
4. Puedes abrir el fichero `.eml` con Outlook u otro cliente de correo.

---

## 6. Navegación por páginas

- Los resultados se paginan de **50 conversaciones por página**.
- En la parte inferior verás:
  - Botones **Anterior** y **Siguiente**.
  - Información de la página actual.
  - Un campo para **ir directamente** a un número de página concreto.

![Barra de paginación con los botones Anterior, Siguiente y el campo Ir a página](./imagenes/captura-05-barra-de-paginacion-con-los-botones-ante.png)

---

## 7. Consejos de uso

- **Para buscar un correo concreto:** usa el campo Texto + Campo "Asunto" para afinar la búsqueda.
- **Para ver todos los correos de una persona:** usa el campo Remitente.
- **Para acotar por fechas:** rellena Desde y Hasta.
- **Si hay demasiados resultados** (más de 10.000), el sistema avisará. Añade más filtros para acotar.

---

*Manual para operadores CGE SERGAS. Versión 1.6 — Abril 2026.*
