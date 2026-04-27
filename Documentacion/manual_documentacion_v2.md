# Manual de Usuario -- Módulo Documentación

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Módulo**  | Documentación                  |
| **Versión** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al módulo Documentación](#1-acceder-al-modulo-documentacion)
2. [Navegar por las carpetas](#2-navegar-por-las-carpetas)
3. [Buscar documentos](#3-buscar-documentos)
4. [Subir un documento](#4-subir-un-documento)
5. [Esperar la conversion a PDF](#5-esperar-la-conversion-a-pdf)
6. [Ver un documento PDF](#6-ver-un-documento-pdf)
7. [Descargar un documento](#7-descargar-un-documento)
8. [Eliminar un documento](#8-eliminar-un-documento)

---

## 1. Acceder al módulo Documentación

1. Abre la aplicación Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Documentación**.
3. Aparecerá la pantalla principal con las carpetas de documentos y las últimas subidas.

![Pantalla principal del módulo Documentación mostrando las tarjetas de carpetas y la tabla de documentos](./imagenes/captura-01-pantalla-principal-del-modulo-documentac.png)

---

## 2. Navegar por las carpetas

Los documentos están organizados en carpetas (tipos). Cada carpeta aparece como una tarjeta con su nombre y el número de documentos que contiene.

1. Haz clic en la tarjeta de la carpeta que quieras explorar.
2. Se mostrara la tabla con los documentos de esa carpeta.
3. La tarjeta seleccionada aparecerá resaltada.
4. Para ver los documentos más recientes de todas las carpetas, haz clic en la tarjeta **"Últimas subidas"**.

![Tarjetas de carpetas con una seleccionada (resaltada) y la tabla de documentos de esa carpeta](./imagenes/captura-02-tarjetas-de-carpetas-con-una-seleccionad.png)

### Filtrar por fecha

Cuando tienes una carpeta seleccionada, puedes filtrar por rango de fechas:

1. Rellena los campos **Desde** y/o **Hasta** con las fechas deseadas.
2. Haz clic en **Filtrar**.
3. Para quitar los filtros, haz clic en **Limpiar**.

---

## 3. Buscar documentos

1. Con una carpeta seleccionada, escribe en el campo de **busqueda** el título o nombre del archivo.
2. Haz clic en **Filtrar**.
3. Se mostraran solo los documentos que coincidan con el texto buscado.
4. Para quitar la busqueda, haz clic en **Limpiar**.

![Campo de busqueda con texto escrito y boton Filtrar](./imagenes/captura-03-campo-de-busqueda-con-texto-escrito-y-bo.png)

---

## 4. Subir un documento

1. Haz clic en el boton **Subir documento** (en la parte superior derecha).
2. Se abrira el formulario de subida con los siguientes campos:

| Campo            | Descripción                                           | Obligatorio |
|------------------|-------------------------------------------------------|-------------|
| **Título**       | Nombre descriptivo del documento                      | Si          |
| **Tipo**         | Carpeta donde se guardara (seleccionar de la lista)   | Si          |
| **Descripción**  | Descripción adicional (opcional)                      | No          |
| **Archivo**      | El archivo a subir                                    | Si          |

3. Haz clic en **Seleccionar archivo** y elige el documento de tu equipo.
4. Haz clic en **Subir documento**.

![Formulario de subida con los campos Título, Tipo, Descripción y selector de archivo](./imagenes/captura-04-formulario-de-subida-con-los-campos-titu.png)

### Formatos y tamaño permitidos

| Formatos aceptados                           | Tamaño máximo |
|----------------------------------------------|---------------|
| PDF, Word (docx, doc), Excel (xlsx, xls), PowerPoint (pptx, ppt) | 50 MB         |

> **Nota:** Si el formato no esta en la lista o el archivo supera los 50 MB, aparecerá un mensaje de error y deberas seleccionar otro archivo.

---

## 5. Esperar la conversion a PDF

Después de subir un documento, el sistema lo convierte automáticamente a PDF para poder verlo en el navegador. Este proceso puede tardar unos segundos.

### Que veras en la tabla

| Estado              | Significado                                               | Icono         |
|---------------------|-----------------------------------------------------------|---------------|
| **Listo**           | El documento esta disponible para ver                     | Punto verde   |
| **Convirtiendo...** | Se esta generando el PDF (espera unos segundos)           | Rueda girando |
| **Error**           | Hubo un problema en la conversion                         | X roja        |

- Si el archivo ya es un PDF, el estado será **Listo** inmediatamente.
- Si es un Word, Excel o PowerPoint, el estado será **Convirtiendo...** durante unos segundos.
- **No necesitas recargar la pagina.** La pantalla se actualizara automáticamente cuando termine la conversion.

![Tabla de documentos mostrando un documento en estado "Convirtiendo..." con el icono de rueda girando](./imagenes/captura-05-tabla-de-documentos-mostrando-un-documen.png)

> Si el estado queda en "Error", puedes intentar subir el archivo de nuevo. Si el problema persiste, comprueba que el archivo no esta danado.

---

## 6. Ver un documento PDF

1. En la tabla de documentos, busca el documento que quieras ver.
2. Comprueba que su estado sea **Listo** (punto verde).
3. Haz clic en el boton **Ver** (icono de ojo).
4. Se abrira una ventana emergente con el visor de PDF integrado en el navegador.
5. Dentro del visor puedes:
   - Navegar por las paginas del documento
   - Hacer zoom
   - Usar las herramientas del visor PDF del navegador
6. Para cerrar el visor, haz clic en el boton **Cerrar** o pulsa la tecla **Escape**.

![Visor de PDF mostrando un documento dentro de la ventana emergente con el boton Cerrar visible](./imagenes/captura-06-visor-de-pdf-mostrando-un-documento-dent.png)

> **Nota:** El boton "Ver" solo esta disponible cuando el documento esta en estado "Listo". Si esta "Convirtiendo...", espera a que termine.

---

## 7. Descargar un documento

1. En la tabla de documentos, busca el documento que quieras descargar.
2. Haz clic en el boton **Descargar** (icono de descarga).
3. Aparecerá un mensaje de confirmacion preguntando si deseas descargar el archivo.
4. Haz clic en **Aceptar**.
5. El archivo original (en su formato original: docx, xlsx, pdf, etc.) se descargara a tu equipo.

![Mensaje de confirmacion de descarga con el nombre del archivo](./imagenes/captura-07-mensaje-de-confirmacion-de-descarga-con.png)

> **Nota:** La descarga siempre es del archivo **original** (no del PDF convertido). Si subiste un Word, descargaras el Word original.

---

## 8. Eliminar un documento

1. En la tabla de documentos, busca el documento que quieras eliminar.
2. Haz clic en el boton **Eliminar** (icono de papelera).
3. Aparecerá una ventana de confirmacion mostrando el título del documento.
4. Lee la advertencia: **esta accion es irreversible** (se eliminan tanto el archivo original como el PDF).
5. Haz clic en **Eliminar** para confirmar, o en **Cancelar** para volver atras.

![Ventana de confirmacion de eliminacion mostrando el título del documento y la advertencia](./imagenes/captura-08-ventana-de-confirmacion-de-eliminacion-m.png)

> **Importante:** Una vez eliminado, el documento no se puede recuperar. Asegurate de que ya no se necesita antes de eliminarlo.

---

## Resumen rápido

| Accion                    | Como hacerlo                                           |
|---------------------------|--------------------------------------------------------|
| Ver documentos de una carpeta | Clic en la tarjeta de la carpeta                   |
| Ver últimas subidas       | Clic en la tarjeta "Últimas subidas"                   |
| Buscar documento          | Escribir en el buscador + Filtrar                      |
| Filtrar por fecha         | Rellenar Desde/Hasta + Filtrar                         |
| Subir documento           | Boton "Subir documento" + rellenar formulario          |
| Ver PDF                   | Boton "Ver" (solo si estado es Listo)                  |
| Descargar original        | Boton "Descargar" + Aceptar                            |
| Eliminar documento        | Boton "Eliminar" + Confirmar                           |
| Cerrar visor PDF          | Boton Cerrar o tecla Escape                            |

---

*Fin del manual -- Módulo Documentación v1.5*
