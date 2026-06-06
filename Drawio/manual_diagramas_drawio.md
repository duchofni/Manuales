# Manual de Usuario: Diagramas online (draw.io)

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Función** | Crear, ver y editar diagramas `.drawio` desde la cabecera y desde los listados de Documentación y Centros |
| **Versión** | 2.1                            |
| **Fecha**   | Mayo 2026                      |
| **Para**    | Operadores CGE SERGAS          |

---

## Índice

1. [Para qué sirve esto](#1-para-qué-sirve-esto)
2. [Formatos soportados](#2-formatos-soportados)
3. [Crear un diagrama nuevo desde la cabecera](#3-crear-un-diagrama-nuevo-desde-la-cabecera)
4. [Abrir un diagrama existente](#4-abrir-un-diagrama-existente)
5. [Guardar los cambios](#5-guardar-los-cambios)
6. [Diagramas Visio (.vsdx) heredados](#6-diagramas-visio-vsdx-heredados)
7. [Resumen rápido](#7-resumen-rápido)

---

## 1. Para qué sirve esto

Hasta ahora dibujábamos los esquemas de red, topologías y diagramas de flujo con la **aplicación de escritorio draw.io** (descargada en cada PC) y guardábamos los `.drawio` en una carpeta del NAS. Eso obligaba a tener la herramienta instalada y a moverse manualmente entre el explorador de archivos y la BDU.

Con la integración de draw.io en BDU **abrimos y editamos esos mismos diagramas dentro del navegador**, sin instalar nada:

- Cualquier `.drawio` que tengamos en el NAS aparece automáticamente en su sitio (Documentación, Centros…) con botones para verlo o editarlo.
- Podemos crear diagramas **nuevos en blanco** desde la cabecera de BDU (mismo modal donde creamos un Word o un Excel).
- Los `.vsdx` de Visio antiguos se abren para consulta sin necesidad de tener Visio.

El editor que se carga en pestaña nueva es **exactamente el mismo** que la aplicación de escritorio (mismos atajos, misma paleta de formas, misma exportación). No hay nada nuevo que aprender de la herramienta — solo cambia cómo entramos a ella.

---

## 2. Formatos soportados

| Extensión | Qué hacemos con ella |
|---|---|
| `.drawio` | Diagrama nativo de draw.io. Lo podemos **ver y editar** en BDU; los cambios se guardan en el NAS. |
| `.vsdx`   | Diagrama de Microsoft Visio. Lo podemos **abrir en modo lectura**. Si necesitamos editarlo, draw.io lo importa al abrirlo; para conservar los cambios hay que guardarlo como `.drawio` (ver sección 6). |

PNG y SVG con metadatos de draw.io NO están enchufados de momento — se ven como imagen normal en la web BDU.

---

## 3. Crear un diagrama nuevo desde la cabecera

Es **exactamente el mismo flujo** que para crear un Word/Excel/PowerPoint nuevo. Si no tenemos clara la mecánica del modal "Documentos", merece la pena leer antes el manual de [Documentos online (OnlyOffice)](../OnlyOffice/manual_documentos_online.md) — la parte de tipo + nombre + destino + explorador de carpetas funciona igual.

### 3.1. Abrir el modal

En la cabecera de BDU pulsamos el icono **📄+** (Nuevo documento). Se abre la ventana **"Documentos"** y aterrizamos en la pestaña **📝 Crear nuevo**.

### 3.2. Elegir el tipo "Diagrama"

En la fila de tipos pulsamos el botón **🗺️ Diagrama (drawio)**. Queda marcado en verde.

| Botón | Tipo de fichero |
|---|---|
| 📝 Word | `.docx` |
| 📊 Excel | `.xlsx` |
| 📋 PowerPoint | `.pptx` |
| 📃 Texto | `.txt` |
| **🗺️ Diagrama** | **`.drawio`** |

### 3.3. Poner el nombre y elegir destino

- **Nombre** del fichero (sin extensión; BDU le pone `.drawio`).
- **Destino**: *Mi carpeta*, *Carpeta común* o un **centro** concreto (con el mismo buscador y explorador de carpetas que para los Word/Excel).

### 3.4. Crear y abrir

Pulsamos el botón verde **Crear y abrir**. Se abre **una pestaña nueva del navegador** con draw.io cargando un lienzo en blanco. A partir de aquí dibujamos como siempre: arrastramos formas desde el panel izquierdo, conectamos con flechas, etc.

---

## 4. Abrir un diagrama existente

Los `.drawio` y `.vsdx` que ya estén en el NAS aparecen en varios sitios:

### 4.1. Desde Documentación

En **Documentación** (`?m=documentacion`), los diagramas se listan con icono **🗺️** y tienen los botones habituales:

- **👁** abre el diagrama en pestaña nueva en modo **lectura** (no se guardan cambios).
- **✏️** lo abre en pestaña nueva en modo **edición** (los cambios se guardan al NAS al pulsar guardar). Solo aparece para `.drawio`; los `.vsdx` no tienen ✏️.
- **⬇** descarga el fichero original.
- **🗑** lo elimina.

### 4.2. Desde un centro

En la ficha de un centro, pestaña **Documentación**, cualquier `.drawio` o `.vsdx` que esté dentro de las carpetas del centro aparece con icono **🗺️** y la flechita **↗** arriba a la derecha. Pulsando la tarjeta se abre directamente en draw.io en pestaña nueva.

### 4.3. Desde Mis borradores

Si creamos un diagrama desde la cabecera y elegimos *Mi carpeta* o *Carpeta común* como destino, lo encontramos también en la pestaña **📂 Mis borradores** del mismo modal, junto al resto de borradores (Word, Excel, etc.). Los diagramas aparecen con icono **🗺️**.

---

## 5. Guardar los cambios

draw.io guarda en BDU **al pulsar el icono de disquete** del editor o con el atajo `Ctrl + S`. También guarda automáticamente cada cierto tiempo mientras editamos (autosave).

Cuando guardamos:

- BDU escribe el `.drawio` actualizado **en su mismo sitio del NAS**, conservando nombre y carpeta.
- Si volvemos a abrirlo más tarde (desde Documentación, desde el centro o desde Mis borradores) tenemos la última versión.

> **Importante:** a diferencia de OnlyOffice, draw.io **no es colaborativo en tiempo real** dentro de BDU. Si dos operadores abrimos el mismo diagrama a la vez y guardamos los dos, **gana el último que guarde**. Para diagramas comunes conviene avisar al compañero antes de tocar.

---

## 6. Diagramas Visio (.vsdx) heredados

Tenemos diagramas históricos en formato Visio (`.vsdx`). draw.io los lee, así que podemos consultarlos desde BDU sin Visio:

- En el listado los vemos con icono **🗺️** y solo el botón **👁** (lectura).
- Al abrirlos, draw.io los importa al lienzo. Aparecen las mismas formas, conexiones y textos.
- **No podemos guardar cambios encima del `.vsdx`**: el guardado está bloqueado para preservar el original. Si necesitamos modificarlo, dentro del editor pulsamos **Archivo → Guardar como… → Dispositivo** y descargamos un `.drawio` que luego subimos a BDU como fichero nuevo (con el botón **⬆ Subir documento** de Documentación o desde la pestaña *Documentación* del centro).

> **Aviso sobre fidelidad:** la importación de Visio en draw.io es muy buena para diagramas estándar pero puede no respetar al 100% formas custom o macros del Visio. Si vemos algo descolocado en un `.vsdx` complejo, es la importación, no un fallo de BDU.

---

## 7. Resumen rápido

| Acción | Cómo |
|---|---|
| Crear un diagrama nuevo en blanco | Cabecera **📄+** → **Crear nuevo** → 🗺️ **Diagrama** → nombre + destino → **Crear y abrir** |
| Editar un diagrama del NAS | Documentación o Centro → botón **✏️** sobre el fichero `.drawio` |
| Solo verlo | Botón **👁** en Documentación o tarjeta **↗** en la ficha del centro |
| Guardar mientras editamos | Icono de disquete dentro de draw.io o `Ctrl + S` (también hay autosave) |
| Volver a abrir un borrador propio | Cabecera **📄+** → pestaña **Mis borradores** → click en el `.drawio` |
| Abrir un Visio (.vsdx) | Botón **👁**; para modificarlo, *Guardar como .drawio* desde el editor y subirlo a BDU |

---

*Manual para operadores CGE SERGAS. Versión 2.1 — Junio 2026.*
