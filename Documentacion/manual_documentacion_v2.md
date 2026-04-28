# Manual de Usuario: Módulo Documentación

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Módulo**  | Documentación                  |
| **Versión** | 1.6                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Índice

1. [Cómo accedemos al módulo](#1-cómo-accedemos-al-módulo)
2. [Navegar por las carpetas](#2-navegar-por-las-carpetas)
3. [Buscar documentos](#3-buscar-documentos)
4. [Subir un documento](#4-subir-un-documento)
5. [Esperar la conversión a PDF](#5-esperar-la-conversión-a-pdf)
6. [Ver un documento PDF](#6-ver-un-documento-pdf)
7. [Descargar un documento](#7-descargar-un-documento)
8. [Eliminar un documento](#8-eliminar-un-documento)

---

## 1. Cómo accedemos al módulo

1. Abrimos la **Web BDU** en el navegador.
2. En el menú lateral pulsamos **Documentación**.
3. Aparece la pantalla principal con las carpetas de documentos y las últimas subidas.

![Pantalla principal del módulo Documentación mostrando las tarjetas de carpetas y la tabla de documentos](./imagenes/captura-01-pantalla-principal-del-modulo-documentac.png)

---

## 2. Navegar por las carpetas

Los documentos están organizados en carpetas (tipos). Cada carpeta aparece como una tarjeta con su nombre y el número de documentos que contiene.

1. Pulsamos sobre la tarjeta de la carpeta que queramos explorar.
2. Se muestra la tabla con los documentos de esa carpeta.
3. La tarjeta seleccionada aparece resaltada.
4. Para ver los documentos más recientes de todas las carpetas, pulsamos la tarjeta **"Últimas subidas"**.

![Tarjetas de carpetas con una seleccionada (resaltada) y la tabla de documentos de esa carpeta](./imagenes/captura-02-tarjetas-de-carpetas-con-una-seleccionad.png)

### 2.1. Filtrar por fecha

Cuando tenemos una carpeta seleccionada podemos filtrar por rango de fechas:

1. Rellenamos los campos **Desde** y/o **Hasta** con las fechas deseadas.
2. Pulsamos **Filtrar**.
3. Para quitar los filtros pulsamos **Limpiar**.

---

## 3. Buscar documentos

1. Con una carpeta seleccionada, escribimos en el campo de **búsqueda** el título o el nombre del archivo.
2. Pulsamos **Filtrar**.
3. Se muestran solo los documentos que coincidan con el texto buscado.
4. Para quitar la búsqueda pulsamos **Limpiar**.

![Campo de búsqueda con texto escrito y botón Filtrar](./imagenes/captura-03-campo-de-busqueda-con-texto-escrito-y-bo.png)

---

## 4. Subir un documento

1. Pulsamos el botón **Subir documento** (en la parte superior derecha).
2. Se abre el formulario de subida con los siguientes campos:

| Campo            | Descripción                                           | Obligatorio |
|------------------|-------------------------------------------------------|-------------|
| **Título**       | Nombre descriptivo del documento.                     | Sí          |
| **Tipo**         | Carpeta donde se guardará (seleccionar de la lista).  | Sí          |
| **Descripción**  | Descripción adicional (opcional).                     | No          |
| **Archivo**      | El archivo a subir.                                   | Sí          |

3. Pulsamos **Seleccionar archivo** y elegimos el documento.
4. Pulsamos **Subir documento**.

![Formulario de subida con los campos Título, Tipo, Descripción y selector de archivo](./imagenes/captura-04-formulario-de-subida-con-los-campos-titu.png)

### 4.1. Formatos y tamaño permitidos

| Formatos aceptados                                                  | Tamaño máximo |
|---------------------------------------------------------------------|---------------|
| PDF, Word (docx, doc), Excel (xlsx, xls), PowerPoint (pptx, ppt).   | 50 MB         |

> **Nota:** si el formato no está en la lista o el archivo supera los 50 MB, aparece un mensaje de error y tenemos que seleccionar otro archivo.

---

## 5. Esperar la conversión a PDF

Después de subir un documento, el sistema lo convierte automáticamente a PDF para poder verlo en el navegador. Este proceso puede tardar unos segundos.

### Qué vemos en la tabla

| Estado              | Significado                                               | Icono         |
|---------------------|-----------------------------------------------------------|---------------|
| **Listo**           | El documento está disponible para ver.                    | Punto verde.  |
| **Convirtiendo…**   | Se está generando el PDF (esperamos unos segundos).       | Rueda girando.|
| **Error**           | Hubo un problema en la conversión.                        | X roja.       |

- Si el archivo ya es un PDF, el estado es **Listo** inmediatamente.
- Si es un Word, Excel o PowerPoint, el estado es **Convirtiendo…** durante unos segundos.
- **No hace falta recargar la página.** La pantalla se actualiza automáticamente cuando termina la conversión.

![Tabla de documentos mostrando un documento en estado "Convirtiendo…" con el icono de rueda girando](./imagenes/captura-05-tabla-de-documentos-mostrando-un-documen.png)

> Si el estado queda en *Error*, podemos intentar subir el archivo de nuevo. Si el problema persiste, comprobamos que el archivo no esté dañado.

---

## 6. Ver un documento PDF

1. En la tabla de documentos buscamos el que queramos ver.
2. Comprobamos que su estado sea **Listo** (punto verde).
3. Pulsamos el botón **Ver** (icono de ojo).
4. Se abre una ventana emergente con el visor de PDF integrado en el navegador.
5. Dentro del visor podemos:
   - Navegar por las páginas del documento.
   - Hacer zoom.
   - Usar las herramientas del visor PDF del navegador.
6. Para cerrar el visor pulsamos **Cerrar** o la tecla **Escape**.

![Visor de PDF mostrando un documento dentro de la ventana emergente con el botón Cerrar visible](./imagenes/captura-06-visor-de-pdf-mostrando-un-documento-dent.png)

> **Nota:** el botón **Ver** solo está disponible cuando el documento está en estado *Listo*. Si está *Convirtiendo…*, esperamos a que termine.

---

## 7. Descargar un documento

1. En la tabla de documentos buscamos el que queramos descargar.
2. Pulsamos el botón **Descargar** (icono de descarga).
3. Aparece un mensaje de confirmación preguntando si queremos descargar el archivo.
4. Pulsamos **Aceptar**.
5. El archivo original (en su formato: docx, xlsx, pdf, etc.) se descarga al equipo.

![Mensaje de confirmación de descarga con el nombre del archivo](./imagenes/captura-07-mensaje-de-confirmacion-de-descarga-con.png)

> **Nota:** la descarga siempre es del archivo **original** (no del PDF convertido). Si subimos un Word, descargamos el Word original.

---

## 8. Eliminar un documento

1. En la tabla de documentos buscamos el que queramos eliminar.
2. Pulsamos el botón **Eliminar** (icono de papelera).
3. Aparece una ventana de confirmación con el título del documento.
4. Leemos la advertencia: **esta acción es irreversible** (se eliminan tanto el archivo original como el PDF).
5. Pulsamos **Eliminar** para confirmar, o **Cancelar** para volver atrás.

![Ventana de confirmación de eliminación mostrando el título del documento y la advertencia](./imagenes/captura-08-ventana-de-confirmacion-de-eliminacion-m.png)

> **Importante:** una vez eliminado, el documento no se puede recuperar. Nos aseguramos de que ya no se necesita antes de eliminarlo.

---

## Resumen rápido

| Acción                        | Cómo lo hacemos                                          |
|-------------------------------|----------------------------------------------------------|
| Ver documentos de una carpeta | Pulsar la tarjeta de la carpeta.                         |
| Ver últimas subidas           | Pulsar la tarjeta **"Últimas subidas"**.                 |
| Buscar documento              | Escribir en el buscador + Filtrar.                       |
| Filtrar por fecha             | Rellenar Desde/Hasta + Filtrar.                          |
| Subir documento               | Botón **Subir documento** + rellenar formulario.         |
| Ver PDF                       | Botón **Ver** (solo si el estado es *Listo*).            |
| Descargar original            | Botón **Descargar** + Aceptar.                           |
| Eliminar documento            | Botón **Eliminar** + Confirmar.                          |
| Cerrar visor PDF              | Botón **Cerrar** o tecla **Escape**.                     |

---

*Manual para operadores CGE SERGAS. Versión 1.6 — Abril 2026.*
