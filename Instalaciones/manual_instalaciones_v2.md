# Manual de Usuario -- Modulo Instalaciones

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Instalaciones                  |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al modulo Instalaciones](#1-acceder-al-modulo-instalaciones)
2. [Pestana LOGOS (instalaciones de datos)](#2-pestana-logos-instalaciones-de-datos)
3. [Pestana BJ (instalaciones de voz)](#3-pestana-bj-instalaciones-de-voz)
4. [Pestana ATLAS (ordenes de acceso)](#4-pestana-atlas-ordenes-de-acceso)
5. [Pestana Calendario](#5-pestana-calendario)
6. [Pestana Proyectos](#6-pestana-proyectos)

---

## 1. Acceder al modulo Instalaciones

1. Abre la aplicacion Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Instalaciones**.
3. Aparecera la pestana LOGOS por defecto.
4. Usa las **pestanas** de la parte superior para cambiar entre LOGOS, BJ, ATLAS, Calendario y Proyectos.

[CAPTURA: Pantalla principal del modulo Instalaciones con las 5 pestanas visibles]

---

## 2. Pestana LOGOS (instalaciones de datos)

### 2.1 Vista de instalaciones activas

La pantalla se divide en dos paneles:

- **Panel izquierdo (sidebar):** Lista de tarjetas con las instalaciones activas
- **Panel derecho (detalle):** Informacion completa de la instalacion seleccionada

[CAPTURA: Vista split de LOGOS con sidebar de tarjetas a la izquierda y panel de detalle a la derecha]

#### Buscar una instalacion

1. Escribe en el campo de **busqueda** de la sidebar.
2. Las tarjetas se filtran en tiempo real mientras escribes.
3. El contador muestra cuantas instalaciones coinciden.

#### Seleccionar una instalacion

1. Haz clic en una tarjeta de la sidebar.
2. La tarjeta se resaltara y el detalle se cargara en el panel derecho.

Cada tarjeta muestra:
- **ID SGC** -- Identificador del pedido
- **Centro** -- Nombre del centro
- **Badges de estado** -- Etiquetas de color indicando el estado, si tiene cita, etc.
- Las tarjetas que **ya no aparecen en el ultimo CSV de LOGOS** se muestran con un estilo diferente ("No en LOGOS")

#### Ver el detalle de una instalacion

El panel de detalle se divide en secciones:

| Seccion             | Contenido                                                  |
|---------------------|-------------------------------------------------------------|
| **Cabecera**        | ID SGC, fecha de importacion, NRI, orden Atlas, badges      |
| **Centro -- BDU**   | Nombre del centro y su horario (datos automaticos de la BDU)|
| **Datos LOGOS**     | Tarea, grupo pendiente, fecha, estado, etc. (solo lectura)  |
| **Datos Indico**    | Responsable, grupo, incidencias LOGOS (solo lectura)         |
| **Gestion CGE**     | Campos editables: proyecto, fecha concertada, observaciones, realizada |

#### Editar los campos de Gestion CGE

1. En la seccion **Gestion CGE** del detalle:
   - **Proyecto** -- Selecciona de la lista desplegable
   - **Fecha concertada** -- Haz clic en el campo; se rellenara automaticamente con la fecha y hora actual (puedes modificarla)
   - **Observaciones** -- Escribe texto libre
   - **Realizada** -- Marca la casilla cuando la instalacion se haya completado
2. Haz clic en **Guardar cambios**.
3. Si marcas "Realizada", se registrara automaticamente la fecha de realizacion.

[CAPTURA: Seccion Gestion CGE con el campo de fecha concertada relleno y el boton Guardar]

### 2.2 Importar CSV de LOGOS

1. Haz clic en el boton **CSV manual** (en la parte superior de la sidebar).
2. Se abrira una ventana emergente.
3. Selecciona el archivo CSV exportado desde LOGOS.
4. Haz clic en **Importar**.
5. El sistema procesara el archivo y mostrara un resumen:
   - Registros nuevos
   - Registros actualizados
   - Registros desaparecidos (ya no estan en el CSV)
   - Errores (si los hay)

[CAPTURA: Ventana de importacion CSV con el selector de archivo y el boton Importar]

### 2.3 Actualizar desde Indico

1. Haz clic en el boton **Actualizar Indico** (en la parte superior de la sidebar).
2. Se abrira una ventana pidiendo credenciales de Indico.
3. Introduce tu usuario y contrasena de Indico.
4. Haz clic en **Actualizar**.
5. El sistema descargara los datos actualizados de Indico y los cruzara con los registros LOGOS.

[CAPTURA: Ventana de actualizacion Indico con campos de usuario y contrasena]

> **Nota:** Las credenciales de Indico no se guardan en el sistema; solo se usan para esa descarga puntual.

### 2.4 Vista de historico

1. Cambia a la vista **Historico** (boton en la sidebar).
2. Se mostrara una tabla paginada con todas las instalaciones (activas e historicas).
3. Usa el buscador para filtrar por ID SGC, poblacion, provincia, administrativo, etc.
4. Navega por las paginas (50 registros por pagina).
5. Haz clic en **Exportar CSV** para descargar el historico.

[CAPTURA: Vista de historico con tabla paginada y boton de exportar CSV]

---

## 3. Pestana BJ (instalaciones de voz)

### 3.1 Vista de pedidos activos

La pantalla tiene el mismo formato split que LOGOS:
- **Sidebar** con tarjetas de pedidos BJ activos
- **Panel de detalle** a la derecha

Cada tarjeta muestra: numero de pedido, centro, MIDAS, BJ y area sanitaria.

#### Buscar un pedido

1. Escribe en el campo de busqueda de la sidebar para filtrar.

#### Ver el detalle de un pedido

1. Haz clic en una tarjeta para ver el detalle.
2. El detalle incluye:

| Seccion          | Contenido                                                  |
|------------------|-------------------------------------------------------------|
| **Cabecera**     | Numero de pedido, badges (Finalizado, Cita, Activo, En tuberias) |
| **Centro -- BDU**| Centro con autocompletado, horario y centralita automaticos  |
| **Referencias**  | Pedido, MIDAS, BJ, empresa, motivo                          |
| **Fechas**       | Fecha entrada, fecha coordinada, fecha finalizado, checkbox Finalizado |
| **Observaciones**| Texto libre                                                  |
| **Tuberias**     | Datos de tuberias BJ (solo lectura, si existen)              |

#### Editar campos

1. Modifica los campos que necesites (fechas, observaciones, etc.).
2. Para las fechas: haz clic en el campo vacio y se rellenara con la fecha actual.
3. Marca **Finalizado** cuando el pedido este completado.
4. Haz clic en **Guardar**.

[CAPTURA: Detalle de un pedido BJ con los campos editables y el boton Guardar]

### 3.2 Crear un nuevo pedido BJ

1. Haz clic en el boton **Nuevo pedido** (en la parte superior de la sidebar).
2. Se abrira el formulario de detalle vacio.
3. Busca y selecciona el **centro** con el autocompletado (el horario y centralita se rellenaran automaticamente).
4. Rellena los campos: pedido, MIDAS, BJ, area sanitaria, motivo, empresa, fechas, observaciones.
5. Haz clic en **Crear**.

[CAPTURA: Formulario de nuevo pedido BJ con campos vacios y el boton Crear]

### 3.3 Ver las tuberias BJ

1. Haz clic en el boton **Tuberias** (en la parte superior de la sidebar).
2. Se abrira una ventana con la tabla de tuberias BJ.
3. Columnas: peticion, tipo obra, tipo orden, modulo, RAI, estado, jalon, descripcion, responsable.
4. Usa los botones:
   - **Copiar tabla** -- Copia la tabla al portapapeles
   - **Cerrar** -- Cierra la ventana

### 3.4 Actualizar tuberias desde Indico

1. Haz clic en el boton **Actualizar tuberias**.
2. Introduce tus credenciales de Indico.
3. Haz clic en **Actualizar**.
4. Los datos de tuberias se descargaran y actualizaran automaticamente.

### 3.5 Vista de historico BJ

1. Cambia a la vista **Historico**.
2. Tabla paginada con busqueda por pedido, MIDAS, BJ, centro, area, motivo, empresa.
3. Exportacion CSV disponible.

---

## 4. Pestana ATLAS (ordenes de acceso)

### 4.1 Vista de ordenes activas

Mismo formato split (sidebar + detalle) que LOGOS y BJ.

Las tarjetas muestran: orden Atlas, tipo de orden, badges de estado.

#### Ver el detalle de una orden

| Seccion          | Contenido                                                     |
|------------------|----------------------------------------------------------------|
| **Cabecera**     | Orden Atlas, badges (Realizada, estado, ID SGC si hay)        |
| **Centro -- BDU**| Administrativo editable; al guardar, el centro se recalcula    |
| **Datos ATLAS**  | Tipo orden, estado, origen, destino, fechas, etc. (solo lectura)|
| **Datos Indico** | Grupo operativo, jalon, incidencia (cruzado por orden Atlas)   |
| **Gestion CGE**  | Proyecto, fecha concertada, observaciones, realizada (editable)|

#### Editar los campos

1. Modifica los campos editables (proyecto, fecha concertada, observaciones, realizada).
2. Si necesitas cambiar el **administrativo**, escribe el nuevo numero y al guardar se recalculara automaticamente el centro asociado.
3. Haz clic en **Guardar**.

[CAPTURA: Detalle de una orden ATLAS con los campos editables]

### 4.2 Importar CSV(s) de ATLAS

1. Haz clic en el boton **Importar CSV(s)**.
2. Se abrira una ventana de seleccion de archivos.
3. Puedes seleccionar **uno o varios archivos** a la vez (formatos: .xls, .csv, .htm, .html).
4. Haz clic en **Importar**.
5. El sistema procesara los archivos, cruzara datos con LOGOS y con la BDU, y mostrara un resumen.

[CAPTURA: Ventana de importacion de CSV de ATLAS con seleccion multiple de archivos]

### 4.3 Vista de historico ATLAS

1. Cambia a la vista **Historico**.
2. Tabla paginada con busqueda y exportacion CSV.

---

## 5. Pestana Calendario

El calendario muestra las **instalaciones programadas** (con fecha concertada) de los tres modulos (LOGOS, BJ, ATLAS) en una unica vista.

### 5.1 Vista mensual

1. Haz clic en la pestana **Calendario**.
2. Por defecto se muestra la vista de **mes**.
3. Cada dia del calendario muestra los eventos programados como botones de colores:
   - **Azul** -- Instalaciones LOGOS
   - **Verde** -- Instalaciones BJ
   - **Ambar** -- Ordenes ATLAS
4. Si un dia tiene muchos eventos, aparecera un boton **"+N mas"** para ver todos.
5. Pasa el raton por encima de un evento para ver un **tooltip** con los detalles (centro, orden, proyecto, responsable, observaciones).

[CAPTURA: Calendario en vista mensual con eventos de colores y tooltip visible]

### 5.2 Vista semanal

1. Haz clic en el boton para cambiar a vista de **semana**.
2. Se mostrara una tabla con las columnas: Fecha, Hora, Modulo, Orden, Centro, Proyecto, Responsable.
3. Los eventos aparecen ordenados cronologicamente.

[CAPTURA: Calendario en vista semanal mostrando la tabla con eventos]

### 5.3 Navegar entre periodos

- **Anterior** -- Ir al mes/semana anterior
- **Siguiente** -- Ir al mes/semana siguiente
- **Hoy** -- Volver al periodo actual

### 5.4 Exportar semana

1. Haz clic en el boton **Exportar semana**.
2. Se abrira una nueva ventana con una tabla imprimible de la semana.
3. Columnas: Modulo, Centro, Horario, Orden, Proyecto, Tipo, Referencia, Fecha concertada, Responsable, Observaciones.
4. Usa los botones:
   - **Copiar tabla** -- Copia la tabla al portapapeles
   - **Imprimir/PDF** -- Abre el dialogo de impresion del navegador (puedes guardar como PDF)
   - **Cerrar** -- Cierra la ventana

[CAPTURA: Ventana de exportacion semanal con la tabla y los botones Copiar, Imprimir y Cerrar]

---

## 6. Pestana Proyectos

La pestana Proyectos muestra los proyectos de despliegue del SERGAS. Al hacer clic aparece una pantalla de seleccion con tarjetas de proyectos.

### 6.1 Proyectos finalizados (solo consulta)

Estos proyectos ya estan completados y se pueden consultar pero no editar:

| Proyecto                              | Descripcion                              |
|---------------------------------------|------------------------------------------|
| **FlexWAN 2024-2027**                 | 206 centros, migracion FlexWAN           |
| **Upgrades Sedes 2024-2027**          | 349 sedes, actualizacion de equipos      |
| **Upgrades Sedes Criticas 2024-2027** | 30 sedes criticas                        |
| **Renovacion Terminales ALE20**       | 250 centros, 1.703 extensiones           |

Para cada proyecto puedes:

1. **Ver la tabla** -- Haz clic en el proyecto para ver la tabla completa.
2. **Filtrar** -- Usa los filtros disponibles (busqueda, provincia, fase, tipo de linea, etc.) para encontrar un centro concreto.
3. **Ver estadisticas** -- Haz clic en el boton de estadisticas para ver graficos de progreso (donuts y barras).
4. **Exportar** -- Descarga los datos en formato CSV.

[CAPTURA: Tabla de un proyecto con filtros y boton de estadisticas]

[CAPTURA: Pantalla de estadisticas con graficos donut y barras de progreso]

### 6.2 Tensiometros (proyecto activo -- editable)

Este es el unico proyecto activo que permite edicion directa en la tabla.

#### Ver la tabla de tensiometros

1. Haz clic en **Dispositivos Control de Tension / Tensiometros**.
2. Se mostrara una tabla con todos los centros del proyecto.
3. En la parte superior hay una **barra de progreso** con:
   - Total de centros
   - Realizados
   - Pendientes
   - Porcentaje de avance

[CAPTURA: Barra de progreso de tensiometros mostrando el porcentaje completado]

#### Filtrar la tabla

Usa los filtros de la parte superior:
- **Busqueda** -- Por nombre de centro, area sanitaria o GDIA
- **Provincia** -- Selecciona una provincia
- **Estado** -- Realizado o Pendiente

#### Rellenar los datos de un tensiometro

Cada fila de la tabla tiene campos editables:

| Campo              | Descripcion                                      |
|--------------------|--------------------------------------------------|
| **Instalado**      | Casilla para marcar si el DCT esta instalado     |
| **N. Largo**       | Numero largo del dispositivo                     |
| **N. Corto**       | Extension corta del dispositivo                  |
| **ICC**            | Numero de ICC del dispositivo                    |
| **Area sanitaria** | Area sanitaria del centro                        |
| **GDIA**           | Codigo GDIA                                      |
| **Fecha realizada**| Fecha en que se instalo                          |
| **Comentarios**    | Observaciones                                    |

#### Guardar los cambios

1. Modifica los campos que necesites en la fila.
2. Haz clic en el boton **Guardar** de esa fila.
3. Los contadores de la barra de progreso se actualizaran automaticamente.

[CAPTURA: Fila de la tabla de tensiometros con campos editables y boton Guardar]

> **Nota:** Un centro se considera "realizado" cuando tiene marcado Instalado (DCT) **y** tiene rellenos los campos N. Largo, N. Corto e ICC.

#### Ver estadisticas de tensiometros

1. Haz clic en el boton de **estadisticas**.
2. Se mostraran graficos con:
   - Progreso por semana
   - Progreso por mes
   - Distribucion por provincia (proporcional)
   - Distribucion por tipo de sede

[CAPTURA: Estadisticas de tensiometros con graficos de progreso por semana y por provincia]

---

## Resumen rapido

| Accion                              | Como hacerlo                                          |
|-------------------------------------|-------------------------------------------------------|
| Buscar instalacion (LOGOS/BJ/ATLAS) | Escribir en el buscador de la sidebar                  |
| Ver detalle                         | Clic en la tarjeta de la sidebar                       |
| Editar campos CGE                   | Modificar campos en el panel de detalle + Guardar      |
| Importar CSV (LOGOS)                | Boton "CSV manual" + seleccionar archivo               |
| Importar CSV(s) (ATLAS)             | Boton "Importar CSV(s)" + seleccionar archivos         |
| Actualizar Indico                   | Boton "Actualizar Indico" + credenciales               |
| Crear nuevo pedido BJ               | Boton "Nuevo pedido" en la sidebar de BJ               |
| Ver tuberias BJ                     | Boton "Tuberias" en la sidebar de BJ                   |
| Ver historico                       | Cambiar a vista "Historico" en cualquier pestana       |
| Exportar CSV historico              | Boton "Exportar CSV" en la vista de historico          |
| Ver calendario                      | Pestana Calendario + elegir vista mes o semana         |
| Exportar semana                     | Boton "Exportar semana" en el calendario               |
| Ver proyectos                       | Pestana Proyectos + seleccionar proyecto               |
| Editar tensiometro                  | Modificar campos en la fila + boton Guardar            |
| Ver estadisticas de proyecto        | Boton de estadisticas en cada proyecto                 |
| Marcar fecha concertada             | Clic en campo vacio (se rellena con fecha actual)      |

---

*Fin del manual -- Modulo Instalaciones v1.5*
