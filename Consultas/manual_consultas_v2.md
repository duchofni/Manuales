# Manual de Usuario -- Módulo Consultas

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Módulo**  | Consultas                      |
| **Versión** | 1.6                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al módulo Consultas](#1-acceder-al-módulo-consultas)
2. [Seleccionar una consulta](#2-seleccionar-una-consulta)
3. [Usar el buscador](#3-usar-el-buscador)
4. [Ordenar columnas](#4-ordenar-columnas)
5. [Navegar por las paginas](#5-navegar-por-las-paginas)
6. [Exportar datos (CSV, PDF, Excel)](#6-exportar-datos-csv-pdf-excel)
7. [Ver estadísticas de una consulta](#7-ver-estadísticas-de-una-consulta)
8. [Control de Cambios](#8-control-de-cambios)

---

## 1. Acceder al módulo Consultas

1. Abre la aplicación Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Consultas**.
3. Aparecerá la pantalla principal con tarjetas grandes, una por cada consulta disponible.

![Pantalla principal del módulo Consultas mostrando las tarjetas de las consultas disponibles](./imagenes/captura-01-pantalla-principal-del-modulo-consultas.png)

---

## 2. Seleccionar una consulta

1. En la pantalla principal, haz clic en la tarjeta de la consulta que necesites.
2. Las consultas disponibles son:

| Consulta                             | Que muestra                                                    |
|--------------------------------------|----------------------------------------------------------------|
| Centros con Dispositivo de Tension   | Centros que tienen tensiometro (DCT)                           |
| Líneas Activas con EDC              | Líneas de datos activas con su equipo                          |
| Mantenimiento Equipos Satec          | Equipos Teldat, Cisco y Fortigate para mantenimiento           |
| Líneas Datos                         | Todas las líneas de datos activas de centros abiertos          |
| Líneas Voz                           | Todas las líneas de voz activas                                |
| Equipos Voz                          | Todos los equipos de voz activos                               |
| Equipos 2.o Nivel                    | Todos los EDCs de segundo nivel activos                        |
| Diversificacion                      | Estado de diversificacion de cada centro                       |
| Circuitos por Nodo                   | Líneas que pasan por un nodo concreto                          |
| Control de Cambios                   | Registro de cambios e incidencias                              |

3. Una vez seleccionada, la tabla de resultados se mostrara con todos los datos.
4. En la parte superior aparecerá una barra de pestanas para cambiar rápidamente entre consultas sin volver al menu.

![Barra de pestanas (pills) con la consulta activa resaltada y la tabla de resultados debajo](./imagenes/captura-02-barra-de-pestanas-pills-con-la-consulta.png)

### Caso especial: Circuitos por Nodo

Esta consulta requiere un paso adicional:

1. Al seleccionarla, aparecerá un campo de busqueda.
2. Escribe el nombre del nodo (mínimo 3 caracteres).
3. Pulsa **Enter** o haz clic en **Buscar**.
4. Se mostraran todas las líneas que pasan por ese nodo.
5. Los nombres de nodo en los resultados son enlaces: puedes hacer clic en ellos para ver los circuitos de otro nodo.

![Formulario de busqueda por nodo con un ejemplo de resultado](./imagenes/captura-03-formulario-de-busqueda-por-nodo-con-un-e.png)

---

## 3. Usar el buscador

1. En la barra de herramientas de cualquier consulta, localiza el campo de **busqueda** (a la izquierda).
2. Escribe el texto que quieras buscar (mínimo **3 caracteres**).
3. La tabla se filtrara automáticamente, mostrando solo las filas que contengan ese texto en cualquier columna.
4. El campo se resaltara en azul cuando hay un filtro activo.
5. Para limpiar la busqueda, haz clic en la **X** junto al campo de busqueda.

![Barra de herramientas con el buscador activo (resaltado en azul) y la X para limpiar](./imagenes/captura-04-barra-de-herramientas-con-el-buscador-ac.png)

> **Nota:** La busqueda se realiza en todas las columnas a la vez. Por ejemplo, si escribes "Pontevedra", encontrara tanto centros en esa provincia como cualquier otro campo que contenga ese texto.

---

## 4. Ordenar columnas

1. Haz clic en la cabecera de cualquier columna de la tabla.
2. Los datos se ordenaran de forma ascendente (A-Z o menor a mayor).
3. Haz clic de nuevo en la misma cabecera para invertir el orden (Z-A o mayor a menor).
4. La ordenacion funciona tanto con texto como con numeros.

![Tabla con una cabecera de columna resaltada indicando que se puede ordenar](./imagenes/captura-05-tabla-con-una-cabecera-de-columna-resalt.png)

---

## 5. Navegar por las paginas

Las consultas muestran **50 registros por pagina**. Si hay más datos, aparecerá un paginador en la parte inferior de la tabla.

1. Usa los botones numerados para ir a una pagina concreta.
2. Usa las flechas **<** y **>** para avanzar o retroceder una pagina.
3. Usa los botones de principio y fin para ir a la primera o última pagina.
4. Debajo del paginador veras la informacion: "Pagina X de Y -- mostrando N-M de Total".

![Paginador mostrando botones de pagina y la información de registros](./imagenes/captura-06-paginador-mostrando-botones-de-pagina-y.png)

> **Nota:** Si tienes una busqueda activa, la paginacion se aplica sobre los resultados filtrados.

---

## 6. Exportar datos (CSV, PDF, Excel)

Puedes exportar los datos de cualquier consulta en tres formatos:

1. En la barra de herramientas, localiza los botones **CSV**, **PDF** y **Excel** (a la derecha).
2. Haz clic en el formato que prefieras:

| Formato  | Uso recomendado                                                    |
|----------|--------------------------------------------------------------------|
| **CSV**  | Para abrir en cualquier programa de hojas de calculo               |
| **PDF**  | Para imprimir o enviar como documento con formato fijo             |
| **Excel**| Para trabajar con los datos en Excel (formato nativo, con estilos) |

3. El archivo se descargara automaticamente.

![Barra de herramientas mostrando los tres botones de exportacion (CSV, PDF, Excel)](./imagenes/captura-07-barra-de-herramientas-mostrando-los-tres.png)

> **Nota:** Si tienes una busqueda activa, se exportaran solo los datos filtrados, no todos los registros.

### Particularidad de la consulta Diversificacion

En la exportacion a Excel de esta consulta cada centro aparece en una sola fila, con la columna **Diversificacion** coloreada según su estado:

| Estado                                       | Color de fondo  |
|----------------------------------------------|-----------------|
| Div. TOTAL (central)                         | Verde oscuro    |
| Div. TOTAL (equipo central)                  | Verde claro     |
| Div. PARCIAL (central)                       | Azul oscuro     |
| Div. PARCIAL (equipo central)                | Azul claro      |
| Div. PARCIAL (equipo central + tecnología)   | Naranja         |
| Div. PARCIAL (Tarjeta)                       | Amarillo        |
| Div. PARCIAL (Tarjeta + tecnología)          | Naranja oscuro  |
| Div. PARCIAL (EDC)                           | Gris            |
| No diversificado                             | Rojo            |

---

## 7. Ver estadísticas de una consulta

Casi todas las consultas (todas salvo **Control de Cambios**) tienen una vista de estadísticas con KPIs y gráficos resumen.

1. Abre la consulta que te interese.
2. En la barra de herramientas, a la derecha de los botones de exportación, haz clic en **📊 Estadísticas**.
3. Se cargara una pagina con:
   - **KPIs** en la cabecera (totales, distintos, etc., depende de la consulta).
   - **Donut + barras** por categoría: por tipo, por provincia, por modelo, por nodo, etc., según la consulta.
4. Para volver a la tabla, haz clic en **← Volver a tabla** (arriba a la derecha).

![Botón "📊 Estadísticas" en la barra de herramientas](./imagenes/captura-12-boton-estadisticas-en-la-barra-de-herramientas.png)

![Vista de estadísticas con KPIs, donut y barras](./imagenes/captura-13-vista-de-estadisticas-con-kpis-y-graficos.png)

> **Nota:** El botón solo aparece si la consulta tiene estadísticas disponibles. En **Control de Cambios** no aparece.

### Particularidad de Diversificacion

Las estadísticas de Diversificacion incluyen además:

- **5 KPIs**: Centros totales, Diversificados, PARCIAL (Tarjeta), No diversificados, % Diversificación.
- **Leyenda con los 9 estados** y sus colores (los mismos que se usan en la tabla y en el Excel).
- **Barras apiladas** por TipoCentro y por Provincia, donde cada segmento de la barra representa un estado de diversificación.

![Estadísticas de Diversificacion: KPIs, leyenda con 9 estados y barras apiladas](./imagenes/captura-14-estadisticas-de-diversificacion-con-leyenda-9-estados.png)

---

## 8. Control de Cambios

La consulta **Control de Cambios** tiene funcionalidades adicionales de edicion. Se utiliza para registrar cambios e incidencias y hacer seguimiento de su solucion.

### 8.1 Ver el registro de cambios (modo lectura)

1. Selecciona **Control de Cambios** en el menu de consultas.
2. Veras una tabla con las columnas:
   - **Tipo** -- Tipo de cambio o incidencia
   - **Fecha** -- Cuando se registro
   - **Versión** -- Versión afectada
   - **Descripción** -- Detalle del cambio
   - **Solucion** -- Solucion aplicada (puede estar vacio si aun no se ha resuelto)
   - **Autor** -- Quien lo registro
   - **Corregido** -- Indicador Si (verde) o No (rojo)

![Tabla de Control de Cambios en modo lectura con las columnas visibles](./imagenes/captura-08-tabla-de-control-de-cambios-en-modo-lect.png)

### 8.2 Activar el modo editor

Para poder editar la solucion o marcar como corregido, necesitas activar el modo editor:

1. Haz clic en el boton **Activar edición** (en la barra de herramientas).
2. Aparecerá una ventana pidiendo la contraseña de edicion.
3. Introduce la contraseña y pulsa **Entrar** (o presiona la tecla Enter).
4. Si la contraseña es correcta, la pagina se recargara con el modo editor activo.

![Ventana emergente pidiendo la contraseña de edición](./imagenes/captura-09-ventana-emergente-pidiendo-la-contrasena.png)

> **Importante:** Si introduces la contraseña incorrecta 3 veces, el acceso se bloqueara durante unos minutos.

### 8.3 Editar la solucion de un registro

1. Con el modo editor activo, haz clic en la celda de la columna **Solucion** del registro que quieras editar.
   - Si esta vacia, mostrara "Clic para anadir..." con un icono de lapiz.
2. Se abrira un area de texto donde podras escribir la solucion.
3. Haz clic en **Guardar** para guardar los cambios.
4. Haz clic en **Cancelar** si no quieres guardar.

![Celda de solucion en modo edición con el area de texto abierta y los botones Guardar/Cancelar](./imagenes/captura-10-celda-de-solucion-en-modo-edicion-con-el.png)

### 8.4 Marcar un registro como corregido

1. Con el modo editor activo, haz clic en la etiqueta **No** (roja) de la columna **Corregido**.
2. La etiqueta cambiara automáticamente a **Si** (verde).
3. Si quieres desmarcar, haz clic de nuevo en **Si** y volvera a **No**.
4. El cambio se guarda automáticamente al hacer clic.

![Columna Corregido mostrando la etiqueta cambiando de No (rojo) a Si (verde)](./imagenes/captura-11-columna-corregido-mostrando-la-etiqueta.png)

### 8.5 Desactivar el modo editor

1. Haz clic en el boton **Desactivar edición** en la barra de herramientas.
2. La pagina se recargara en modo lectura.

---

## Resumen rápido

| Accion                          | Como hacerlo                                        |
|---------------------------------|-----------------------------------------------------|
| Abrir una consulta              | Clic en la tarjeta o en la pestana                  |
| Buscar en la tabla              | Escribir en el buscador (mínimo 3 caracteres)       |
| Limpiar busqueda                | Clic en la X del buscador                           |
| Ordenar por columna             | Clic en la cabecera de la columna                   |
| Cambiar de pagina               | Botones del paginador                               |
| Exportar datos                  | Botones CSV, PDF o Excel                            |
| Ver estadísticas                | Botón **📊 Estadísticas** en la barra de herramientas |
| Editar solucion                 | Activar editor + clic en celda Solucion             |
| Marcar como corregido           | Activar editor + clic en etiqueta No/Si             |

---

*Fin del manual -- Módulo Consultas v1.6*
