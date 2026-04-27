# BDU -- Manual de Usuario Global

| | |
|---|---|
| **Aplicacion** | BDU (Base de Datos Unificada) |
| **Version** | 1.5 |
| **Fecha** | Abril 2026 |
| **Para** | Operadores CGE SERGAS |

---

## Indice

1. [Introduccion](#1-introduccion)
2. [Navegacion general](#2-navegacion-general)
3. [Modulos](#3-modulos)
4. [Funciones comunes](#4-funciones-comunes)
5. [Preguntas frecuentes](#5-preguntas-frecuentes)
6. [Referencia de manuales](#6-referencia-de-manuales)

---

## 1. Introduccion

### 1.1 Que es BDU

BDU (Base de Datos Unificada) es la aplicacion web interna del Centro de Gestion (CGE) de Telefonica para el cliente SERGAS (Servicio Gallego de Salud). Permite gestionar de forma integral toda la infraestructura de red: centros sanitarios, lineas de datos y voz, equipos de comunicaciones, incidencias, provisiones, informes, documentacion y herramientas operativas del dia a dia.

En resumen, BDU es la herramienta principal de trabajo de los operadores del CGE para:

- Consultar informacion de centros sanitarios y su infraestructura de red
- Dar de alta, modificar o dar de baja elementos de red (lineas, equipos, centros)
- Gestionar incidencias y boletines de trabajo programado (BTPs)
- Generar correos operativos estandarizados
- Consultar y exportar datos en diferentes formatos
- Controlar el stock de equipos en almacenes
- Acceder a documentacion interna y enlaces utiles
- Monitorizar el estado de la infraestructura en tiempo real

### 1.2 Para quien es este manual

Este manual esta dirigido a los **operadores del CGE SERGAS** que utilizan BDU en su trabajo diario. No se requieren conocimientos tecnicos avanzados para seguir las instrucciones.

Cada modulo de BDU tiene su propio manual detallado con instrucciones paso a paso. Este documento ofrece una **vision global** de la aplicacion y sirve como punto de partida para familiarizarse con todas las funcionalidades disponibles.

### 1.3 Como acceder

**URL de acceso:**

| Entorno | URL |
|---|---|
| Produccion (PRO) | `https://bdu.sergascge.local` |
| Preproduccion (PRE) | `https://pre.bdu.sergascge.local` |

> **Nota:** La URL de preproduccion solo se utiliza para pruebas. El trabajo diario se realiza siempre en la URL de produccion.

**Pasos para acceder:**

1. Abrir el navegador web e introducir la URL de produccion
2. Aparecera la portada publica con el logotipo del CGE SERGAS y un boton **ACCEDER**
3. Pulsar **ACCEDER**
4. Introducir las credenciales del dominio (usuario y contrasena de red, las mismas que se usan para iniciar sesion en el ordenador)
5. Pulsar **Entrar**

![Pantalla de login con campos de usuario y contrasena](./imagenes/captura-01-pantalla-de-login-con-campos-de-usuario.png)

**Informacion importante sobre el acceso:**

- La autenticacion se realiza contra el directorio LDAP del dominio `sergascge.local`
- Tras **3 intentos fallidos** de contrasena, la cuenta se bloquea durante **5 minutos**
- La sesion expira automaticamente tras **30 minutos de inactividad**. Si esto ocurre, se redirige a la pantalla de login con un aviso de sesion expirada

---

## 2. Navegacion general

Una vez autenticado, la interfaz de BDU se compone de los siguientes elementos:

![Vista general de la aplicacion con los elementos de navegacion senalados](./imagenes/captura-02-vista-general-de-la-aplicacion-con-los-e.png)

### 2.1 Menu superior (barra de navegacion)

En la parte superior de la pantalla se encuentra la barra de navegacion con los modulos disponibles:

**Inicio** | **Centros** | **Provision** | **Instalaciones** | **Consultas** | **Stock** | **Correos** | **Mantenimiento** | **Documentacion** | **Info/Ayuda** | **Mailviewer**

- Pulsar sobre cualquier nombre de modulo para acceder a el
- El modulo activo se resalta visualmente para que siempre se sepa en que seccion se esta trabajando

### 2.2 Modo oscuro

En la barra superior, junto a los botones de utilidad, se encuentra el boton de modo oscuro/claro:

- Pulsar el icono de luna para activar el **modo oscuro** (fondo oscuro, texto claro)
- Pulsar el icono de sol para volver al **modo claro** (fondo blanco, texto oscuro)
- La preferencia se guarda automaticamente en el navegador: al volver a entrar, se mantiene el ultimo modo seleccionado

![Boton de modo oscuro en la barra superior](./imagenes/captura-03-boton-de-modo-oscuro-en-la-barra-superio.png)

### 2.3 Boton de feedback

El icono con forma de insecto permite **reportar incidencias o sugerencias** sobre la propia aplicacion BDU.

- Pulsar el icono para abrir el formulario de feedback
- Describir el problema o la sugerencia
- Enviar el reporte

Este boton no esta relacionado con las incidencias de red; es exclusivamente para comunicar fallos o mejoras de la herramienta BDU.

### 2.4 Acerca de

El icono de informacion abre una ventana con los datos de la version actual de BDU, incluyendo:

- Numero de version
- Informacion del desarrollador
- Datos de contacto

### 2.5 Cerrar sesion

Para cerrar la sesion de forma segura:

1. Pulsar el boton de **Cerrar sesion** en la parte derecha de la barra superior
2. Se vuelve a la portada publica

> **Importante:** Si simplemente se cierra el navegador sin cerrar sesion, esta expirara automaticamente a los 30 minutos.

---

## 3. Modulos

A continuacion se describe brevemente cada modulo. Para instrucciones detalladas, consultar el manual especifico de cada uno (ver seccion [6. Referencia de manuales](#6-referencia-de-manuales)).

---

### 3.1 Inicio

**Panel de control con KPIs y estado de la infraestructura.**

Al entrar en BDU, el modulo Inicio muestra un panel con la vision global del estado de la plataforma:

- **KPIs de centros:** total de centros, activos, cerrados, alta prioridad, FlexWAN, DCT
- **Graficos:** tipo de sede, lineas activas por tipo, equipos gestionados, equipos por modelo (top 12)
- **Incidencias:** resumen de incidencias abiertas clasificadas por tipo
- **Pedidos pendientes:** estado de instalaciones en curso
- **Infraestructura:** estado de los servidores Proxmox, NAS y base de datos

Los datos se actualizan automaticamente cada 2 minutos. Este modulo es solo de lectura (no se modifican datos).

![Panel de Inicio con KPIs y graficos](./imagenes/captura-04-panel-de-inicio-con-kpis-y-graficos.png)

> **Manual detallado:** `Inicio/manual_inicio.md`

---

### 3.2 Centros

**Buscador y ficha completa de centros de salud.**

El modulo Centros permite buscar cualquier centro sanitario del SERGAS y ver toda su informacion de red:

- **Buscador inteligente** con autocompletado: busca por nombre del centro, direccion, IdCliente, numero de linea, administrativo o nemonico de equipo
- **Ficha del centro** con datos generales, comentarios editables y estado Nagios en tiempo real
- **Lineas de datos** con detalle completo (linea, equipo, VLANs)
- **Lineas de voz**
- **Equipos de voz** con imagen del modelo
- **Equipos de segundo nivel** con imagen del modelo
- **Documentacion del centro** almacenada en el NAS (subida de archivos, carpetas, visor integrado)

![Ficha de un centro con sus lineas y equipos](./imagenes/captura-05-ficha-de-un-centro-con-sus-lineas-y-equi.png)

> **Manual detallado:** `Centros/manual_centros.md`

---

### 3.3 Provision

**Altas, bajas y modificaciones de elementos de red.**

El modulo Provision permite gestionar el ciclo de vida de la infraestructura:

- **Altas:** centro nuevo, linea de datos con equipo, linea de voz, equipo de voz, equipo de segundo nivel
- **Modificaciones:** edicion campo a campo de cualquier elemento existente
- **Bajas:** eliminacion de elementos individuales o cierre completo de un centro
- **Registro:** todas las acciones quedan registradas con usuario, fecha y detalle

**Acceso con contrasena adicional:**

Al entrar en Provision, se solicita una contrasena adicional ademas de la sesion LDAP ya iniciada. Esta contrasena es compartida por el equipo y protege las operaciones de modificacion de datos.

![Menu principal de Provision con las opciones de alta, baja y modificacion](./imagenes/captura-06-menu-principal-de-provision-con-las-opci.png)

> **Manual detallado:** `provision/manual_provision.md`

---

### 3.4 Instalaciones

**Gestion de instalaciones LOGOS, BJ, ATLAS y proyectos de red.**

Este modulo gestiona los pedidos e instalaciones de infraestructura, organizado en pestanas:

- **LOGOS (datos):** pedidos de instalaciones de datos importados via CSV. Vista de pedidos activos e historico. Panel dividido con lista lateral y detalle
- **BJ (voz):** pedidos de instalaciones de voz con autocompletado de centro. Activos e historico. Integracion con tuberias Indico
- **ATLAS:** ordenes importadas desde ficheros Excel. Cruces automaticos con pedidos LOGOS y datos de centros
- **Calendario:** vista mensual y semanal de instalaciones programadas con colores por tipo. Exportacion para impresion y copia para Outlook
- **Proyectos:** estadisticas agregadas de proyectos del CGE

![Vista de Instalaciones con las pestanas LOGOS, BJ, ATLAS, Calendario y Proyectos](./imagenes/captura-07-vista-de-instalaciones-con-las-pestanas.png)

> **Manual detallado:** `Instalaciones/manual_instalaciones.md`

---

### 3.5 Consultas

**Consultas predefinidas con exportacion CSV/PDF/Excel.**

El modulo Consultas ofrece un conjunto de consultas preparadas sobre los datos de BDU:

- Centros con Dispositivo de Tension
- Lineas Activas con EDC
- Mantenimiento Equipos Satec
- Lineas Datos / Lineas Voz
- Equipos Voz / Equipos 2o Nivel
- Diversificacion
- Circuitos por Nodo
- Control de Cambios (con modo editor para edicion inline)

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

El modulo Stock permite gestionar el inventario de equipos en los almacenes provinciales:

- **Stock EECC:** stock clasificado por empresa colaboradora
- **Stock Almacen:** stock clasificado por ubicacion fisica
- Actualizacion de cantidades
- Exportacion de datos

![Vista del modulo Stock con listado de equipos](./imagenes/captura-09-vista-del-modulo-stock-con-listado-de-eq.png)

> **Manual detallado:** `Stock/manual_stock.md`

---

### 3.7 Correos

**Generador de correos con plantillas predefinidas.**

El modulo Correos permite generar correos operativos estandarizados de forma rapida. Las plantillas garantizan que la informacion se envia siempre con el formato correcto.

**Categorias de plantillas disponibles:**

- **Averias Datos:** centro incomunicado, corte electrico, linea caida, masiva, Artemis, DWDM
- **Averias Voz:** Sirios, GLPI, IVR, tarificador, grabadoras, SIRIO, nodo EB, medidas radio, red inteligente
- **Soporte TI L3:** Satec, Ednon, Plexus, RightFax, tensiometro
- **Escalados:** Ibercom, CTM, Mesa Nacional
- **Satec:** VPN-IP, contingencia, boton rojo, tecnico campo, SIRIO
- **Varios CGE:** cambio turno, informe Sergas, informe Telefonica

**Funcionamiento basico:**

1. Seleccionar la categoria
2. Seleccionar la plantilla
3. Rellenar los datos solicitados
4. Pulsar el boton para copiar la tabla al portapapeles y abrir el cliente de correo con el asunto y cuerpo predefinidos

![Seleccion de plantilla de correo y formulario de datos](./imagenes/captura-10-seleccion-de-plantilla-de-correo-y-formu.png)

> **Manual detallado:** `Correos/manual_correos.md`

---

### 3.8 Mantenimiento

**BTPs, Tareas automatizadas, Incidencias, Licencias, KPIs, Nagios, Informes, Grilloweb.**

El modulo Mantenimiento agrupa varias herramientas operativas organizadas en tarjetas desplegables:

#### BTPs (Boletines de Trabajo Programado)
Gestion de BTPs recibidos de Telefonica: importacion desde Excel, consulta por numero o estado, marcado como informado, edicion de detalles (estado, afectacion, fechas), generacion de correo de revision diaria.

#### Tareas
Herramientas de automatizacion de red:
- **Config Planta (datos y voz):** configuracion automatica de equipos via SSH
- **Gentest 5G:** test BGP y reset radio en equipos 5G
- **Config Serial:** extraccion de numeros de serie via SSH
- **LOGOS-PT:** comparacion de CSV con base de datos
- **Importar seriales:** actualizacion de la base de datos desde logs historicos

#### Incidencias
Gestion completa de incidencias de red: creacion, edicion, acciones, cierre. Vista de activas y cerradas. Panel lateral con listado y area de detalle. Tipos: VOZ, DATOS, SOP TI L1/L3, Modificaciones. Validaciones temporales automaticas.

#### DDIs GDIA
Gestion de DDIs (numeros de marcacion directa) para incidencias GDIA.

#### Nagios
Panel de monitorizacion de hosts caidos (DOWN) con posibilidad de crear incidencias en lote. Gestion de la planta de equipos monitorizados: alta y baja de equipos en Nagios directamente desde BDU.

#### Informes
Generacion automatica de informes operativos: Diario CGP Lote 1/3 (Excel y PDF), Diario interno, Semanal interno, Semanal Sergas CSV. Los informes se generan en segundo plano y se almacenan en el NAS.

#### Licencias
Gestion mensual de licencias de equipos: Cisco, OXE (Alcatel), SBC, NGN. Capturas de pantalla, importacion y generacion de PDF.

#### KPIs Inelcom
Dashboard de cumplimiento de SLA sobre incidencias cerradas. 4 indicadores contractuales con semaforo verde/rojo. Detalle de incidencias fuera de SLA. Exportacion a Excel y PDF.

#### KPIs Nubodata
Dashboard de SLA para incidencias Nubodata (Material No Ibercom). Semaforo tricolor: verde (dentro de plazo), naranja (proximo a vencer), rojo (fuera de plazo). Exportacion a Excel y PDF.

#### KPIs CGE
Dashboard analitico de **volumen y tendencias** de incidencias cerradas (no SLA). 6 bloques: volumen anual por tipo, evolucion mensual comparada por año, top subtipos y centros, evolucion de los subtipos TOP, totales y variacion interanual y bloque especifico de **cortes electricos**. Filtros globales por años, tipos y area sanitaria. Datos desde 2022 en adelante. Exportacion a Excel y PDF con las graficas embebidas.

#### Grilloweb
Gestion de suscripciones a alertas Grilloweb.

#### Plantillas
Generador de configuraciones de router (Cisco y Teldat) desde formularios web. Sustituye los antiguos Excel con macros y los programas Python heredados. Cuatro submodulos:
- **Completa**: configuracion completa de un router Teldat para un centro nuevo (la plantilla se elige automaticamente segun sede y rol).
- **Modificaciones**: alta de una VLAN nueva en Cisco o Teldat (incluye sede `FLEXWAN` en Teldat).
- **Traductor**: traducir ACLs Cisco ⇄ Teldat, renumerar entries Teldat, habilitar/deshabilitar ACLs en interfaces.
- **Migracion red 69→10**: **TEMPORAL.** Genera los 3 bloques de comandos (Preparativos / Migracion / Eliminacion) para migrar el direccionamiento del cliente.

Cada configuracion generada se guarda automaticamente en `/mnt/centros/plantillas/<nemonico>/` para auditoria.

> **Nota:** El acceso a los modulos de KPIs (Inelcom, Nubodata, CGE) esta restringido a determinados usuarios segun su grupo en el directorio.

![Panel de Mantenimiento con las tarjetas desplegables](./imagenes/captura-11-panel-de-mantenimiento-con-las-tarjetas.png)

> **Manual detallado:** `Mantenimiento/manual_mantenimiento.md`

---

### 3.9 Documentacion

**Repositorio de documentos con conversion automatica a PDF.**

El modulo Documentacion permite subir y gestionar la documentacion interna del CGE:

- **Subida de ficheros:** se pueden subir documentos en cualquier formato (Word, Excel, PowerPoint, etc.)
- **Conversion automatica a PDF:** al subir un documento, se convierte automaticamente a PDF en segundo plano para facilitar su visualizacion
- **Visor integrado:** los PDF se pueden visualizar directamente en el navegador sin necesidad de descargarlos
- **Descarga del original:** siempre se puede descargar el fichero en su formato original
- **Filtros por tipo:** los documentos se organizan en carpetas/tipos configurados

![Listado de documentos con visor PDF integrado](./imagenes/captura-12-listado-de-documentos-con-visor-pdf-inte.png)

> **Manual detallado:** `Documentacion/manual_documentacion.md`

---

### 3.10 Info/Ayuda

**Enlaces utiles, contactos de escalado, tabla NAT/LAN2LAN.**

El modulo Info/Ayuda reune informacion de referencia organizada en tres secciones:

#### NAT LAN2LAN
Tabla de registros NAT con tarjetas de rangos y barras de uso. Estado automatico segun el campo IP outside: vacio = LIBRE, ping positivo = OCUPADO, resto = COMPROBAR. Filtros por busqueda libre, grupo, estado y ping. Exportacion a Excel y PDF.

#### Escalados / Directorio
Directorio de contactos de escalado organizados por secciones. Busqueda global entre todas las secciones. Exportacion a Excel y PDF por seccion.

#### Enlaces de Interes
Catalogo de enlaces utiles organizados por categorias con colores personalizables. Acceso rapido a herramientas externas y recursos del CGE.

> **Nota:** Las secciones de Info/Ayuda tienen un **modo editor** protegido con contrasena adicional para modificar los datos. Los operadores que solo necesitan consultar no necesitan esta contrasena.

![Vista del modulo Info/Ayuda con las tres secciones](./imagenes/captura-13-vista-del-modulo-info-ayuda-con-las-tres.png)

> **Manual detallado:** `Informacion/manual_informacion.md`

---

### 3.11 Mailviewer

**Visor de correos electronicos del buzon operativo.**

El modulo Mailviewer permite buscar y consultar los correos almacenados en el buzon operativo del CGE (mas de 500.000 correos):

- **Busqueda:** por texto libre (asunto o cuerpo), remitente, carpeta y rango de fechas
- **Sin filtros:** muestra los ultimos 500 correos agrupados por conversacion
- **Con filtros:** hasta 10.000 resultados
- **Agrupacion por conversacion:** los correos de un mismo hilo se agrupan automaticamente
- **Ver hilo completo:** se puede expandir una conversacion para ver todos los mensajes
- **Descarga .eml:** posibilidad de descargar cualquier correo en formato .eml
- **Ordenacion:** por fecha, remitente o asunto
- **Paginacion:** 50 resultados por pagina

![Vista de Mailviewer con resultados de busqueda y un correo abierto](./imagenes/captura-14-vista-de-mailviewer-con-resultados-de-bu.png)

> **Manual detallado:** `mailviewer/manual_mailviewer.md`

---

## 4. Funciones comunes

Las siguientes funcionalidades estan disponibles en varios modulos de BDU.

### 4.1 Buscadores y autocompletados

Muchos modulos incluyen campos de busqueda con **autocompletado**: al escribir las primeras letras, aparece una lista de sugerencias que se puede seleccionar con el raton o con las flechas del teclado.

**Donde se encuentran:**

- **Centros:** buscador principal (busca por nombre, direccion, IdCliente, numero de linea, administrativo, nemonico)
- **Instalaciones BJ:** autocompletado de centro al crear un pedido
- **Provision:** autocompletado en los formularios de alta y modificacion
- **Correos:** autocompletado de centro en las plantillas que lo requieren

**Como usar el autocompletado:**

1. Escribir al menos 2-3 caracteres en el campo de busqueda
2. Esperar a que aparezca la lista de sugerencias
3. Seleccionar la opcion deseada pulsando sobre ella o usando las flechas y Enter

### 4.2 Modo oscuro / modo claro

El modo oscuro esta disponible en **toda la aplicacion** y en **todos los modulos**. Se activa y desactiva desde el boton en la barra superior (ver seccion [2.2](#22-modo-oscuro)).

La preferencia se guarda en el navegador, por lo que se mantiene entre sesiones. Al cambiar de modulo, el modo seleccionado se conserva.

### 4.3 Exportar datos (CSV, PDF, Excel)

Varios modulos permiten exportar los datos mostrados en pantalla. Los formatos disponibles dependen del modulo:

| Formato | Descripcion | Disponible en |
|---|---|---|
| **CSV** | Fichero de texto separado por comas, abre en Excel | Consultas, Instalaciones |
| **PDF** | Documento PDF listo para imprimir | Consultas, KPIs, Informes, Info/Ayuda |
| **Excel (XLSX)** | Hoja de calculo Excel | Consultas, KPIs, Informes, Info/Ayuda |

**Como exportar:**

1. Realizar la consulta o abrir la vista deseada
2. Localizar los botones de exportacion (normalmente en la parte superior de la tabla de resultados)
3. Pulsar el boton del formato deseado
4. El fichero se descargara automaticamente

### 4.4 Copiar tablas al portapapeles

En el modulo **Correos**, la funcion principal es copiar una tabla formateada al portapapeles para pegarla directamente en un correo electronico.

**Como funciona:**

1. Rellenar los datos de la plantilla
2. Pulsar el boton de copiar/enviar
3. La tabla se copia al portapapeles
4. Abrir el cliente de correo (se abre automaticamente con el asunto predefinido)
5. Pegar la tabla en el cuerpo del correo (Ctrl+V)

### 4.5 Reportar incidencias de la aplicacion (feedback)

Si se detecta un error en la aplicacion BDU o se quiere sugerir una mejora:

1. Pulsar el icono de feedback (insecto) en la barra superior
2. Describir el problema o la sugerencia con el mayor detalle posible
3. Indicar en que modulo se encontro el problema y que se estaba haciendo
4. Enviar el reporte

> **Importante:** Este boton es para reportar problemas de la **herramienta BDU**, no para gestionar incidencias de red (para eso se usa el modulo Mantenimiento > Incidencias).

---

## 5. Preguntas frecuentes

### Por que me pide contrasena en Provision si ya estoy logueado?

El modulo Provision permite modificar datos criticos de la infraestructura de red (altas, bajas, modificaciones). Por seguridad, requiere una **contrasena adicional** compartida por el equipo, independiente de la contrasena de red.

Esta doble autenticacion protege contra modificaciones accidentales y garantiza que solo personal autorizado realice cambios en la base de datos.

La misma contrasena adicional se utiliza tambien para:
- El modo editor en **Control de Cambios** (Consultas)
- El modo editor en **Info/Ayuda**

Si no se conoce esta contrasena, consultar con el responsable del equipo.

---

### Como cambio el modo oscuro?

Pulsar el boton con el icono de luna/sol en la barra superior derecha. El cambio es inmediato y se aplica a toda la aplicacion. La preferencia se guarda automaticamente en el navegador.

---

### Por que al buscar en Consultas recarga la pagina?

Actualmente, el modulo Consultas realiza la busqueda recargando la pagina completa. Esto es un comportamiento conocido. En futuras versiones esta previsto que la busqueda se realice sin recargar la pagina, actualizando solo la tabla de resultados.

---

### Donde estan los manuales de cada modulo?

Cada modulo tiene su propio manual detallado. Ver la tabla completa en la seccion [6. Referencia de manuales](#6-referencia-de-manuales).

---

### La sesion ha expirado y he perdido lo que estaba haciendo, que paso?

La sesion de BDU expira automaticamente tras **30 minutos de inactividad** (sin hacer ninguna accion en la aplicacion). Al expirar, se redirige a la pantalla de login con un aviso.

Para evitarlo, basta con interactuar periodicamente con la aplicacion (cambiar de modulo, realizar una consulta, etc.).

---

### Que hago si me aparece un error o la pagina no carga correctamente?

1. Probar a recargar la pagina (F5 o Ctrl+R)
2. Si el error persiste, cerrar sesion y volver a entrar
3. Si sigue sin funcionar, reportar el problema con el boton de feedback (insecto) indicando que modulo y que accion se estaba realizando
4. Si la aplicacion esta completamente inaccesible, contactar con el administrador del sistema

---

## 6. Funcionalidades transversales (sin manual propio)

Ademas de los modulos principales, BDU dispone de tres utilidades transversales
que aparecen integradas en la cabecera y no tienen un manual dedicado:

- **Avisos entre turnos**: sistema de mensajes que los operadores se dejan al
  cambio de turno. Permite listar los avisos pendientes, crear nuevos y
  marcarlos como resueltos. Util para registrar tareas en curso, incidencias
  abiertas o cualquier informacion que el siguiente turno deba conocer.

- **Buscador global**: caja de busqueda en la barra superior que consulta
  simultaneamente centros, lineas, equipos, BTPs e incidencias. Requiere al
  menos 2 caracteres y muestra hasta 15 resultados por categoria. Al pulsar
  un resultado se navega directamente al elemento.

- **Acerca de**: pantalla informativa con la version actual de BDU, autor y
  contacto. Accesible desde el menu de ayuda.

---

## 7. Referencia de manuales

Cada modulo dispone de un manual detallado con instrucciones paso a paso. A continuacion se indica la ruta de cada manual:

| Modulo | Ruta del manual detallado |
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
| Documentacion | `Documentacion/manual_documentacion.md` |
| Info/Ayuda | `Informacion/manual_informacion.md` |
| Mailviewer | `mailviewer/manual_mailviewer.md` |

> **Nota:** Todos los manuales se encuentran dentro de la carpeta del proyecto `Web BDU/`, en la subcarpeta correspondiente a cada modulo.

---

*Manual generado en abril 2026. Version 1.5 de BDU.*
