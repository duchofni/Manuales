# Manual de Usuario -- Modulo Centros

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Centros                        |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al modulo Centros](#1-acceder-al-modulo-centros)
2. [Buscar un centro](#2-buscar-un-centro)
3. [Leer la ficha del centro](#3-leer-la-ficha-del-centro)
4. [Copiar datos del centro al portapapeles](#4-copiar-datos-del-centro-al-portapapeles)
5. [Ver el estado Nagios](#5-ver-el-estado-nagios)
6. [Editar comentarios](#6-editar-comentarios)
7. [Ver la documentacion del centro](#7-ver-la-documentacion-del-centro)
8. [Ver el detalle de una linea de datos](#8-ver-el-detalle-de-una-linea-de-datos)
9. [Ver la imagen de un equipo](#9-ver-la-imagen-de-un-equipo)
10. [Consultar el tensiometro (DCT)](#10-consultar-el-tensiometro-dct)

---

## 1. Acceder al modulo Centros

1. Abre la aplicacion Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Centros**.
3. Se mostrara la pantalla del buscador de centros.

![Pantalla inicial del modulo Centros mostrando el campo de busqueda vacio](./imagenes/captura-01-pantalla-inicial-del-modulo-centros-most.png)

---

## 2. Buscar un centro

Puedes buscar un centro de dos formas: por **autocompletado** o por **busqueda libre**.

### Opcion A -- Autocompletado (recomendado)

1. Empieza a escribir el nombre del centro en el campo de busqueda.
2. Cuando lleves al menos **2 caracteres**, aparecera una lista de sugerencias debajo del campo.
3. Haz clic en el centro que buscas de la lista.
4. Se abrira directamente la ficha de ese centro.

![Campo de busqueda con lista de sugerencias de autocompletado desplegada](./imagenes/captura-02-campo-de-busqueda-con-lista-de-sugerenci.png)

### Opcion B -- Busqueda libre

1. Escribe en el campo de busqueda cualquiera de estos datos:
   - Nombre del centro
   - Direccion
   - ID de cliente
   - Numero de linea (datos o voz)
   - Administrativo
   - Nemonico de equipo
2. Pulsa **Enter** o haz clic en el boton de buscar.
3. Si se encuentra un unico resultado, se abrira la ficha directamente.
4. Si hay varios resultados, aparecera una tabla con las columnas:
   - **Nombre** del centro
   - **Poblacion**
   - **Provincia**
   - Boton **Abrir** para acceder a la ficha
5. Los centros cerrados apareceran con una etiqueta **[CERRADO]** y en tono apagado.

![Tabla de resultados de busqueda con varios centros, uno de ellos marcado como CERRADO](./imagenes/captura-03-tabla-de-resultados-de-busqueda-con-vari.png)

> **Nota:** La busqueda muestra un maximo de 50 resultados. Si no encuentras lo que buscas, prueba con un termino mas especifico.

---

## 3. Leer la ficha del centro

Una vez que abres un centro, la ficha se divide en varias secciones:

### Datos del centro (bloque izquierdo)

Muestra toda la informacion basica del centro organizada en filas:

- **ID Cliente** -- Codigo identificador del cliente
- **Direccion, C. Postal, Poblacion, Provincia** -- Ubicacion del centro
- **Coordenadas** -- Si estan disponibles, incluye un enlace a Google Maps
- **Cerrado** -- Indica si el centro esta cerrado (casilla de solo lectura)
- **Critica** -- Indica si es una sede critica (casilla de solo lectura)
- **Tensiometro** -- Indica si tiene dispositivo de tension (casilla de solo lectura + enlace)
- **H. Centro** -- Horario del centro
- **Horario** -- Tipo de horario asignado
- **Centralita** -- Tipo de centralita (CISCO / OXE)
- **Tipo Sede** -- Clasificacion de la sede
- **Switch** -- Fabricante del switch
- **RAI / Modulo** -- Identificadores RAI y modulo para CISCO, OXE y NGN
- **Documentacion** -- Enlace para ver los documentos del centro

![Ficha del centro mostrando el bloque de datos con todos los campos rellenos](./imagenes/captura-04-ficha-del-centro-mostrando-el-bloque-de.png)

### Tablas de lineas y equipos

Debajo de la ficha aparecen las tablas con los elementos activos del centro:

- **Lineas de datos** -- Tabla principal con todas las lineas de datos activas
- **Lineas de voz** -- Tabla con las lineas de voz activas
- **Equipos de voz** -- Tabla con los equipos de voz activos
- **Equipos de 2.o nivel** -- Tabla con los EDCs de segundo nivel activos

Cada tabla tiene:
- Un **buscador** para filtrar filas escribiendo cualquier texto
- **Paginacion** con informacion de pagina actual y total
- Un boton **Copiar tabla** para copiar las filas visibles al portapapeles

![Vista general de la ficha de un centro con las tablas de lineas de datos y las tres tablas inferiores (voz, equipos voz, equipos 2.o nivel)](./imagenes/captura-05-vista-general-de-la-ficha-de-un-centro-c.png)

---

## 4. Copiar datos del centro al portapapeles

1. En la ficha del centro, localiza el boton de copiar (icono de copiar) junto al nombre del centro.
2. Haz clic en el boton.
3. Se copiara al portapapeles un texto con el formato:
   **Nombre -- Horario -- Direccion -- CP -- Poblacion -- Provincia**
4. El icono cambiara brevemente a un check verde para confirmar que se ha copiado.
5. Pega el texto donde lo necesites con **Ctrl+V**.

> **Uso tipico:** Para pegar rapidamente los datos del centro en un correo o incidencia.

### Copiar una tabla completa

1. En cualquiera de las tablas (lineas de datos, lineas de voz, equipos de voz, equipos de 2.o nivel), haz clic en el boton **Copiar tabla**.
2. Se copiaran al portapapeles todas las filas visibles en formato tabla con bordes.
3. Aparecera un aviso confirmando la copia.
4. Pega con **Ctrl+V** en un correo o documento para mantener el formato de tabla.

---

## 5. Ver el estado Nagios

El bloque de **Estado Nagios** aparece en la parte derecha de la ficha del centro. Muestra el estado de monitorizacion de todos los equipos del centro.

Cada equipo aparece con un indicador de color:

| Color    | Significado                                      |
|----------|--------------------------------------------------|
| Verde    | El equipo esta **activo** (UP) en Nagios         |
| Rojo     | El equipo esta **caido** (DOWN) en Nagios        |
| Gris     | El equipo **no esta monitorizado** en Nagios     |

![Bloque de estado Nagios mostrando varios equipos con indicadores verde, rojo y gris](./imagenes/captura-06-bloque-de-estado-nagios-mostrando-varios.png)

> **Nota:** Los datos de Nagios se actualizan automaticamente cada 30 segundos. No es necesario recargar la pagina.

---

## 6. Editar comentarios

1. En la ficha del centro, localiza el bloque **Comentarios** (parte central de la ficha).
2. Haz clic dentro del area de texto.
3. Escribe o modifica el texto que necesites.
4. Al hacer clic fuera del campo (o cambiar a otra zona), los comentarios se guardan automaticamente.
5. Durante el guardado veras indicadores visuales:
   - **Borde azul** -- Se esta guardando
   - **Borde verde** -- Guardado correctamente
   - **Borde rojo** -- Error al guardar (intentalo de nuevo)

![Campo de comentarios con borde verde indicando guardado correcto](./imagenes/captura-07-campo-de-comentarios-con-borde-verde-ind.png)

> **Importante:** No necesitas pulsar ningun boton para guardar. El guardado es automatico al salir del campo.

---

## 7. Ver la documentacion del centro

1. En la ficha del centro, busca el enlace **Documentacion** en el bloque de datos.
2. Haz clic en el enlace.
3. Se abrira el gestor de documentos del centro con:
   - Un **panel izquierdo** con el arbol de carpetas (CONFIGURACIONES, FOTOS, MANTENIMIENTO, PROVISION, REPLANTEOS, OTROS)
   - Un **panel derecho** con el contenido de la carpeta seleccionada

### Navegar por las carpetas

1. Haz clic en una carpeta del panel izquierdo para ver su contenido.
2. Usa las migas de pan (breadcrumb) en la parte superior para volver a carpetas anteriores.

### Ver un archivo

1. Haz clic en el archivo que quieras ver.
2. Segun el tipo de archivo:
   - **Imagenes** (jpg, png, gif) -- Se muestran directamente en pantalla
   - **PDF** -- Se abre un visor de PDF en el navegador
   - **Texto** -- Se muestra el contenido en formato texto
   - **Otros formatos** -- Se ofrece un boton de descarga

### Subir un archivo

1. Haz clic en el boton de subir archivo (boton azul).
2. Selecciona el archivo de tu equipo.
3. El archivo se subira automaticamente a la carpeta actual.

![Gestor de documentos del centro mostrando el arbol de carpetas a la izquierda y archivos a la derecha](./imagenes/captura-08-gestor-de-documentos-del-centro-mostrand.png)

---

## 8. Ver el detalle de una linea de datos

1. En la tabla de **Lineas de datos**, busca la linea que te interese.
2. Haz clic en el boton de la **lupa** (columna "Detalle") de esa linea.
3. Se abrira una ventana emergente con toda la informacion detallada de la linea:

   - **Datos de la linea:** ID, tipo, numero, administrativo, servicio, velocidad, funcion, tipo de acceso, OLT, nodos de acceso y red
   - **Observaciones de la linea** (si las hay)
   - **Datos del equipo:** ID, modelo, IOS, nemonicos, IPs, numero de serie, si es gestionable
   - **Routing y WAN:** Red WAN, routing WAN y routing LAN
   - **VLANs:** Estado de las 7 VLANs del equipo (Datos, Voz, RFID, MESI, Electro, Retinometro, Ecografo) con indicador de activa/inactiva
   - **Switch cliente:** Si tiene switch de cliente e IP del switch
   - **Observaciones del equipo** (si las hay)

4. Para cerrar la ventana, haz clic en el boton **Cerrar**, haz clic fuera de la ventana o pulsa la tecla **Escape**.

![Ventana emergente de detalle de linea mostrando las secciones de datos, equipo y VLANs](./imagenes/captura-09-ventana-emergente-de-detalle-de-linea-mo.png)

### Enlaces utiles en la tabla de lineas

- **Administrativo** -- Haz clic para abrir las pruebas de Telefonica (ETXLAN) de esa linea
- **Nemonico** -- Haz clic para abrir una conexion SSH al equipo
- **Nodo Acceso / Nodo Red** -- Haz clic para ver todos los circuitos de ese nodo en el modulo Consultas

---

## 9. Ver la imagen de un equipo

1. En las tablas de lineas de datos, equipos de voz o equipos de 2.o nivel, busca la columna **Equipo** o **Modelo**.
2. Si el modelo tiene imagen disponible, aparecera como un enlace.
3. Haz clic en el nombre del modelo.
4. Se abrira una ventana con la fotografia del equipo a tamano grande.
5. Para cerrar, haz clic fuera de la imagen o pulsa **Escape**.

![Visor de imagen mostrando la fotografia de un modelo de equipo (por ejemplo, un Fortigate 60F)](./imagenes/captura-10-visor-de-imagen-mostrando-la-fotografia.png)

---

## 10. Consultar el tensiometro (DCT)

Si el centro tiene un dispositivo de control de tension (tensiometro), podras consultar sus datos:

1. En la ficha del centro, busca el campo **Tensiometro** en el bloque de datos.
2. Si la casilla esta marcada, haz clic en el enlace **Tensiometro**.
3. Se abrira una ventana emergente con los datos del dispositivo:
   - **ICC** -- Numero de ICC del dispositivo
   - **Numero Largo** -- Numero de telefono largo
   - **Extension** -- Extension corta
4. Para cerrar la ventana, haz clic en **Cerrar**, haz clic fuera de la ventana o pulsa **Escape**.

![Ventana emergente del tensiometro mostrando los campos ICC, Numero Largo y Extension](./imagenes/captura-11-ventana-emergente-del-tensiometro-mostra.png)

---

## Resumen de atajos y consejos

| Accion                          | Como hacerlo                                           |
|---------------------------------|--------------------------------------------------------|
| Buscar un centro                | Escribir en el buscador (minimo 2 caracteres)          |
| Copiar datos del centro         | Boton de copiar junto al nombre                        |
| Copiar tabla completa           | Boton "Copiar tabla" debajo de cada tabla              |
| Guardar comentarios             | Se guarda automaticamente al salir del campo            |
| Abrir detalle de linea          | Boton lupa en la tabla de lineas de datos              |
| Ver imagen de equipo            | Clic en el nombre del modelo (si es enlace)            |
| Ver tensiometro                 | Clic en enlace "Tensiometro" en la ficha               |
| Cerrar ventanas emergentes      | Boton Cerrar, clic fuera, o tecla Escape               |
| Abrir conexion SSH a equipo     | Clic en el nemonico del equipo                         |
| Ver circuitos de un nodo        | Clic en el nombre del nodo de acceso o red             |

---

*Fin del manual -- Modulo Centros v1.5*
