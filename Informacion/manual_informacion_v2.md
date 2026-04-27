# Manual de Usuario -- Modulo Informacion / Ayuda

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Informacion / Ayuda            |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al modulo Informacion](#1-acceder-al-modulo-informacion)
2. [Panel principal](#2-panel-principal)
3. [Activar el modo editor](#3-activar-el-modo-editor)
4. [Enlaces de interes](#4-enlaces-de-interes)
5. [Escalados / Directorio de contactos](#5-escalados--directorio-de-contactos)
6. [NAT / LAN2LAN](#6-nat--lan2lan)

---

## 1. Acceder al modulo Informacion

1. Abre la aplicacion Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Informacion** (o **Ayuda**).
3. Aparecera el panel principal con tres secciones disponibles.

![Panel principal del modulo Informacion mostrando las tres tarjetas de navegacion](./imagenes/captura-01-panel-principal-del-modulo-informacion-m.png)

---

## 2. Panel principal

El panel principal muestra tres bloques de acceso rapido:

| Bloque                      | Que contiene                                          |
|-----------------------------|-------------------------------------------------------|
| **Red y Conectividad**      | Tabla NAT LAN2LAN                                     |
| **Contactos / Escalados**   | Directorio de contactos y escalados                    |
| **Herramientas**            | Enlaces de interes                                     |

Haz clic en cualquiera de los tres bloques para acceder a esa seccion.

En la cabecera veras:
- El titulo **"Modulo Informacion / Ayuda"**
- Un boton **Editor** para activar el modo de edicion (ver seccion 3)

---

## 3. Activar el modo editor

El modo editor permite crear, modificar y eliminar datos en las tres secciones (enlaces, escalados y NAT). Esta protegido por contrasena.

### Activar

1. Haz clic en el boton **Editor** en la cabecera.
2. Aparecera una ventana pidiendo la contrasena.
3. Introduce la contrasena y pulsa **Entrar** (o la tecla Enter).
4. Si es correcta, la pagina se recargara con el modo editor activo.
5. Veras una etiqueta **EDITOR** junto a tu nombre de usuario.

![Ventana de login de editor con el campo de contrasena y el boton Entrar](./imagenes/captura-02-ventana-de-login-de-editor-con-el-campo.png)

> **Atencion:** Si introduces la contrasena incorrecta **3 veces seguidas**, tu acceso se bloqueara durante **5 minutos**. Deberas esperar antes de volver a intentarlo.

### Desactivar

1. Haz clic en el boton **Salir** que aparece junto a la etiqueta EDITOR.
2. La pagina se recargara en modo lectura.

---

## 4. Enlaces de interes

### 4.1 Ver los enlaces

1. Desde el panel principal, haz clic en **Herramientas** (o **Enlaces de interes**).
2. Los enlaces estan organizados por **categorias** (bloques de colores).
3. Cada enlace muestra:
   - Una abreviatura o punto de color
   - El nombre del enlace (haz clic para abrirlo en una nueva pestana)
4. Las primeras 3 categorias aparecen en la fila superior; el resto debajo.

![Vista de enlaces de interes con varias categorias y enlaces agrupados por colores](./imagenes/captura-03-vista-de-enlaces-de-interes-con-varias-c.png)

### 4.2 Crear un enlace nuevo (modo editor)

1. Activa el modo editor (ver seccion 3).
2. En la categoria donde quieras anadir el enlace, haz clic en el boton **+** (anadir enlace).
3. Se abrira una ventana con los campos:
   - **Nombre** (obligatorio) -- Texto que se mostrara
   - **URL** (obligatorio) -- Direccion web del enlace
   - **Abreviatura** -- Texto corto para el badge (opcional)
   - **Descripcion** -- Descripcion adicional (opcional)
4. Haz clic en **Guardar**.

![Ventana de crear enlace con los campos Nombre, URL, Abreviatura y Descripcion](./imagenes/captura-04-ventana-de-crear-enlace-con-los-campos-n.png)

### 4.3 Editar un enlace (modo editor)

1. Haz clic en el boton de editar (icono de lapiz) junto al enlace.
2. Se abrira la ventana con los datos actuales.
3. Modifica lo que necesites.
4. Haz clic en **Guardar**.

### 4.4 Eliminar un enlace (modo editor)

1. Abre la ventana de edicion del enlace.
2. Haz clic en el boton **Eliminar** (rojo, en la parte inferior).
3. El enlace se eliminara.

### 4.5 Crear una categoria nueva (modo editor)

1. Haz clic en el boton para crear una nueva categoria.
2. Introduce el **nombre** de la categoria.
3. Opcionalmente, elige un **color** con el selector de color.
4. Haz clic en **Guardar**.

### 4.6 Editar o eliminar una categoria (modo editor)

1. Haz clic en el boton de editar categoria (junto al nombre de la categoria).
2. Modifica el nombre o el color.
3. Para eliminar, haz clic en **Eliminar**.

> **Atencion:** Al eliminar una categoria se eliminan **todos los enlaces** que contiene. El sistema pedira confirmacion antes de proceder.

---

## 5. Escalados / Directorio de contactos

### 5.1 Navegar por las pestanas

1. Desde el panel principal, haz clic en **Contactos / Escalados**.
2. Aparecera una barra de **pestanas** con las secciones disponibles:
   - Escalados Incidencias
   - Personal CGE
   - Personal CST
   - Personal Satec
   - Personal Nubodata
   - Circet
   - Envios Zeleris
3. Cada pestana muestra un **contador** con el numero de contactos.
4. Haz clic en una pestana para ver los contactos de esa seccion.

![Barra de pestanas de escalados con los contadores y una seccion seleccionada](./imagenes/captura-05-barra-de-pestanas-de-escalados-con-los-c.png)

### 5.2 Ver los contactos

Los contactos se muestran como **tarjetas** agrupadas por grupos dentro de cada seccion.

Cada tarjeta muestra:
- **Nombre**
- **Telefono** (haz clic para llamar)
- **Correo** (haz clic para enviar email)
- **Campos extra** (varian segun la seccion, por ejemplo: "Descripcion", "Usuario Telefonica", "DNI/Matricula", etc.)
- **Notas** (si las hay)

![Tarjetas de contactos mostrando nombre, telefono, correo y campos extra](./imagenes/captura-06-tarjetas-de-contactos-mostrando-nombre-t.png)

### 5.3 Buscar un contacto

1. Escribe en el campo de **busqueda** (parte superior).
2. Haz clic en **Buscar** o pulsa Enter.
3. Se buscara en nombre, telefono, correo y campos extra de **todas las secciones**.
4. Los resultados se mostraran agrupados por seccion.
5. Para limpiar la busqueda, haz clic en **Limpiar**.

![Resultados de busqueda de contactos mostrando coincidencias de varias secciones](./imagenes/captura-07-resultados-de-busqueda-de-contactos-most.png)

### 5.4 Crear un contacto nuevo (modo editor)

1. Activa el modo editor.
2. Haz clic en el boton **Nuevo contacto**.
3. Se abrira una ventana con los campos:
   - **Grupo** -- Subgrupo dentro de la seccion
   - **Nombre** (obligatorio)
   - **Telefono**
   - **Correo**
   - **Campos extra** (las etiquetas cambian segun la seccion)
   - **Notas**
4. Haz clic en **Guardar**.

![Ventana de crear contacto con los campos del formulario](./imagenes/captura-08-ventana-de-crear-contacto-con-los-campos.png)

### 5.5 Editar un contacto (modo editor)

1. Haz clic en el boton de editar en la tarjeta del contacto.
2. Modifica los campos que necesites.
3. Haz clic en **Guardar**.

### 5.6 Eliminar un contacto (modo editor)

1. Abre la ventana de edicion del contacto.
2. Haz clic en **Eliminar**.
3. Confirma la eliminacion.

### 5.7 Crear una nueva seccion (modo editor)

1. Haz clic en el boton **Nueva seccion**.
2. Introduce el nombre de la nueva seccion.
3. Haz clic en **Crear**.
4. La nueva seccion aparecera como una pestana adicional.

### 5.8 Exportar contactos

Puedes exportar los contactos de la seccion activa en dos formatos:

1. Haz clic en el boton **Excel** para descargar en formato Excel (.xlsx).
2. Haz clic en el boton **PDF** para descargar en formato PDF.

El archivo descargado incluira solo los contactos de la seccion seleccionada.

![Botones de exportar Excel y PDF junto a la cabecera de la seccion](./imagenes/captura-09-botones-de-exportar-excel-y-pdf-junto-a.png)

---

## 6. NAT / LAN2LAN

### 6.1 Ver la tabla NAT

1. Desde el panel principal, haz clic en **Red y Conectividad** (o **NAT LAN2LAN**).
2. En la parte superior aparecen las **tarjetas de rangos** con:
   - Nombre del grupo
   - Rango de IPs (inicio - fin)
   - Barra de progreso (uso del rango)
   - Estadisticas: IPs usadas / libres

![Tarjetas de rangos NAT con barras de progreso de colores (verde, naranja, rojo)](./imagenes/captura-10-tarjetas-de-rangos-nat-con-barras-de-pro.png)

3. Debajo se muestra la tabla con todos los registros NAT:

| Columna        | Que muestra                                    |
|----------------|------------------------------------------------|
| IP Inside      | IP interna                                      |
| IP Outside     | IP externa (puede estar vacia si esta libre)    |
| Nemonico       | Nombre del equipo asociado                      |
| Uso/Servicio   | Para que se usa esta IP                         |
| Ubicacion      | Donde esta el equipo                            |
| Grupo          | Grupo al que pertenece                          |
| Ping           | Si responde a ping (SI/NO)                      |
| Estado         | Estado actual (OCUPADO/LIBRE/COMPROBAR)         |

### Colores de estado

| Estado       | Color    | Significado                                    |
|--------------|----------|------------------------------------------------|
| OCUPADO      | Verde    | IP en uso, con ping activo                     |
| LIBRE        | Sin color| IP disponible (sin IP Outside)                 |
| COMPROBAR    | Rojo     | Tiene IP Outside pero no responde al ping      |

### Colores de ping

| Ping | Color   |
|------|---------|
| SI   | Verde   |
| NO   | Rojo    |
| N/D  | Neutro  |

### 6.2 Filtrar registros

1. Usa los campos de filtro en la parte superior de la tabla:
   - **Buscar** -- Texto libre (busca en IP, nemonico, uso, ubicacion)
   - **Grupo** -- Selecciona un grupo especifico
   - **Estado** -- Filtra por OCUPADO, LIBRE o COMPROBAR
   - **Ping** -- Filtra por SI o NO
2. Haz clic en **Filtrar**.
3. Para quitar los filtros, haz clic en **Limpiar**.

![Barra de filtros con los selectores de grupo, estado y ping](./imagenes/captura-11-barra-de-filtros-con-los-selectores-de-g.png)

### 6.3 Editar un registro NAT (modo editor)

1. Activa el modo editor (ver seccion 3).
2. En la tabla, haz clic en el boton **Editar** del registro.
3. Se abrira una ventana con los datos del registro:
   - **IP Inside** -- Solo lectura (no se puede modificar)
   - **IP Outside** -- Editable
   - **Nemonico** -- Editable
   - **Uso/Servicio** -- Editable
   - **Ubicacion** -- Editable
   - **Grupo** -- Editable
   - **Ping** -- Seleccionar SI o NO
   - **Estado** -- Se calcula automaticamente:
     * Si quitas la IP Outside -> Estado pasa a **LIBRE**
     * Si pones IP Outside y Ping = SI -> Estado pasa a **OCUPADO**
     * Si pones IP Outside y Ping = NO -> Estado pasa a **COMPROBAR**
4. Haz clic en **Guardar**.

![Ventana de edicion de registro NAT mostrando los campos editables y la previsualizacion del estado](./imagenes/captura-12-ventana-de-edicion-de-registro-nat-mostr.png)

> **Nota:** No necesitas elegir el estado manualmente. El sistema lo calcula automaticamente segun los valores de IP Outside y Ping.

### 6.4 Exportar tabla NAT

Puedes exportar los datos de la tabla NAT (respetando los filtros activos):

1. Haz clic en el boton **Excel** para descargar en formato Excel (.xlsx).
2. Haz clic en el boton **PDF** para descargar en formato PDF.

> Los filtros aplicados se mantienen en la exportacion. Si tienes un filtro de grupo activo, solo se exportaran los registros de ese grupo.

---

## Resumen rapido

| Accion                          | Como hacerlo                                           |
|---------------------------------|--------------------------------------------------------|
| Activar modo editor             | Boton Editor + contrasena                              |
| Desactivar modo editor          | Boton Salir                                            |
| Ver enlaces                     | Panel principal > Herramientas                         |
| Crear/editar enlace             | Modo editor + boton + / lapiz                          |
| Ver contactos                   | Panel principal > Contactos > pestana de seccion       |
| Buscar contacto                 | Campo de busqueda (busca en todas las secciones)       |
| Crear contacto                  | Modo editor + Nuevo contacto                           |
| Crear nueva seccion             | Modo editor + Nueva seccion                            |
| Exportar contactos              | Botones Excel / PDF                                    |
| Ver tabla NAT                   | Panel principal > Red y Conectividad                   |
| Filtrar tabla NAT               | Campos de filtro + Filtrar                             |
| Editar registro NAT             | Modo editor + boton Editar en la fila                  |
| Exportar tabla NAT              | Botones Excel / PDF                                    |

---

*Fin del manual -- Modulo Informacion / Ayuda v1.5*
