# Manual de Usuario -- Modulo Correos

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Correos                        |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al modulo Correos](#1-acceder-al-modulo-correos)
2. [Menu de categorias](#2-menu-de-categorias)
3. [Generar un correo con datos de centro](#3-generar-un-correo-con-datos-de-centro)
4. [Generar un correo con seleccion de lineas](#4-generar-un-correo-con-seleccion-de-lineas)
5. [Incidencia masiva](#5-incidencia-masiva)
6. [Correos de escalado](#6-correos-de-escalado)
7. [Correos simples (sin centro)](#7-correos-simples-sin-centro)
8. [Cambio de turno y otros correos internos](#8-cambio-de-turno-y-otros-correos-internos)
9. [Crear incidencia desde un correo](#9-crear-incidencia-desde-un-correo)
10. [Tipos de plantillas disponibles](#10-tipos-de-plantillas-disponibles)

---

## 1. Acceder al modulo Correos

1. Abre la aplicacion Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Correos**.
3. Aparecera el menu principal con todas las plantillas de correo organizadas por categorias.

[CAPTURA: Menu principal del modulo Correos mostrando las 6 categorias con sus tarjetas]

> Para volver al menu principal desde cualquier correo, haz clic en el enlace **"Volver a correos"** que aparece en la parte superior.

---

## 2. Menu de categorias

El menu principal esta organizado en **6 categorias**:

| Categoria          | Contenido                                                            |
|--------------------|----------------------------------------------------------------------|
| **Averias Datos**  | Centro incomunicado, Corte electrico, Linea caida, Masiva, Artemis, DWDM |
| **Averias Voz**    | Sirios, GLPI, IVR CISCO, Tarificador, NICE, Infomicro, SIRIO Gotor, Nodo EB, Radio, RI |
| **Sop. TI L3**    | Satec L3, Ednon L3, Plexus L3, RightFax L3, Tensiometro             |
| **Escalados**      | Escalado Ibercom, Escalado CTM, Mesa Nacional                        |
| **Satec**          | VPN-IP, Contingencia, Boton Rojo, Tecnico Campo, Satec Sirio         |
| **Varios CGE**     | Cambio turno, Informe Sergas, Informe Telefonica                     |

Cada tarjeta tiene un icono y un nombre descriptivo. Haz clic en la que necesites para empezar a generar el correo.

---

## 3. Generar un correo con datos de centro

Este es el flujo mas habitual. Se usa para correos como "Centro incomunicado", "Linea datos caida", escalados, etc.

### Paso 1 -- Buscar el centro

1. Haz clic en la plantilla de correo que necesites.
2. Aparecera un campo de busqueda de centros.
3. Empieza a escribir el nombre del centro (minimo 2 caracteres).
4. Selecciona el centro de la lista de sugerencias.
5. Haz clic en **Buscar** o pulsa Enter.

[CAPTURA: Buscador de centros con sugerencias de autocompletado desplegadas]

### Paso 2 -- Rellenar los campos del correo

1. Se mostrara un formulario con los campos especificos de esa plantilla.
2. Rellena los campos necesarios (urgencia, descripcion, ticket, etc.).
3. Algunos campos son desplegables (selecciona una opcion de la lista).
4. Otros son campos de texto libre.
5. Haz clic en **Generar correo** (o el boton de enviar).

[CAPTURA: Formulario de campos de una plantilla con varios campos rellenos y el boton de generar]

### Paso 3 -- Copiar la tabla y abrir el correo

1. Se generara la tabla con los datos del centro y los campos que rellenaste.
2. Haz clic en **Copiar tabla** para copiar la tabla al portapapeles con formato.
3. Automaticamente se abrira tu cliente de correo (Outlook, Thunderbird, etc.) con:
   - **Destinatario** (Para) ya relleno
   - **CC** ya relleno (si aplica)
   - **Asunto** ya relleno con los datos del centro
   - **Cuerpo** con el texto base del correo
4. Pega la tabla en el cuerpo del correo con **Ctrl+V**.
5. Revisa el correo y envialo.

[CAPTURA: Resultado del correo generado mostrando la tabla, el boton "Copiar tabla" y el enlace de correo]

> **Importante:** La tabla se copia con formato HTML (bordes, colores de cabecera). Al pegar en el correo se vera como una tabla con formato.

---

## 4. Generar un correo con seleccion de lineas

Algunas plantillas (como "Centro incomunicado", "Corte electrico", "Linea datos caida") permiten seleccionar lineas especificas del centro.

### Paso 1 -- Buscar el centro

1. Sigue los mismos pasos que en la seccion anterior para buscar y seleccionar el centro.

### Paso 2 -- Seleccionar las lineas afectadas

1. Aparecera una tabla con todas las lineas activas del centro.
2. Cada linea muestra: Funcion, Numero, Nemonico.
3. Marca las casillas de las lineas que estan afectadas.
4. Haz clic en **Continuar** (o en el boton de siguiente paso).

[CAPTURA: Tabla de seleccion de lineas con casillas de verificacion, algunas marcadas]

### Paso 3 -- Opciones adicionales

1. Segun la plantilla, puede aparecer una pregunta adicional (por ejemplo: "Es incidencia masiva? SI / NO").
2. Selecciona la opcion que corresponda.
3. Se generara la tabla con una fila por cada linea seleccionada.

### Paso 4 -- Copiar y enviar

1. Haz clic en **Copiar tabla** para copiar la tabla al portapapeles.
2. Se abrira el cliente de correo automaticamente.
3. Pega la tabla con **Ctrl+V** y envia.

La tabla generada incluye columnas como: Centro, Horario, Tipo Linea, Descripcion, Apertura, Estado, etc.

---

## 5. Incidencia masiva

La plantilla de **Incidencia masiva** permite acumular lineas de varios centros en un unico correo.

### Paso 1 -- Introducir el numero de incidencia

1. Al seleccionar "Incidencia masiva", lo primero que pedira es el **numero de incidencia de Telefonica**.
2. Escribe el numero y pulsa **Continuar**.

[CAPTURA: Formulario pidiendo el numero de incidencia de Telefonica]

### Paso 2 -- Anadir centros y lineas

1. Busca el primer centro afectado.
2. Selecciona las lineas afectadas de ese centro.
3. Las lineas se anadiran a un **panel acumulativo** que muestra todos los centros agregados.
4. Haz clic en **Anadir mas centros** para repetir el proceso con otro centro.
5. Puedes quitar lineas individuales del panel haciendo clic en el boton de eliminar.

[CAPTURA: Panel acumulativo de incidencia masiva mostrando lineas de varios centros con opcion de quitar]

### Paso 3 -- Generar el correo

1. Cuando hayas anadido todos los centros afectados, genera el correo.
2. La tabla incluira todas las lineas de todos los centros seleccionados.
3. Copia la tabla y enviala por correo como en los pasos habituales.

### Empezar de nuevo

- Haz clic en **Nueva incidencia masiva** para limpiar todo y empezar una nueva incidencia masiva desde cero.

---

## 6. Correos de escalado

Los escalados (Ibercom, CTM Zaragoza, Mesa Nacional) incluyen datos corporativos fijos del SERGAS.

### Flujo

1. Selecciona la plantilla de escalado.
2. Busca y selecciona el centro afectado.
3. Rellena los campos del operador:
   - Administrativo / ID del elemento afectado
   - Breve descripcion del problema
   - Impacto en el cliente
   - Diagnostico
4. La tabla se generara con datos fijos corporativos (Director de Oficina, GST, Jefe de Sector, etc.) junto con los datos del centro y los campos que rellenaste.
5. Copia la tabla y envia el correo.

[CAPTURA: Tabla de escalado mostrando datos corporativos fijos y campos rellenos por el operador]

---

## 7. Correos simples (sin centro)

Algunas plantillas tienen un centro fijo predefinido o no requieren seleccionar centro. En estos casos:

1. Haz clic en la plantilla.
2. Rellena los campos solicitados.
3. Se generara el correo directamente.
4. Copia y envia.

Ejemplos: plantillas de Satec, Lote 3 (soporte TI), etc.

---

## 8. Cambio de turno y otros correos internos

Las plantillas de la categoria **Varios CGE** funcionan de manera especial:

### Cambio de turno

1. Haz clic en **Cambio turno** en la categoria "Varios CGE".
2. Se mostrara la plantilla del correo de cambio de turno con formato de tablas.
3. Rellena la informacion correspondiente.
4. Copia la tabla con **Copiar tabla** y pega en el correo.

[CAPTURA: Plantilla de cambio de turno mostrando el formato con tablas]

### Informe Sergas / Informe Telefonica

1. Haz clic en la plantilla correspondiente.
2. Se mostrara el formulario del informe.
3. Rellena los datos y genera el correo.

> Estas plantillas se cargan directamente sin pasar por el buscador de centros.

---

## 9. Crear incidencia desde un correo

Muchas plantillas de correo permiten crear automaticamente una incidencia en la base de datos despues de generar el correo.

### Como funciona

1. Genera el correo normalmente (buscar centro, rellenar campos, etc.).
2. Despues de copiar la tabla (o abrir el correo), se activara el boton **Crear incidencia**.
   - El boton aparece deshabilitado (gris) hasta que copies la tabla o abras el correo.
3. Haz clic en **Crear incidencia**.
4. Se creara automaticamente una incidencia en el sistema con los datos del correo:
   - Centro, tipo de incidencia, subtipo, urgencia, ticket, estado, etc.
5. Seras redirigido al modulo de Mantenimiento (seccion Incidencias) para ver la incidencia creada.

[CAPTURA: Boton "Crear incidencia" activado (azul) despues de copiar la tabla]

> **Nota:** El sistema verifica automaticamente si ya existe una incidencia activa para el mismo equipo, evitando duplicados.

> **Importante:** El boton solo se activa despues de copiar la tabla o abrir el correo, para asegurarse de que se ha enviado la comunicacion antes de registrar la incidencia.

---

## 10. Tipos de plantillas disponibles

### Averias Datos (6 plantillas)

| Plantilla               | Requiere         | Seleccion lineas | Incidencia automatica |
|--------------------------|------------------|------------------|-----------------------|
| Centro incomunicado      | Buscar centro    | Si               | Si                    |
| Corte electrico          | Buscar centro    | Si               | Si                    |
| Linea datos caida        | Buscar centro    | Si               | Si                    |
| Incidencia masiva        | N.o incidencia + multiples centros | Si | Si               |
| Incidencia Artemis       | Buscar centro    | No               | Si                    |
| Averia DWDM              | Buscar centro    | No               | No                    |

### Averias Voz (11 plantillas)

| Plantilla                | Requiere         |
|--------------------------|------------------|
| Sirios pendientes        | Carga directa    |
| GLPI Nubodata            | Buscar centro    |
| GLPI pendientes          | Carga directa    |
| IVR CISCO                | Buscar centro    |
| Tarificador              | Buscar centro    |
| Grabadoras NICE          | Buscar centro    |
| Grabadoras Infomicro     | Buscar centro    |
| SIRIO Gotor              | Buscar centro    |
| Nodo EB movil            | Buscar centro    |
| Medidas Radio            | Buscar centro    |
| Red Inteligente          | Buscar centro    |

### Soporte TI L3, Escalados, Satec y Varios CGE

Cada una tiene sus plantillas especificas. El flujo es siempre el mismo:
1. Seleccionar plantilla
2. Buscar centro (si aplica)
3. Rellenar campos
4. Copiar tabla y abrir correo

---

## Resumen rapido

| Accion                          | Como hacerlo                                           |
|---------------------------------|--------------------------------------------------------|
| Volver al menu                  | Enlace "Volver a correos" en la parte superior         |
| Buscar centro                   | Escribir nombre (minimo 2 caracteres) + seleccionar    |
| Rellenar campos                 | Completar el formulario y pulsar el boton de generar   |
| Copiar tabla                    | Boton "Copiar tabla" (se copia con formato para correo)|
| Abrir correo                    | Se abre automaticamente al copiar, o boton "Abrir correo" |
| Crear incidencia                | Boton "Crear incidencia" (se activa tras copiar tabla) |
| Incidencia masiva               | Agregar centros uno a uno al panel acumulativo         |
| Nueva incidencia masiva         | Boton "Nueva incidencia masiva" para empezar de cero   |

---

*Fin del manual -- Modulo Correos v1.5*
