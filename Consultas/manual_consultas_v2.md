# Manual de Usuario -- Modulo Consultas

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Consultas                      |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al modulo Consultas](#1-acceder-al-modulo-consultas)
2. [Seleccionar una consulta](#2-seleccionar-una-consulta)
3. [Usar el buscador](#3-usar-el-buscador)
4. [Ordenar columnas](#4-ordenar-columnas)
5. [Navegar por las paginas](#5-navegar-por-las-paginas)
6. [Exportar datos (CSV, PDF, Excel)](#6-exportar-datos-csv-pdf-excel)
7. [Control de Cambios](#7-control-de-cambios)

---

## 1. Acceder al modulo Consultas

1. Abre la aplicacion Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Consultas**.
3. Aparecera la pantalla principal con tarjetas grandes, una por cada consulta disponible.

![Pantalla principal del modulo Consultas mostrando las tarjetas de las consultas disponibles](./imagenes/captura-01-pantalla-principal-del-modulo-consultas.png)

---

## 2. Seleccionar una consulta

1. En la pantalla principal, haz clic en la tarjeta de la consulta que necesites.
2. Las consultas disponibles son:

| Consulta                             | Que muestra                                                    |
|--------------------------------------|----------------------------------------------------------------|
| Centros con Dispositivo de Tension   | Centros que tienen tensiometro (DCT)                           |
| Lineas Activas con EDC              | Lineas de datos activas con su equipo                          |
| Mantenimiento Equipos Satec          | Equipos Teldat, Cisco y Fortigate para mantenimiento           |
| Lineas Datos                         | Todas las lineas de datos activas de centros abiertos          |
| Lineas Voz                           | Todas las lineas de voz activas                                |
| Equipos Voz                          | Todos los equipos de voz activos                               |
| Equipos 2.o Nivel                    | Todos los EDCs de segundo nivel activos                        |
| Diversificacion                      | Estado de diversificacion de cada centro                       |
| Circuitos por Nodo                   | Lineas que pasan por un nodo concreto                          |
| Control de Cambios                   | Registro de cambios e incidencias                              |

3. Una vez seleccionada, la tabla de resultados se mostrara con todos los datos.
4. En la parte superior aparecera una barra de pestanas para cambiar rapidamente entre consultas sin volver al menu.

![Barra de pestanas (pills) con la consulta activa resaltada y la tabla de resultados debajo](./imagenes/captura-02-barra-de-pestanas-pills-con-la-consulta.png)

### Caso especial: Circuitos por Nodo

Esta consulta requiere un paso adicional:

1. Al seleccionarla, aparecera un campo de busqueda.
2. Escribe el nombre del nodo (minimo 3 caracteres).
3. Pulsa **Enter** o haz clic en **Buscar**.
4. Se mostraran todas las lineas que pasan por ese nodo.
5. Los nombres de nodo en los resultados son enlaces: puedes hacer clic en ellos para ver los circuitos de otro nodo.

![Formulario de busqueda por nodo con un ejemplo de resultado](./imagenes/captura-03-formulario-de-busqueda-por-nodo-con-un-e.png)

---

## 3. Usar el buscador

1. En la barra de herramientas de cualquier consulta, localiza el campo de **busqueda** (a la izquierda).
2. Escribe el texto que quieras buscar (minimo **3 caracteres**).
3. La tabla se filtrara automaticamente, mostrando solo las filas que contengan ese texto en cualquier columna.
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

Las consultas muestran **50 registros por pagina**. Si hay mas datos, aparecera un paginador en la parte inferior de la tabla.

1. Usa los botones numerados para ir a una pagina concreta.
2. Usa las flechas **<** y **>** para avanzar o retroceder una pagina.
3. Usa los botones de principio y fin para ir a la primera o ultima pagina.
4. Debajo del paginador veras la informacion: "Pagina X de Y -- mostrando N-M de Total".

![Paginador mostrando botones de pagina y la informacion de registros](./imagenes/captura-06-paginador-mostrando-botones-de-pagina-y.png)

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

En la exportacion a Excel de esta consulta, los centros se agrupan visualmente por colores segun su estado de diversificacion:

| Estado                  | Color de fondo |
|-------------------------|----------------|
| Diversificado Total     | Verde          |
| Diversificado Acceso    | Azul           |
| Diversificado Parcial   | Amarillo       |
| No Diversificado        | Rojo           |
| Faltan Datos            | Gris           |

---

## 7. Control de Cambios

La consulta **Control de Cambios** tiene funcionalidades adicionales de edicion. Se utiliza para registrar cambios e incidencias y hacer seguimiento de su solucion.

### 7.1 Ver el registro de cambios (modo lectura)

1. Selecciona **Control de Cambios** en el menu de consultas.
2. Veras una tabla con las columnas:
   - **Tipo** -- Tipo de cambio o incidencia
   - **Fecha** -- Cuando se registro
   - **Version** -- Version afectada
   - **Descripcion** -- Detalle del cambio
   - **Solucion** -- Solucion aplicada (puede estar vacio si aun no se ha resuelto)
   - **Autor** -- Quien lo registro
   - **Corregido** -- Indicador Si (verde) o No (rojo)

![Tabla de Control de Cambios en modo lectura con las columnas visibles](./imagenes/captura-08-tabla-de-control-de-cambios-en-modo-lect.png)

### 7.2 Activar el modo editor

Para poder editar la solucion o marcar como corregido, necesitas activar el modo editor:

1. Haz clic en el boton **Activar edicion** (en la barra de herramientas).
2. Aparecera una ventana pidiendo la contrasena de edicion.
3. Introduce la contrasena y pulsa **Entrar** (o presiona la tecla Enter).
4. Si la contrasena es correcta, la pagina se recargara con el modo editor activo.

![Ventana emergente pidiendo la contrasena de edicion](./imagenes/captura-09-ventana-emergente-pidiendo-la-contrasena.png)

> **Importante:** Si introduces la contrasena incorrecta 3 veces, el acceso se bloqueara durante unos minutos.

### 7.3 Editar la solucion de un registro

1. Con el modo editor activo, haz clic en la celda de la columna **Solucion** del registro que quieras editar.
   - Si esta vacia, mostrara "Clic para anadir..." con un icono de lapiz.
2. Se abrira un area de texto donde podras escribir la solucion.
3. Haz clic en **Guardar** para guardar los cambios.
4. Haz clic en **Cancelar** si no quieres guardar.

![Celda de solucion en modo edicion con el area de texto abierta y los botones Guardar/Cancelar](./imagenes/captura-10-celda-de-solucion-en-modo-edicion-con-el.png)

### 7.4 Marcar un registro como corregido

1. Con el modo editor activo, haz clic en la etiqueta **No** (roja) de la columna **Corregido**.
2. La etiqueta cambiara automaticamente a **Si** (verde).
3. Si quieres desmarcar, haz clic de nuevo en **Si** y volvera a **No**.
4. El cambio se guarda automaticamente al hacer clic.

![Columna Corregido mostrando la etiqueta cambiando de No (rojo) a Si (verde)](./imagenes/captura-11-columna-corregido-mostrando-la-etiqueta.png)

### 7.5 Desactivar el modo editor

1. Haz clic en el boton **Desactivar edicion** en la barra de herramientas.
2. La pagina se recargara en modo lectura.

---

## Resumen rapido

| Accion                          | Como hacerlo                                        |
|---------------------------------|-----------------------------------------------------|
| Abrir una consulta              | Clic en la tarjeta o en la pestana                  |
| Buscar en la tabla              | Escribir en el buscador (minimo 3 caracteres)       |
| Limpiar busqueda                | Clic en la X del buscador                           |
| Ordenar por columna             | Clic en la cabecera de la columna                   |
| Cambiar de pagina               | Botones del paginador                               |
| Exportar datos                  | Botones CSV, PDF o Excel                            |
| Editar solucion                 | Activar editor + clic en celda Solucion             |
| Marcar como corregido           | Activar editor + clic en etiqueta No/Si             |

---

*Fin del manual -- Modulo Consultas v1.5*
