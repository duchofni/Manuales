# BDU -- Manual de Usuario Global

| | |
|---|---|
| **Aplicación** | BDU (Base de Datos Unificada) |
| **Versión** | 1.5 |
| **Fecha** | Abril 2026 |
| **Para** | Operadores CGE SERGAS |

---

## Indice

1. [Introducción](#1-introduccion)
2. [Navegación general](#2-navegacion-general)
3. [Módulos](#3-modulos)
4. [Funciones comunes](#4-funciones-comunes)
5. [Preguntas frecuentes](#5-preguntas-frecuentes)
6. [Referencia de manuales](#6-referencia-de-manuales)

---

## 1. Introducción

### 1.1 Que es BDU

BDU (Base de Datos Unificada) es la aplicación web interna del Centro de Gestión (CGE) de Telefónica para el cliente SERGAS (Servicio Gallego de Salud). Permite gestionar de forma integral toda la infraestructura de red: centros sanitarios, líneas de datos y voz, equipos de comunicaciones, incidencias, provisiones, informes, documentación y herramientas operativas del día a dia.

En resumen, BDU es la herramienta principal de trabajo de los operadores del CGE para:

- Consultar información de centros sanitarios y su infraestructura de red
- Dar de alta, modificar o dar de baja elementos de red (líneas, equipos, centros)
- Gestionar incidencias y boletines de trabajo programado (BTPs)
- Generar correos operativos estandarizados
- Consultar y exportar datos en diferentes formatos
- Controlar el stock de equipos en almacenes
- Acceder a documentación interna y enlaces utiles
- Monitorizar el estado de la infraestructura en tiempo real

### 1.2 Para quien es este manual

Este manual esta dirigido a los **operadores del CGE SERGAS** que utilizan BDU en su trabajo diario. No se requieren conocimientos técnicos avanzados para seguir las instrucciones.

Cada módulo de BDU tiene su propio manual detallado con instrucciones paso a paso. Este documento ofrece una **visión global** de la aplicación y sirve como punto de partida para familiarizarse con todas las funcionalidades disponibles.

### 1.3 Como acceder

**URL de acceso:**

| Entorno | URL |
|---|---|
| Producción (PRO) | `https://bdu.sergascge.local` |
| Preproducción (PRE) | `https://pre.bdu.sergascge.local` |

> **Nota:** La URL de preproducción solo se utiliza para pruebas. El trabajo diario se realiza siempre en la URL de produccion.

**Pasos para acceder:**

1. Abrir el navegador web e introducir la URL de producción
2. Aparecerá la portada publica con el logotipo del CGE SERGAS y un boton **ACCEDER**
3. Pulsar **ACCEDER**
4. Introducir las credenciales del dominio (usuario y contraseña de red, las mismas que se usan para iniciar sesión en el ordenador)
5. Pulsar **Entrar**

![Pantalla de login con campos de usuario y contraseña](./imagenes/captura-01-pantalla-de-login-con-campos-de-usuario.png)

**Información importante sobre el acceso:**

- La autenticación se realiza contra el directorio LDAP del dominio `sergascge.local`
- Tras **3 intentos fallidos** de contraseña, la cuenta se bloquea durante **5 minutos**
- La sesión expira automáticamente tras **30 minutos de inactividad**. Si esto ocurre, se redirige a la pantalla de login con un aviso de sesión expirada

---

## 2. Navegación general

Una vez autenticado, la interfaz de BDU se compone de los siguientes elementos:

![Vista general de la aplicación con los elementos de navegación señalados](./imagenes/captura-02-vista-general-de-la-aplicacion-con-los-e.png)

### 2.1 Menu superior (barra de navegación)

En la parte superior de la pantalla se encuentra la barra de navegación con los módulos disponibles:

**Inicio** | **Centros** | **Provision** | **Instalaciones** | **Consultas** | **Stock** | **Correos** | **Mantenimiento** | **Documentación** | **Info/Ayuda** | **Mailviewer**

- Pulsar sobre cualquier nombre de módulo para acceder a el
- El módulo activo se resalta visualmente para que siempre se sepa en que seccion se esta trabajando

### 2.2 Modo oscuro

En la barra superior, junto a los botones de utilidad, se encuentra el boton de modo oscuro/claro:

- Pulsar el icono de luna para activar el **modo oscuro** (fondo oscuro, texto claro)
- Pulsar el icono de sol para volver al **modo claro** (fondo blanco, texto oscuro)
- La preferencia se guarda automáticamente en el navegador: al volver a entrar, se mantiene el último modo seleccionado

![Boton de modo oscuro en la barra superior](./imagenes/captura-03-boton-de-modo-oscuro-en-la-barra-superio.png)

### 2.3 Boton de feedback

El icono con forma de insecto permite **reportar incidencias o sugerencias** sobre la propia aplicación BDU.

- Pulsar el icono para abrir el formulario de feedback
- Describir el problema o la sugerencia
- Enviar el reporte

Este boton no esta relacionado con las incidencias de red; es exclusivamente para comunicar fallos o mejoras de la herramienta BDU.

### 2.4 Acerca de

El icono de información abre una ventana con los datos de la versión actual de BDU, incluyendo:

- Número de versión
- Información del desarrollador
- Datos de contacto

### 2.5 Cerrar sesión

Para cerrar la sesión de forma segura:

1. Pulsar el boton de **Cerrar sesión** en la parte derecha de la barra superior
2. Se vuelve a la portada publica

> **Importante:** Si simplemente se cierra el navegador sin cerrar sesión, esta expirará automáticamente a los 30 minutos.

---

## 3. Módulos

A continuacion se describe brevemente cada modulo. Para instrucciones detalladas, consultar el manual especifico de cada uno (ver seccion [6. Referencia de manuales](#6-referencia-de-manuales)).

---

### 3.1 Inicio

**Panel de control con KPIs y estado de la infraestructura.**

Al entrar en BDU, el módulo Inicio muestra un panel con la visión global del estado de la plataforma:

- **KPIs de centros:** total de centros, activos, cerrados, alta prioridad, FlexWAN, DCT
- **Graficos:** tipo de sede, líneas activas por tipo, equipos gestionados, equipos por modelo (top 12)
- **Incidencias:** resumen de incidencias abiertas clasificadas por tipo
- **Pedidos pendientes:** estado de instalaciones en curso
- **Infraestructura:** estado de los servidores Proxmox, NAS y base de datos

Los datos se actualizan automáticamente cada 2 minutos. Este módulo es solo de lectura (no se modifican datos).

![Panel de Inicio con KPIs y gráficos](./imagenes/captura-04-panel-de-inicio-con-kpis-y-graficos.png)

> **Manual detallado:** `Inicio/manual_inicio.md`

---

### 3.2 Centros

**Buscador y ficha completa de centros de salud.**

El módulo Centros permite buscar cualquier centro sanitario del SERGAS y ver toda su información de red:

- **Buscador inteligente** con autocompletado: busca por nombre del centro, dirección, IdCliente, número de línea, administrativo o nemonico de equipo
- **Ficha del centro** con datos generales, comentarios editables y estado Nagios en tiempo real
- **Líneas de datos** con detalle completo (línea, equipo, VLANs)
- **Líneas de voz**
- **Equipos de voz** con imagen del modelo
- **Equipos de segundo nivel** con imagen del modelo
- **Documentación del centro** almacenada en el NAS (subida de archivos, carpetas, visor integrado)

![Ficha de un centro con sus líneas y equipos](./imagenes/captura-05-ficha-de-un-centro-con-sus-lineas-y-equi.png)

> **Manual detallado:** `Centros/manual_centros.md`

---

### 3.3 Provision

**Altas, bajas y modificaciones de elementos de red.**

El módulo Provision permite gestionar el ciclo de vida de la infraestructura:

- **Altas:** centro nuevo, línea de datos con equipo, línea de voz, equipo de voz, equipo de segundo nivel
- **Modificaciones:** edición campo a campo de cualquier elemento existente
- **Bajas:** eliminacion de elementos individuales o cierre completo de un centro
- **Registro:** todas las acciones quedan registradas con usuario, fecha y detalle

**Acceso con contraseña adicional:**

Al entrar en Provision, se solicita una contraseña adicional además de la sesión LDAP ya iniciada. Esta contraseña es compartida por el equipo y protege las operaciones de modificación de datos.

![Menu principal de Provision con las opciones de alta, baja y modificación](./imagenes/captura-06-menu-principal-de-provision-con-las-opci.png)

> **Manual detallado:** `provision/manual_provision.md`

---

### 3.4 Instalaciones

**Gestión de instalaciones LOGOS, BJ, ATLAS y proyectos de red.**

Este módulo gestiona los pedidos e instalaciones de infraestructura, organizado en pestanas:

- **LOGOS (datos):** pedidos de instalaciones de datos importados vía CSV. Vista de pedidos activos e historico. Panel dividido con lista lateral y detalle
- **BJ (voz):** pedidos de instalaciones de voz con autocompletado de centro. Activos e historico. Integración con tuberias Indico
- **ATLAS:** ordenes importadas desde ficheros Excel. Cruces automaticos con pedidos LOGOS y datos de centros
- **Calendario:** vista mensual y semanal de instalaciones programadas con colores por tipo. Exportacion para impresion y copia para Outlook
- **Proyectos:** estadisticas agregadas de proyectos del CGE

![Vista de Instalaciones con las pestanas LOGOS, BJ, ATLAS, Calendario y Proyectos](./imagenes/captura-07-vista-de-instalaciones-con-las-pestanas.png)

> **Manual detallado:** `Instalaciones/manual_instalaciones.md`

---

### 3.5 Consultas

**Consultas predefinidas con exportacion CSV/PDF/Excel.**

El módulo Consultas ofrece un conjunto de consultas preparadas sobre los datos de BDU:

- Centros con Dispositivo de Tension
- Líneas Activas con EDC
- Mantenimiento Equipos Satec
- Líneas Datos / Líneas Voz
- Equipos Voz / Equipos 2o Nivel
- Diversificacion
- Circuitos por Nodo
- Control de Cambios (con modo editor para edición inline)

**Caracteristicas de todas las consultas:**

- Resultados filtrables con buscador
- Paginacion (50 resultados por pagina)
- Ordenacion por columnas
- Exportacion a CSV, PDF y Excel

![Resultado de una consulta con opciones de filtro y exportacion](./imagenes/captura-08-resultado-de-una-consulta-con-opciones-d.png)

> **Manual detallado:** `Consultas/manual_consultas.md`

---

### 3.6 Stock

**Control de stock de equipos de comunicaciones.**

El módulo Stock permite gestionar el inventario de equipos en los almacenes provinciales:

- **Stock EECC:** stock clasificado por empresa colaboradora
- **Stock Almacen:** stock clasificado por ubicacion fisica
- Actualización de cantidades
- Exportacion de datos

![Vista del módulo Stock con listado de equipos](./imagenes/captura-09-vista-del-modulo-stock-con-listado-de-eq.png)

> **Manual detallado:** `Stock/manual_stock.md`

---

### 3.7 Correos

**Generador de correos con plantillas predefinidas.**

El módulo Correos permite generar correos operativos estandarizados de forma rapida. Las plantillas garantizan que la información se envía siempre con el formato correcto.

**Categorías de plantillas disponibles:**

- **Averias Datos:** centro incomunicado, corte eléctrico, línea caida, masiva, Artemis, DWDM
- **Averias Voz:** Sirios, GLPI, IVR, tarificador, grabadoras, SIRIO, nodo EB, medidas radio, red inteligente
- **Soporte TI L3:** Satec, Ednon, Plexus, RightFax, tensiometro
- **Escalados:** Ibercom, CTM, Mesa Nacional
- **Satec:** VPN-IP, contingencia, boton rojo, técnico campo, SIRIO
- **Varios CGE:** cambio turno, informe Sergas, informe Telefónica

**Funcionamiento basico:**

1. Seleccionar la categoría
2. Seleccionar la plantilla
3. Rellenar los datos solicitados
4. Pulsar el boton para copiar la tabla al portapapeles y abrir el cliente de correo con el asunto y cuerpo predefinidos

![Seleccion de plantilla de correo y formulario de datos](./imagenes/captura-10-seleccion-de-plantilla-de-correo-y-formu.png)

> **Manual detallado:** `Correos/manual_correos.md`

---

### 3.8 Mantenimiento

**BTPs, Tareas automatizadas, Incidencias, Licencias, KPIs, Nagios, Informes, Grilloweb.**

El módulo Mantenimiento agrupa varias herramientas operativas organizadas en tarjetas desplegables:

#### BTPs (Boletines de Trabajo Programado)
Gestión de BTPs recibidos de Telefonica: importacion desde Excel, consulta por número o estado, marcado como informado, edición de detalles (estado, afectacion, fechas), generación de correo de revision diaria.

#### Tareas
Herramientas de automatización de red:
- **Config Planta (datos y voz):** configuración automatica de equipos vía SSH
- **Gentest 5G:** test BGP y reset radio en equipos 5G
- **Config Serial:** extracción de números de serie vía SSH
- **LOGOS-PT:** comparacion de CSV con base de datos
- **Importar seriales:** actualización de la base de datos desde logs historicos

#### Incidencias
Gestión completa de incidencias de red: creación, edición, acciones, cierre. Vista de activas y cerradas. Panel lateral con listado y area de detalle. Tipos: VOZ, DATOS, SOP TI L1/L3, Modificaciones. Validaciones temporales automaticas.

#### DDIs GDIA
Gestión de DDIs (números de marcacion directa) para incidencias GDIA.

#### Nagios
Panel de monitorizacion de hosts caidos (DOWN) con posibilidad de crear incidencias en lote. Gestión de la planta de equipos monitorizados: alta y baja de equipos en Nagios directamente desde BDU.

#### Informes
Generación automatica de informes operativos: Diario CGP Lote 1/3 (Excel y PDF), Diario interno, Semanal interno, Semanal Sergas CSV. Los informes se generan en segundo plano y se almacenan en el NAS.

#### Licencias
Gestión mensual de licencias de equipos: Cisco, OXE (Alcatel), SBC, NGN. Capturas de pantalla, importacion y generación de PDF.

#### KPIs Inelcom
Dashboard de cumplimiento de SLA sobre incidencias cerradas. 4 indicadores contractuales con semaforo verde/rojo. Detalle de incidencias fuera de SLA. Exportacion a Excel y PDF.

#### KPIs Nubodata
Dashboard de SLA para incidencias Nubodata (Material No Ibercom). Semaforo tricolor: verde (dentro de plazo), naranja (proximo a vencer), rojo (fuera de plazo). Exportacion a Excel y PDF.

#### KPIs CGE
Dashboard analitico de **volumen y tendencias** de incidencias cerradas (no SLA). 6 bloques: volumen anual por tipo, evolucion mensual comparada por año, top subtipos y centros, evolucion de los subtipos TOP, totales y variacion interanual y bloque especifico de **cortes electricos**. Filtros globales por años, tipos y area sanitaria. Datos desde 2022 en adelante. Exportacion a Excel y PDF con las gráficas embebidas.

#### Grilloweb
Gestión de suscripciones a alertas Grilloweb.

#### Plantillas
Generador de configuraciones de router (Cisco y Teldat) desde formularios web. Sustituye los antiguos Excel con macros y los programas Python heredados. Cuatro submodulos:
- **Completa**: configuración completa de un router Teldat para un centro nuevo (la plantilla se elige automáticamente según sede y rol).
- **Modificaciones**: alta de una VLAN nueva en Cisco o Teldat (incluye sede `FLEXWAN` en Teldat).
- **Traductor**: traducir ACLs Cisco ⇄ Teldat, renumerar entries Teldat, habilitar/deshabilitar ACLs en interfaces.
- **Migracion red 69→10**: **TEMPORAL.** Genera los 3 bloques de comandos (Preparativos / Migracion / Eliminacion) para migrar el direccionamiento del cliente.

Cada configuración generada se guarda automáticamente en `/mnt/centros/plantillas/<nemonico>/` para auditoria.

> **Nota:** El acceso a los módulos de KPIs (Inelcom, Nubodata, CGE) esta restringido a determinados usuarios según su grupo en el directorio.

![Panel de Mantenimiento con las tarjetas desplegables](./imagenes/captura-11-panel-de-mantenimiento-con-las-tarjetas.png)

> **Manual detallado:** `Mantenimiento/manual_mantenimiento.md`

---

### 3.9 Documentación

**Repositorio de documentos con conversion automatica a PDF.**

El módulo Documentación permite subir y gestionar la documentación interna del CGE:

- **Subida de ficheros:** se pueden subir documentos en cualquier formato (Word, Excel, PowerPoint, etc.)
- **Conversion automatica a PDF:** al subir un documento, se convierte automáticamente a PDF en segundo plano para facilitar su visualizacion
- **Visor integrado:** los PDF se pueden visualizar directamente en el navegador sin necesidad de descargarlos
- **Descarga del original:** siempre se puede descargar el fichero en su formato original
- **Filtros por tipo:** los documentos se organizan en carpetas/tipos configurados

![Listado de documentos con visor PDF integrado](./imagenes/captura-12-listado-de-documentos-con-visor-pdf-inte.png)

> **Manual detallado:** `Documentacion/manual_documentacion.md`

---

### 3.10 Info/Ayuda

**Enlaces utiles, contactos de escalado, tabla NAT/LAN2LAN.**

El módulo Info/Ayuda reune información de referencia organizada en tres secciones:

#### NAT LAN2LAN
Tabla de registros NAT con tarjetas de rangos y barras de uso. Estado automático según el campo IP outside: vacio = LIBRE, ping positivo = OCUPADO, resto = COMPROBAR. Filtros por busqueda libre, grupo, estado y ping. Exportacion a Excel y PDF.

#### Escalados / Directorio
Directorio de contactos de escalado organizados por secciones. Busqueda global entre todas las secciones. Exportacion a Excel y PDF por seccion.

#### Enlaces de Interes
Catalogo de enlaces utiles organizados por categorías con colores personalizables. Acceso rápido a herramientas externas y recursos del CGE.

> **Nota:** Las secciones de Info/Ayuda tienen un **modo editor** protegido con contraseña adicional para modificar los datos. Los operadores que solo necesitan consultar no necesitan esta contrasena.

![Vista del módulo Info/Ayuda con las tres secciones](./imagenes/captura-13-vista-del-modulo-info-ayuda-con-las-tres.png)

> **Manual detallado:** `Informacion/manual_informacion.md`

---

### 3.11 Mailviewer

**Visor de correos electronicos del buzon operativo.**

El módulo Mailviewer permite buscar y consultar los correos almacenados en el buzon operativo del CGE (más de 500.000 correos):

- **Busqueda:** por texto libre (asunto o cuerpo), remitente, carpeta y rango de fechas
- **Sin filtros:** muestra los últimos 500 correos agrupados por conversacion
- **Con filtros:** hasta 10.000 resultados
- **Agrupacion por conversacion:** los correos de un mismo hilo se agrupan automáticamente
- **Ver hilo completo:** se puede expandir una conversacion para ver todos los mensajes
- **Descarga .eml:** posibilidad de descargar cualquier correo en formato .eml
- **Ordenacion:** por fecha, remitente o asunto
- **Paginacion:** 50 resultados por pagina

![Vista de Mailviewer con resultados de busqueda y un correo abierto](./imagenes/captura-14-vista-de-mailviewer-con-resultados-de-bu.png)

> **Manual detallado:** `mailviewer/manual_mailviewer.md`

---

## 4. Funciones comunes

Las siguientes funcionalidades están disponibles en varios módulos de BDU.

### 4.1 Buscadores y autocompletados

Muchos módulos incluyen campos de busqueda con **autocompletado**: al escribir las primeras letras, aparece una lista de sugerencias que se puede seleccionar con el raton o con las flechas del teclado.

**Donde se encuentran:**

- **Centros:** buscador principal (busca por nombre, dirección, IdCliente, número de línea, administrativo, nemonico)
- **Instalaciones BJ:** autocompletado de centro al crear un pedido
- **Provision:** autocompletado en los formularios de alta y modificación
- **Correos:** autocompletado de centro en las plantillas que lo requieren

**Como usar el autocompletado:**

1. Escribir al menos 2-3 caracteres en el campo de busqueda
2. Esperar a que aparezca la lista de sugerencias
3. Seleccionar la opción deseada pulsando sobre ella o usando las flechas y Enter

### 4.2 Modo oscuro / modo claro

El modo oscuro esta disponible en **toda la aplicación** y en **todos los módulos**. Se activa y desactiva desde el boton en la barra superior (ver seccion [2.2](#22-modo-oscuro)).

La preferencia se guarda en el navegador, por lo que se mantiene entre sesiones. Al cambiar de módulo, el modo seleccionado se conserva.

### 4.3 Exportar datos (CSV, PDF, Excel)

Varios módulos permiten exportar los datos mostrados en pantalla. Los formatos disponibles dependen del modulo:

| Formato | Descripción | Disponible en |
|---|---|---|
| **CSV** | Fichero de texto separado por comas, abre en Excel | Consultas, Instalaciones |
| **PDF** | Documento PDF listo para imprimir | Consultas, KPIs, Informes, Info/Ayuda |
| **Excel (XLSX)** | Hoja de calculo Excel | Consultas, KPIs, Informes, Info/Ayuda |

**Como exportar:**

1. Realizar la consulta o abrir la vista deseada
2. Localizar los botones de exportacion (normalmente en la parte superior de la tabla de resultados)
3. Pulsar el boton del formato deseado
4. El fichero se descargara automáticamente

### 4.4 Copiar tablas al portapapeles

En el módulo **Correos**, la función principal es copiar una tabla formateada al portapapeles para pegarla directamente en un correo electronico.

**Como funciona:**

1. Rellenar los datos de la plantilla
2. Pulsar el boton de copiar/enviar
3. La tabla se copia al portapapeles
4. Abrir el cliente de correo (se abre automáticamente con el asunto predefinido)
5. Pegar la tabla en el cuerpo del correo (Ctrl+V)

### 4.5 Reportar incidencias de la aplicación (feedback)

Si se detecta un error en la aplicación BDU o se quiere sugerir una mejora:

1. Pulsar el icono de feedback (insecto) en la barra superior
2. Describir el problema o la sugerencia con el mayor detalle posible
3. Indicar en que módulo se encontro el problema y que se estaba haciendo
4. Enviar el reporte

> **Importante:** Este boton es para reportar problemas de la **herramienta BDU**, no para gestionar incidencias de red (para eso se usa el módulo Mantenimiento > Incidencias).

---

## 5. Preguntas frecuentes

### Por que me pide contraseña en Provision si ya estoy logueado?

El módulo Provision permite modificar datos criticos de la infraestructura de red (altas, bajas, modificaciones). Por seguridad, requiere una **contraseña adicional** compartida por el equipo, independiente de la contraseña de red.

Esta doble autenticación protege contra modificaciones accidentales y garantiza que solo personal autorizado realice cambios en la base de datos.

La misma contraseña adicional se utiliza también para:
- El modo editor en **Control de Cambios** (Consultas)
- El modo editor en **Info/Ayuda**

Si no se conoce esta contraseña, consultar con el responsable del equipo.

---

### Como cambio el modo oscuro?

Pulsar el boton con el icono de luna/sol en la barra superior derecha. El cambio es inmediato y se aplica a toda la aplicacion. La preferencia se guarda automáticamente en el navegador.

---

### Por que al buscar en Consultas recarga la pagina?

Actualmente, el módulo Consultas realiza la busqueda recargando la pagina completa. Esto es un comportamiento conocido. En futuras versiones esta previsto que la busqueda se realice sin recargar la pagina, actualizando solo la tabla de resultados.

---

### Donde están los manuales de cada modulo?

Cada módulo tiene su propio manual detallado. Ver la tabla completa en la seccion [6. Referencia de manuales](#6-referencia-de-manuales).

---

### La sesión ha expirado y he perdido lo que estaba haciendo, que paso?

La sesión de BDU expira automáticamente tras **30 minutos de inactividad** (sin hacer ninguna accion en la aplicación). Al expirar, se redirige a la pantalla de login con un aviso.

Para evitarlo, basta con interactuar periódicamente con la aplicación (cambiar de módulo, realizar una consulta, etc.).

---

### Que hago si me aparece un error o la pagina no carga correctamente?

1. Probar a recargar la pagina (F5 o Ctrl+R)
2. Si el error persiste, cerrar sesión y volver a entrar
3. Si sigue sin funcionar, reportar el problema con el boton de feedback (insecto) indicando que módulo y que accion se estaba realizando
4. Si la aplicación esta completamente inaccesible, contactar con el administrador del sistema

---

## 6. Funcionalidades transversales (sin manual propio)

Además de los módulos principales, BDU dispone de tres utilidades transversales
que aparecen integradas en la cabecera y no tienen un manual dedicado:

- **Avisos entre turnos**: sistema de mensajes que los operadores se dejan al
  cambio de turno. Permite listar los avisos pendientes, crear nuevos y
  marcarlos como resueltos. Util para registrar tareas en curso, incidencias
  abiertas o cualquier información que el siguiente turno deba conocer.

- **Buscador global**: caja de busqueda en la barra superior que consulta
  simultaneamente centros, líneas, equipos, BTPs e incidencias. Requiere al
  menos 2 caracteres y muestra hasta 15 resultados por categoria. Al pulsar
  un resultado se navega directamente al elemento.

- **Acerca de**: pantalla informativa con la versión actual de BDU, autor y
  contacto. Accesible desde el menu de ayuda.

---

## 7. Referencia de manuales

Cada módulo dispone de un manual detallado con instrucciones paso a paso. A continuacion se indica la ruta de cada manual:

| Módulo | Ruta del manual detallado |
|---|---|
| Inicio | `Inicio/manual_inicio.md` |
| Centros | `Centros/manual_centros.md` |
| Provision | `provision/manual_provision.md` |
| Instalaciones | `Instalaciones/manual_instalaciones.md` |
| Consultas | `Consultas/manual_consultas.md` |
| Stock | `Stock/manual_stock.md` |
| Correos | `Correos/manual_correos.md` |
| Mantenimiento | `Mantenimiento/manual_mantenimiento.md` |
| Plantillas (sub. de Mantenimiento) | `Plantillas/manual_plantillas.md` |
| Documentación | `Documentacion/manual_documentacion.md` |
| Info/Ayuda | `Informacion/manual_informacion.md` |
| Mailviewer | `mailviewer/manual_mailviewer.md` |

> **Nota:** Todos los manuales se encuentran dentro de la carpeta del proyecto `Web BDU/`, en la subcarpeta correspondiente a cada modulo.

---

*Manual generado en abril 2026. Versión 1.5 de BDU.*
