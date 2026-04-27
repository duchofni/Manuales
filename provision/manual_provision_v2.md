# Manual de Usuario -- Módulo Provision

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Módulo**  | Provision                      |
| **Versión** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al módulo Provision](#1-acceder-al-modulo-provision)
2. [Menu de opciones](#2-menu-de-opciones)
3. [Alta de centro](#3-alta-de-centro)
4. [Alta de línea de datos](#4-alta-de-linea-de-datos)
5. [Alta de línea de voz](#5-alta-de-linea-de-voz)
6. [Alta de equipo de voz](#6-alta-de-equipo-de-voz)
7. [Alta de equipo de 2.o nivel](#7-alta-de-equipo-de-2o-nivel)
8. [Modificaciones](#8-modificaciones)
9. [Bajas](#9-bajas)

---

## 1. Acceder al módulo Provision

El módulo Provision requiere una **contraseña adicional** además de tu sesión normal.

1. Abre la aplicación Web BDU en tu navegador.
2. En el menu lateral, haz clic en **Provision**.
3. Aparecerá una pantalla de login.
4. Introduce la contraseña de provision y haz clic en **Entrar**.
5. Si la contraseña es correcta, accederas al menu principal.

![Pantalla de login de Provision con el campo de contraseña y el boton Entrar](./imagenes/captura-01-pantalla-de-login-de-provision-con-el-ca.png)

> **Atencion:** Si introduces la contraseña incorrecta **3 veces seguidas**, tu acceso se bloqueara durante **5 minutos**.

Para **cerrar sesión** de Provision, haz clic en el boton de logout en la parte superior.

---

## 2. Menu de opciones

Una vez dentro, veras un menu con tarjetas para cada opción disponible:

| Opción                   | Descripción                                    |
|--------------------------|------------------------------------------------|
| **Alta centro**          | Dar de alta un centro nuevo                    |
| **Alta línea datos**     | Dar de alta una línea de datos                 |
| **Alta línea voz**       | Dar de alta una línea de voz                   |
| **Alta equipo voz**      | Dar de alta un equipo de voz                   |
| **Alta equipo 2.o nivel**| Dar de alta un EDC de segundo nivel            |
| **Modificaciones**       | Buscar y modificar registros existentes        |
| **Bajas**                | Dar de baja elementos o cerrar centros         |
| **Registro de acciones** | Ver el historial de operaciones realizadas     |

Haz clic en la tarjeta que necesites. También puedes usar la **barra de pestanas** en la parte superior para cambiar entre opciones sin volver al menu.

![Menu principal de Provision con las 8 tarjetas de opciones](./imagenes/captura-02-menu-principal-de-provision-con-las-8-ta.png)

---

## 3. Alta de centro

1. Haz clic en **Alta centro**.
2. Rellena el formulario con los datos del nuevo centro:

### Datos basicos (columna izquierda)

| Campo              | Descripción                                    | Obligatorio |
|--------------------|------------------------------------------------|-------------|
| **Nombre**         | Nombre del centro (se convertira a mayusculas) | Si          |
| **Dirección**      | Dirección postal                               | No          |
| **Código Postal**  | 5 digitos                                      | No          |
| **Poblacion**      | Nombre de la poblacion                         | No          |
| **Provincia**      | A Coruna, Lugo, Ourense o Pontevedra           | No          |
| **Horario Centro** | Horario del centro (max. 15 caracteres)        | No          |
| **Centralita**     | CISCO u OXE                                    | No          |
| **ID Cliente**     | Código de cliente (max. 8 digitos)             | No          |

### RAI y Módulos (columna izquierda)

| Campo          | Formato                |
|----------------|------------------------|
| RAI CISCO      | 8 digitos              |
| Módulo CISCO   | 4 digitos              |
| RAI OXE        | 8 digitos              |
| Módulo OXE     | 4 digitos              |
| RAI NGN        | 8 digitos              |
| Módulo NGN     | 4 digitos              |

### Configuración (columna derecha)

| Campo                  | Descripción                                       |
|------------------------|---------------------------------------------------|
| **Horario**            | Tipo de horario (seleccionar de la lista)         |
| **Tipo de Sede**       | Clasificacion de la sede (seleccionar de la lista)|
| **Switch**             | Fabricante del switch (seleccionar de la lista)   |
| **Coordenadas**        | Latitud y longitud (opcionales)                   |
| **Critica**            | Marcar si es sede critica                         |
| **FlexWAN**            | Marcar si tiene FlexWAN                           |

### Datos del tensiometro (DCT)

| Campo          | Descripción                     |
|----------------|---------------------------------|
| **DCT**        | Marcar si tiene tensiometro     |
| **Extensión**  | 6 digitos                       |
| **ICC**        | Hasta 30 digitos                |
| **N. Largo**   | 9 digitos                       |

### Comentarios

- Campo de texto libre para observaciones del centro.

3. Revisa todos los datos.
4. Haz clic en **Guardar**.
5. El sistema pedira confirmacion antes de guardar.
6. Si todo es correcto, veras un mensaje de exito con el nombre y el ID del nuevo centro.

![Formulario de alta de centro con los campos rellenos y el boton Guardar](./imagenes/captura-03-formulario-de-alta-de-centro-con-los-cam.png)

> **Nota:** Si intentas dar de alta un centro con un nombre o ID de cliente que ya existe, el sistema mostrara un error de duplicado.

---

## 4. Alta de línea de datos

1. Haz clic en **Alta línea datos**.
2. Lo primero que debes elegir es si la línea tendrá equipo asociado o no:
   - **Sin equipo** -- Solo se creara la línea
   - **Con equipo** -- Se creara la línea y un equipo de datos

![Selector de modo "Sin equipo" / "Con equipo" al inicio del formulario](./imagenes/captura-04-selector-de-modo-sin-equipo-con-equipo-a.png)

### Datos de la línea

| Campo              | Descripción                                     | Obligatorio |
|--------------------|-------------------------------------------------|-------------|
| **Centro**         | Buscar y seleccionar el centro (autocompletado) | Si          |
| **Tipo de línea**  | Seleccionar de la lista                         | Si          |
| **Administrativo** | Número administrativo (max. 14 digitos)         | No          |
| **Número línea**   | Número de la línea (max. 14 digitos)            | No          |
| **VRF**            | Seleccionar de la lista                         | No          |
| **Observaciones**  | Texto libre                                     | No          |
| **OLT**            | Nombre del OLT                                  | No          |
| **Nodo N1 / N2**   | Nodos de acceso y red con interfaces e IPs      | No          |
| **Tipo acceso**    | Seleccionar de la lista                         | No          |
| **Función**        | Principal, Redundante, etc. (seleccionar)       | No          |
| **Velocidad**      | Seleccionar de la lista                         | No          |
| **Servicio**       | Seleccionar de la lista                         | No          |

### Datos del equipo (solo si eliges "Con equipo")

Al seleccionar "Con equipo", aparecen campos adicionales:

| Campo                    | Descripción                                     | Obligatorio |
|--------------------------|-------------------------------------------------|-------------|
| **Nemonico Telefónica**  | Nombre del equipo en Telefónica (mayusculas)    | Si          |
| **Nemonico Cliente**     | Nombre del equipo en cliente (mayusculas)       | Si          |
| **IP Gestión Telefónica**| IP de gestión de Telefónica                     | No          |
| **IP Gestión Cliente**   | IP de gestión del cliente                       | No          |
| **Red WAN**              | Formato IP/mascara (ej: 10.0.0.0/30)           | No          |
| **Routing WAN**          | BGP o RIP                                       | No          |
| **Número de Serie**      | Número de serie del equipo                      | No          |
| **Gestionable**          | Marcar si el equipo es gestionable              | No          |
| **Routing LAN**          | BGP, OSPF o RIP                                 | No          |
| **Modelo**               | Seleccionar modelo del catalogo                 | Si          |

### VLANs

Para cada VLAN disponible, marca la casilla para activarla y escribe la red LAN asociada:

| VLAN | Nombre        | Campo de red           |
|------|---------------|------------------------|
| 10   | Datos         | Red LAN Datos          |
| 12   | Voz           | Red LAN Voz            |
| 37   | RFID          | Red LAN RFID           |
| 39   | MESI          | Red LAN MESI           |
| 38   | Electro       | Red LAN Electro        |
| 40   | Retinometro   | Red LAN Retinometro    |
| 60   | Ecografo      | Red LAN Ecografo       |

Marca la casilla de la VLAN para habilitar el campo de red.

![Seccion de VLANs con algunas casillas marcadas y campos de red rellenos](./imagenes/captura-05-seccion-de-vlans-con-algunas-casillas-ma.png)

### Switch Cliente

- Marca la casilla **Switch Cliente** si el centro tiene un switch del cliente.
- Introduce la **IP del switch** en el campo habilitado.

3. Revisa todos los datos y haz clic en **Guardar**.
4. El sistema pedira confirmacion.
5. Si es con equipo, se crearan tanto el equipo como la línea en una única operacion.

---

## 5. Alta de línea de voz

1. Haz clic en **Alta línea voz**.
2. Rellena el formulario:

| Campo              | Descripción                                     | Obligatorio |
|--------------------|-------------------------------------------------|-------------|
| **Centro**         | Buscar y seleccionar (autocompletado)           | Si          |
| **Tipo de línea**  | Seleccionar de la lista                         | Si          |
| **Administrativo** | Número administrativo (max. 14 digitos)         | No          |
| **Número línea**   | Número de la línea (max. 9 digitos)             | No          |
| **Servicio**       | Seleccionar de la lista                         | Si          |
| **Observaciones**  | Texto libre                                     | No          |

3. Haz clic en **Guardar** y confirma.

![Formulario de alta de línea de voz con los campos rellenos](./imagenes/captura-06-formulario-de-alta-de-linea-de-voz-con-l.png)

---

## 6. Alta de equipo de voz

1. Haz clic en **Alta equipo voz**.
2. Rellena el formulario:

| Campo              | Descripción                                     | Obligatorio |
|--------------------|-------------------------------------------------|-------------|
| **Centro**         | Buscar y seleccionar (autocompletado)           | Si          |
| **Nemonico**       | Nombre del equipo                               | Si          |
| **Centralita**     | Tipo de centralita (seleccionar)                | Si          |
| **IP Gestión**     | IP del equipo                                   | Si          |
| **Tipo equipo**    | Modelo del equipo (seleccionar del catalogo)    | Si          |
| **Nodo**           | Tipo de nodo (seleccionar)                      | Si          |
| **Cristal**        | Información del cristal                         | No          |
| **Observaciones**  | Texto libre                                     | No          |

3. Haz clic en **Guardar** y confirma.

![Formulario de alta de equipo de voz con los campos rellenos](./imagenes/captura-07-formulario-de-alta-de-equipo-de-voz-con.png)

> **Nota:** Si el nemonico o la IP de gestión ya existen, el sistema mostrara un error de duplicado.

---

## 7. Alta de equipo de 2.o nivel

1. Haz clic en **Alta equipo 2.o nivel**.
2. Rellena el formulario:

| Campo                       | Descripción                                     | Obligatorio |
|-----------------------------|-------------------------------------------------|-------------|
| **Centro**                  | Buscar y seleccionar (autocompletado)           | Si          |
| **Nemonico Telefónica**     | Nombre del equipo en Telefónica                 | Si          |
| **Nemonico Cliente**        | Nombre del equipo en cliente                    | Si          |
| **Equipo (modelo)**         | Seleccionar modelo del catalogo                 | No          |
| **IP Gestión**              | IP del equipo                                   | Si          |
| **Equipo 1.er Nivel**       | Nemonico del equipo principal (se sugieren)     | No          |
| **Administrativo 1.er Nivel**| Número administrativo de la línea (se sugieren)| No          |
| **Observaciones**           | Texto libre                                     | No          |

3. Al escribir en "Equipo 1.er Nivel", aparecerán sugerencias de equipos existentes.
4. Haz clic en **Guardar** y confirma.

![Formulario de alta de equipo 2.o nivel con sugerencias de equipo 1.er nivel](./imagenes/captura-08-formulario-de-alta-de-equipo-2-o-nivel-c.png)

---

## 8. Modificaciones

El módulo de modificaciones permite buscar cualquier registro de la base de datos y editar sus campos.

### 8.1 Modificar un registro existente

#### Paso 1 -- Seleccionar la tabla

1. Haz clic en **Modificaciones**.
2. Selecciona la tabla donde quieres buscar:
   - Centros
   - Líneas de datos
   - Equipos de datos
   - Equipos de voz
   - Equipos de 2.o nivel

![Selector de tabla con las opciones disponibles](./imagenes/captura-09-selector-de-tabla-con-las-opciones-dispo.png)

#### Paso 2 -- Buscar el registro

1. Escribe en el campo de busqueda (mínimo 2 caracteres).
2. Aparecerán sugerencias con los registros que coinciden.
3. Haz clic en el registro que buscas.

![Campo de busqueda con sugerencias de registros](./imagenes/captura-10-campo-de-busqueda-con-sugerencias-de-reg.png)

#### Paso 3 -- Ver los campos del registro

1. Se mostrara una tabla con todos los campos del registro y sus valores actuales.
2. Cada campo tiene un enlace **Editar** a la derecha.

![Tabla con los campos de un registro mostrando valores actuales y enlaces "Editar"](./imagenes/captura-11-tabla-con-los-campos-de-un-registro-most.png)

#### Paso 4 -- Editar un campo

1. Haz clic en **Editar** junto al campo que quieras modificar.
2. Según el tipo de campo:
   - **Campo de texto** -- Aparecerá un campo de texto para escribir el nuevo valor
   - **Lista desplegable** -- Si el campo es una referencia (tipo de línea, modelo, etc.), aparecerá un desplegable con las opciones
   - **Casilla** -- Si el valor actual es 0/1, aparecerá una casilla de verificación
   - **Centro** -- Si el campo es un centro, aparecerá el buscador con autocompletado
3. Introduce el nuevo valor.
4. Haz clic en **Guardar**.
5. El sistema pedira confirmacion antes de guardar el cambio.

![Edición de un campo con un desplegable de opciones y el boton Guardar](./imagenes/captura-12-edicion-de-un-campo-con-un-desplegable-d.png)

> **Nota:** Algunos campos no se pueden editar (ID, estado de baja, cerrado). Estos no mostraran el enlace "Editar".

### 8.2 Añadir equipo a una línea

Esta opción permite asociar un equipo de datos nuevo a una línea que no tiene equipo.

1. En Modificaciones, selecciona la pestana **"Añadir equipo a línea"**.
2. Busca la línea por número o administrativo.
3. Selecciona la línea de las sugerencias.
4. Se mostrara un formulario con los campos del equipo (identico al de alta de línea con equipo).
5. Rellena los datos del equipo: nemonicos, IPs, modelo, VLANs, etc.
6. Haz clic en **Guardar** y confirma.

![Formulario de añadir equipo a línea con los campos de equipo visibles](./imagenes/captura-13-formulario-de-anadir-equipo-a-linea-con.png)

---

## 9. Bajas

### 9.1 Baja individual de un elemento

1. Haz clic en **Bajas**.
2. Busca y selecciona el centro (autocompletado).
3. Se mostraran todos los elementos activos del centro agrupados por tipo:
   - Líneas de datos
   - Líneas de voz
   - Equipos de voz
   - Equipos de 2.o nivel
   - Equipos de datos
4. Junto a cada elemento hay un boton **Dar de baja**.
5. Haz clic en **Dar de baja** del elemento que quieras desactivar.
6. El sistema pedira confirmacion.
7. Tras confirmar, el elemento se marcara como dado de baja (no se elimina, solo se desactiva).

![Lista de elementos activos de un centro con botones "Dar de baja" junto a cada uno](./imagenes/captura-14-lista-de-elementos-activos-de-un-centro.png)

### 9.2 Cerrar un centro completo

Si necesitas cerrar un centro entero (dar de baja el centro y todos sus elementos):

1. En la vista de bajas de un centro, busca el boton **Cerrar centro** (normalmente al final).
2. Haz clic en **Cerrar centro**.
3. El sistema pedira **doble confirmacion** (por seguridad, ya que esta accion afecta a todo el centro).
4. Confirma ambas veces.
5. Se realizara el cierre completo:
   - El centro se marcara como **Cerrado**
   - Todas las líneas de datos se daran de baja
   - Todas las líneas de voz se daran de baja
   - Todos los equipos de voz se daran de baja
   - Todos los equipos de 2.o nivel se daran de baja
   - Todos los equipos de datos se daran de baja

![Boton "Cerrar centro" con la ventana de confirmacion doble](./imagenes/captura-15-boton-cerrar-centro-con-la-ventana-de-co.png)

> **Importante:** El cierre completo de un centro es una operación sensible. Asegurate de que realmente quieres cerrar el centro y todos sus elementos antes de confirmar.

> **Nota:** Todas las operaciones de baja y cierre quedan registradas en el registro de acciones con el nombre del usuario y la fecha.

---

## Resumen rápido

| Accion                          | Como hacerlo                                          |
|---------------------------------|-------------------------------------------------------|
| Acceder a Provision             | Contraseña de provision                                |
| Alta de centro                  | Rellenar formulario + Guardar                          |
| Alta de línea datos sin equipo  | Seleccionar "Sin equipo" + rellenar + Guardar          |
| Alta de línea datos con equipo  | Seleccionar "Con equipo" + rellenar línea y equipo     |
| Activar VLAN                    | Marcar casilla de la VLAN + escribir la red            |
| Modificar un campo              | Modificaciones > tabla > buscar > Editar campo         |
| Añadir equipo a línea           | Modificaciones > pestana "Añadir equipo" > buscar línea|
| Baja individual                 | Bajas > centro > boton "Dar de baja" del elemento      |
| Cerrar centro completo          | Bajas > centro > boton "Cerrar centro" + doble confirm.|
| Cerrar sesión Provision         | Boton de logout                                        |

---

*Fin del manual -- Módulo Provision v1.5*
