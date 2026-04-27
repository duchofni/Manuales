# Manual de Usuario -- Módulo Instalaciones

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Módulo**  | Instalaciones                  |
| **Versión** | 1.6                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al módulo Instalaciones](#1-acceder-al-módulo-instalaciones)
2. [Pestana LOGOS (instalaciones de datos)](#2-pestana-logos-instalaciones-de-datos)
3. [Pestana BJ (instalaciones de voz)](#3-pestana-bj-instalaciones-de-voz)
4. [Pestana ATLAS (ordenes de acceso)](#4-pestana-atlas-ordenes-de-acceso)
5. [Pestana Calendario](#5-pestana-calendario)
6. [Pestana Proyectos](#6-pestana-proyectos)

---

## 1. Acceder al módulo Instalaciones

1. Abre la aplicación Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Instalaciones**.
3. Aparecerá la pestana LOGOS por defecto.
4. Usa las **pestañas** de la parte superior para cambiar entre LOGOS, BJ, ATLAS, Calendario y Proyectos.

![Pantalla principal del módulo Instalaciones con las 5 pestanas visibles](./imagenes/captura-01-pantalla-principal-del-modulo-instalacio.png)

---

## 2. Pestana LOGOS (instalaciones de datos)

### 2.1 Vista de instalaciones activas

La pantalla se divide en dos paneles:

- **Panel izquierdo (sidebar):** Lista de tarjetas con las instalaciones activas
- **Panel derecho (detalle):** Información completa de la instalación seleccionada

![Vista split de LOGOS con sidebar de tarjetas a la izquierda y panel de detalle a la derecha](./imagenes/captura-02-vista-split-de-logos-con-sidebar-de-tarj.png)

#### Buscar una instalación

1. Escribe en el campo de **busqueda** de la sidebar.
2. Las tarjetas se filtran en tiempo real mientras escribes.
3. El contador muestra cuantas instalaciones coinciden.

#### Seleccionar una instalación

1. Haz clic en una tarjeta de la sidebar.
2. La tarjeta se resaltara y el detalle se cargara en el panel derecho.

Cada tarjeta muestra:
- **ID SGC** -- Identificador del pedido
- **Centro** -- Nombre del centro
- **Badges de estado** -- Etiquetas de color indicando el estado, si tiene cita, etc.
- Las tarjetas que **ya no aparecen en el último CSV de LOGOS** se muestran con un estilo diferente ("No en LOGOS")

#### Ver el detalle de una instalación

El panel de detalle se divide en secciones:

| Sección             | Contenido                                                  |
|---------------------|-------------------------------------------------------------|
| **Cabecera**        | ID SGC, fecha de importacion, NRI, orden Atlas, badges      |
| **Centro -- BDU**   | Nombre del centro y su horario (datos automaticos de la BDU)|
| **Datos LOGOS**     | Tarea, grupo pendiente, fecha, estado, etc. (solo lectura)  |
| **Datos Indico**    | Responsable, grupo, incidencias LOGOS (solo lectura)         |
| **Gestión CGE**     | Campos editables: proyecto, fecha concertada, observaciones, realizada |

#### Editar los campos de Gestión CGE

1. En la sección **Gestión CGE** del detalle:
   - **Proyecto** -- Selecciona de la lista desplegable
   - **Fecha concertada** -- Haz clic en el campo; se rellenara automáticamente con la fecha y hora actual (puedes modificarla)
   - **Observaciones** -- Escribe texto libre
   - **Realizada** -- Marca la casilla cuando la instalación se haya completado
2. Haz clic en **Guardar cambios**.
3. Si marcas "Realizada", se registrara automáticamente la fecha de realizacion.

![Seccion Gestión CGE con el campo de fecha concertada relleno y el boton Guardar](./imagenes/captura-03-seccion-gestion-cge-con-el-campo-de-fech.png)

### 2.2 Importar CSV de LOGOS

1. Haz clic en el boton **CSV manual** (en la parte superior de la sidebar).
2. Se abrira una ventana emergente.
3. Selecciona el archivo CSV exportado desde LOGOS.
4. Haz clic en **Importar**.
5. El sistema procesara el archivo y mostrara un resumen:
   - Registros nuevos
   - Registros actualizados
   - Registros desaparecidos (ya no están en el CSV)
   - Errores (si los hay)

![Ventana de importacion CSV con el selector de archivo y el boton Importar](./imagenes/captura-04-ventana-de-importacion-csv-con-el-select.png)

### 2.3 Actualizar desde Indico

1. Haz clic en el boton **Actualizar Indico** (en la parte superior de la sidebar).
2. Se abrira una ventana pidiendo credenciales de Indico.
3. Introduce tu usuario y contraseña de Indico.
4. Haz clic en **Actualizar**.
5. El sistema descargara los datos actualizados de Indico y los cruzara con los registros LOGOS.

![Ventana de actualización Indico con campos de usuario y contraseña](./imagenes/captura-05-ventana-de-actualizacion-indico-con-camp.png)

> **Nota:** Las credenciales de Indico no se guardan en el sistema; solo se usan para esa descarga puntual.

### 2.4 Vista de histórico

1. Cambia a la vista **Histórico** (boton en la sidebar).
2. Se mostrara una tabla paginada con todas las instalaciones finalizadas.
3. Usa el buscador para filtrar por ID SGC, poblacion, provincia, administrativo, etc.
4. Navega por las paginas (50 registros por pagina).
5. Haz clic en **Exportar CSV** para descargar el historico.

![Vista de historico con tabla paginada y boton de exportar CSV](./imagenes/captura-06-vista-de-historico-con-tabla-paginada-y.png)

---

## 3. Pestana BJ (instalaciones de voz)

### 3.1 Vista de pedidos activos

La pantalla tiene el mismo formato split que LOGOS:
- **Sidebar** con tarjetas de pedidos BJ activos
- **Panel de detalle** a la derecha

Cada tarjeta muestra: número de pedido, centro, MIDAS, BJ y area sanitaria.

#### Buscar un pedido

1. Escribe en el campo de busqueda de la sidebar para filtrar.

#### Ver el detalle de un pedido

1. Haz clic en una tarjeta para ver el detalle.
2. El detalle incluye:

| Sección          | Contenido                                                  |
|------------------|-------------------------------------------------------------|
| **Cabecera**     | Número de pedido, badges (Finalizado, Cita, Activo, En tuberias) |
| **Centro -- BDU**| Centro con autocompletado, horario y centralita automaticos  |
| **Referencias**  | Pedido, MIDAS, BJ, empresa, motivo                          |
| **Fechas**       | Fecha entrada, fecha coordinada, fecha finalizado, checkbox Finalizado |
| **Observaciones**| Texto libre                                                  |
| **Tuberias**     | Datos de tuberias BJ (solo lectura, si existen)              |

#### Editar campos

1. Modifica los campos que necesites (fechas, observaciones, etc.).
2. Para las fechas: haz clic en el campo vacío y se rellenará con la fecha actual.
3. Marca **Finalizado** cuando el pedido este completado.
4. Haz clic en **Guardar**.

![Detalle de un pedido BJ con los campos editables y el boton Guardar](./imagenes/captura-07-detalle-de-un-pedido-bj-con-los-campos-e.png)

### 3.2 Crear un nuevo pedido BJ

1. Haz clic en el boton **Nuevo pedido** (en la parte superior de la sidebar).
2. Se abrira el formulario de detalle vacio.
3. Busca y selecciona el **centro** con el autocompletado (el horario y centralita se rellenaran automáticamente).
4. Rellena los campos: pedido, MIDAS, BJ, area sanitaria, motivo, empresa, fechas, observaciones.
5. Haz clic en **Crear**.

![Formulario de nuevo pedido BJ con campos vacios y el boton Crear](./imagenes/captura-08-formulario-de-nuevo-pedido-bj-con-campos.png)

### 3.3 Ver las tuberias BJ

1. Haz clic en el boton **Tuberias** (en la parte superior de la sidebar).
2. Se abrira una ventana con la tabla de tuberias BJ.
3. Columnas: peticion, tipo obra, tipo orden, módulo, RAI, estado, jalon, descripción, responsable.
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
3. Exportación CSV disponible.

---

## 4. Pestana ATLAS (ordenes de acceso)

### 4.1 Vista de ordenes activas

Mismo formato split (sidebar + detalle) que LOGOS y BJ.

Las tarjetas muestran: orden Atlas, tipo de orden, badges de estado.

#### Ver el detalle de una orden

| Sección          | Contenido                                                     |
|------------------|----------------------------------------------------------------|
| **Cabecera**     | Orden Atlas, badges (Realizada, estado, ID SGC si hay)        |
| **Centro -- BDU**| Administrativo editable; al guardar, el centro se recalcula    |
| **Datos ATLAS**  | Tipo orden, estado, origen, destino, fechas, etc. (solo lectura)|
| **Datos Indico** | Grupo operativo, jalon, incidencia (cruzado por orden Atlas)   |
| **Gestión CGE**  | Proyecto, fecha concertada, observaciones, realizada (editable)|

#### Editar los campos

1. Modifica los campos editables (proyecto, fecha concertada, observaciones, realizada).
2. Si necesitas cambiar el **administrativo**, escribe el nuevo número y al guardar se recalculara automáticamente el centro asociado.
3. Haz clic en **Guardar**.

![Detalle de una orden ATLAS con los campos editables](./imagenes/captura-09-detalle-de-una-orden-atlas-con-los-campo.png)

### 4.2 Importar CSV(s) de ATLAS

1. Haz clic en el boton **Importar CSV(s)**.
2. Se abrira una ventana de selección de archivos.
3. Puedes seleccionar **uno o varios archivos** a la vez (formatos: .xls, .csv, .htm, .html).
4. Haz clic en **Importar**.
5. El sistema procesara los archivos, cruzara datos con LOGOS y con la BDU, y mostrara un resumen.

![Ventana de importacion de CSV de ATLAS con seleccion múltiple de archivos](./imagenes/captura-10-ventana-de-importacion-de-csv-de-atlas-c.png)

### 4.3 Vista de histórico ATLAS

1. Cambia a la vista **Historico**.
2. Tabla paginada con busqueda y exportación CSV.

---

## 5. Pestaña Calendario

El calendario muestra las **instalaciones programadas** (con fecha concertada) de los tres módulos (LOGOS, BJ, ATLAS) en una única vista.

### 5.1 Vista mensual

1. Haz clic en la pestana **Calendario**.
2. Por defecto se muestra la vista de **mes**.
3. Cada día del calendario muestra los eventos programados como botones de colores:
   - **Azul** -- Instalaciones LOGOS
   - **Verde** -- Instalaciones BJ
   - **Ambar** -- Ordenes ATLAS
4. Si un día tiene muchos eventos, aparecerá un boton **"+N más"** para ver todos.
5. Pasa el raton por encima de un evento para ver un **tooltip** con los detalles (centro, orden, proyecto, responsable, observaciones).

![Calendario en vista mensual con eventos de colores y tooltip visible](./imagenes/captura-11-calendario-en-vista-mensual-con-eventos.png)

### 5.2 Vista semanal

1. Haz clic en el boton para cambiar a vista de **semana**.
2. Se mostrara una tabla con las columnas: Fecha, Hora, Módulo, Orden, Centro, Proyecto, Responsable.
3. Los eventos aparecen ordenados cronologicamente.

![Calendario en vista semanal mostrando la tabla con eventos](./imagenes/captura-12-calendario-en-vista-semanal-mostrando-la.png)

### 5.3 Navegar entre periodos

- **Anterior** -- Ir al mes/semana anterior
- **Siguiente** -- Ir al mes/semana siguiente
- **Hoy** -- Volver al periodo actual

### 5.4 Exportar semana

1. Haz clic en el boton **Exportar semana**.
2. Se abrira una nueva ventana con una tabla imprimible de la semana.
3. Columnas: Módulo, Centro, Horario, Orden, Proyecto, Tipo, Referencia, Fecha concertada, Responsable, Observaciones.
4. Usa los botones:
   - **Copiar tabla** -- Copia la tabla al portapapeles
   - **Imprimir/PDF** -- Abre el dialogo de impresion del navegador (puedes guardar como PDF)
   - **Cerrar** -- Cierra la ventana

![Ventana de exportacion semanal con la tabla y los botones Copiar, Imprimir y Cerrar](./imagenes/captura-13-ventana-de-exportacion-semanal-con-la-ta.png)

---

## 6. Pestana Proyectos

La pestana Proyectos muestra los proyectos de despliegue del SERGAS. Al hacer clic aparece una pantalla de selección con tarjetas de proyectos.

### 6.1 Proyectos finalizados (solo consulta)

Estos proyectos ya están completados y se pueden consultar pero no editar:

| Proyecto                              | Descripción                              |
|---------------------------------------|------------------------------------------|
| **FlexWAN 2024-2027**                 | 206 centros, migración FlexWAN           |
| **Upgrades Sedes 2024-2027**          | 349 sedes, actualización de equipos      |
| **Upgrades Sedes Criticas 2024-2027** | 30 sedes criticas                        |
| **Renovación Terminales ALE20**       | 250 centros, 1.703 extensiones           |

Para cada proyecto puedes:

1. **Ver la tabla** -- Haz clic en el proyecto para ver la tabla completa.
2. **Filtrar** -- Usa los filtros disponibles (busqueda, provincia, fase, tipo de línea, etc.) para encontrar un centro concreto.
3. **Ver estadisticas** -- Haz clic en el boton de estadisticas para ver gráficos de progreso (donuts y barras).
4. **Exportar** -- Descarga los datos en formato CSV.

![Tabla de un proyecto con filtros y boton de estadisticas](./imagenes/captura-14-tabla-de-un-proyecto-con-filtros-y-boton.png)

![Pantalla de estadisticas con gráficos donut y barras de progreso](./imagenes/captura-15-pantalla-de-estadisticas-con-graficos-do.png)

### 6.2 Tensiometros (proyecto activo -- editable)

Este es el único proyecto activo que permite edición directa en la tabla.

#### Ver la tabla de tensiometros

1. Haz clic en **Dispositivos Control de Tension / Tensiometros**.
2. Se mostrara una tabla con todos los centros del proyecto.
3. En la parte superior hay una **barra de progreso** con:
   - Total de centros
   - Realizados
   - Pendientes
   - Porcentaje de avance

![Barra de progreso de tensiometros mostrando el porcentaje completado](./imagenes/captura-16-barra-de-progreso-de-tensiometros-mostra.png)

#### Filtrar la tabla

Usa los filtros de la parte superior:
- **Búsqueda** -- Por nombre de centro, area sanitaria o GDIA
- **Provincia** -- Selecciona una provincia
- **Estado** -- Realizado o Pendiente

#### Rellenar los datos de un tensiometro

Cada fila de la tabla tiene campos editables:

| Campo              | Descripción                                      |
|--------------------|--------------------------------------------------|
| **Instalado**      | Casilla para marcar si el DCT esta instalado     |
| **N. Largo**       | Número largo del dispositivo                     |
| **N. Corto**       | Extensión corta del dispositivo                  |
| **ICC**            | Número de ICC del dispositivo                    |
| **Area sanitaria** | Area sanitaria del centro                        |
| **GDIA**           | Código GDIA                                      |
| **Fecha realizada**| Fecha en que se instalo                          |
| **Comentarios**    | Observaciones                                    |

#### Guardar los cambios

1. Modifica los campos que necesites en la fila.
2. Haz clic en el boton **Guardar** de esa fila.
3. Los contadores de la barra de progreso se actualizaran automaticamente.

![Fila de la tabla de tensiometros con campos editables y boton Guardar](./imagenes/captura-17-fila-de-la-tabla-de-tensiometros-con-cam.png)

> **Nota:** Un centro se considera "realizado" cuando tiene marcado Instalado (DCT) **y** tiene rellenos los campos N. Largo, N. Corto e ICC.

#### Ver estadisticas de tensiometros

1. Haz clic en el boton de **estadísticas**.
2. Se mostraran gráficos con:
   - Progreso por semana
   - Progreso por mes
   - Distribución por provincia (proporcional)
   - Distribución por tipo de sede

![Estadisticas de tensiometros con gráficos de progreso por semana y por provincia](./imagenes/captura-18-estadisticas-de-tensiometros-con-grafico.png)

---

## Resumen rápido

| Acción                              | Como hacerlo                                          |
|-------------------------------------|-------------------------------------------------------|
| Buscar instalación (LOGOS/BJ/ATLAS) | Escribir en el buscador de la sidebar                  |
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

*Fin del manual -- Módulo Instalaciones v1.6*
