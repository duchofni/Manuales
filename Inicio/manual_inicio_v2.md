# Manual de Usuario -- Modulo Inicio (Panel de Control)

| Campo       | Valor                          |
|-------------|--------------------------------|
| **Modulo**  | Inicio                         |
| **Version** | 1.5                            |
| **Fecha**   | Abril 2026                     |
| **Para**    | Operadores CGE SERGAS          |

---

## Indice

1. [Acceder al panel de inicio](#1-acceder-al-panel-de-inicio)
2. [Barra superior](#2-barra-superior)
3. [KPIs de centros](#3-kpis-de-centros)
4. [Tipo de sede (grafico)](#4-tipo-de-sede-grafico)
5. [Equipos gestionados](#5-equipos-gestionados)
6. [Lineas activas](#6-lineas-activas)
7. [Equipos por modelo](#7-equipos-por-modelo)
8. [Incidencias abiertas](#8-incidencias-abiertas)
9. [Pedidos pendientes de instalaciones](#9-pedidos-pendientes-de-instalaciones)
10. [Infraestructura](#10-infraestructura)

---

## 1. Acceder al panel de inicio

1. Abre la aplicacion Web BDU en tu navegador.
2. El panel de inicio es la **primera pantalla** que aparece al acceder a la aplicacion.
3. Tambien puedes volver a el en cualquier momento haciendo clic en **Inicio** en el menu lateral.

[CAPTURA: Vista general del panel de inicio completo]

> **Nota:** Los datos del panel se actualizan automaticamente cada **2 minutos**. No necesitas recargar la pagina manualmente.

---

## 2. Barra superior

En la parte superior del panel veras:

- **Titulo:** "BDU -- Panel de inicio"
- **Fecha y hora:** Se actualiza automaticamente con cada recarga de datos
- **Estado de la base de datos:** Una etiqueta que indica si la conexion a la base de datos esta funcionando correctamente

[CAPTURA: Barra superior mostrando el titulo, la fecha/hora y la etiqueta de estado de BD]

---

## 3. KPIs de centros

La primera seccion muestra **6 tarjetas** con los indicadores clave de los centros:

| Tarjeta              | Que indica                                                  |
|----------------------|-------------------------------------------------------------|
| **Total**            | Numero total de centros registrados en la base de datos     |
| **Activos**          | Centros que estan abiertos y operativos                     |
| **Cerrados**         | Centros que han sido cerrados                               |
| **Alta prioridad**   | Centros marcados como sede critica                          |
| **Con FlexWAN**      | Centros que tienen el servicio FlexWAN activo               |
| **Con DCT**          | Centros que tienen dispositivo de control de tension        |

[CAPTURA: Fila de 6 tarjetas KPI de centros con sus valores numericos]

---

## 4. Tipo de sede (grafico)

En la columna izquierda aparece un **grafico de anillo (donut)** que muestra la distribucion de centros por tipo de sede.

- El grafico usa colores diferentes para cada tipo de sede.
- En el centro del anillo se muestra el **total de centros activos**.
- Debajo del grafico hay una **leyenda** con el nombre de cada tipo de sede, su color y su numero.

[CAPTURA: Grafico donut de tipo de sede con leyenda]

---

## 5. Equipos gestionados

Debajo del grafico de tipo de sede, se muestra la seccion de **equipos gestionados**:

- **Equipos datos activos** -- Numero total de equipos de datos en servicio
- **Gestionables** -- Cuantos de esos equipos son gestionables remotamente
- **Con IP de gestion** -- Equipos que tienen asignada una IP de gestion
- **Con switch cliente** -- Equipos que tienen switch del cliente

Cada indicador se muestra con una **barra de progreso** que permite ver de un vistazo la proporcion.

[CAPTURA: Seccion de equipos gestionados con barras de progreso]

---

## 6. Lineas activas

La columna central muestra las **lineas activas** de la red:

- En la parte superior, un **badge** con el total de lineas activas.
- Debajo, una lista de **barras** donde cada barra representa un tipo de linea.
- Cada barra muestra:
  - El nombre del tipo de linea
  - El numero de lineas activas de ese tipo
  - La proporcion respecto al total (barra de color)

[CAPTURA: Seccion de lineas activas con el total y las barras por tipo de linea]

---

## 7. Equipos por modelo

La columna derecha muestra los **12 modelos de equipo mas frecuentes**:

- Lista de barras, una por cada modelo.
- Cada barra muestra el nombre del modelo y el numero de unidades activas.
- Ordenados de mayor a menor.

[CAPTURA: Seccion de equipos por modelo mostrando las barras de los 12 modelos mas frecuentes]

---

## 8. Incidencias abiertas

La seccion de **incidencias abiertas** muestra tarjetas con las incidencias que estan actualmente sin resolver:

- **Total** de incidencias abiertas.
- Desglose por **tipo de incidencia**, cada uno con su propia tarjeta y barra de progreso.

Esto permite ver rapidamente si hay incidencias acumuladas y de que tipo son.

[CAPTURA: Seccion de incidencias abiertas con tarjetas por tipo]

---

## 9. Pedidos pendientes de instalaciones

Esta seccion muestra los **pedidos de instalacion** que estan pendientes de realizarse:

| Tarjeta    | Que indica                                            |
|------------|-------------------------------------------------------|
| **LOGOS**  | Pedidos pendientes de instalacion de datos (LOGOS)    |
| **BJ**     | Pedidos pendientes de instalacion de voz (BJ)        |
| **ATLAS**  | Pedidos pendientes de ordenes ATLAS                   |

Cada tarjeta muestra el numero de pedidos pendientes.

[CAPTURA: Tarjetas de pedidos pendientes de LOGOS, BJ y ATLAS]

---

## 10. Infraestructura

La seccion inferior del panel muestra el estado en tiempo real de los servidores y sistemas que soportan la aplicacion BDU. Esta informacion es util para saber si hay algun problema en la infraestructura.

### 10.1 Servidores Proxmox (PVE)

Se muestran **dos nodos** de servidor Proxmox. Para cada nodo veras:

| Indicador             | Que significa                                           |
|-----------------------|---------------------------------------------------------|
| **CPU**               | Porcentaje de uso del procesador                        |
| **RAM**               | Memoria usada / total (en GB) y porcentaje              |
| **Disco**             | Espacio en disco usado / total y porcentaje             |
| **VMs activas**       | Maquinas virtuales que estan funcionando                |
| **VMs paradas**       | Maquinas virtuales apagadas                             |
| **Contenedores**      | Contenedores LXC activos y parados                     |
| **Storage pools**     | Almacenamiento: nombre, tipo, uso y porcentaje          |

Las barras de progreso cambian de color segun el nivel de uso:
- **Verde** -- Uso normal
- **Amarillo** -- Uso alto (atencion)
- **Rojo** -- Uso critico (posible problema)

[CAPTURA: Panel de un nodo Proxmox con barras de CPU, RAM y disco]

### 10.2 Servidor de backups (PBS)

Muestra el estado del servidor de copias de seguridad Proxmox Backup Server:

| Indicador        | Que significa                                |
|------------------|----------------------------------------------|
| **CPU**          | Porcentaje de uso del procesador             |
| **RAM**          | Memoria usada / total y porcentaje           |
| **Datastores**   | Almacenes de backup con espacio usado/total  |

[CAPTURA: Panel del servidor PBS con indicadores de datastores]

### 10.3 NAS (almacenamiento en red)

Muestra el estado del NAS QNAP:

| Indicador          | Que significa                                      |
|--------------------|----------------------------------------------------|
| **CPU**            | Porcentaje de uso del procesador                   |
| **RAM**            | Memoria usada / total (en MB) y porcentaje         |
| **Temp. CPU**      | Temperatura del procesador                         |
| **Temp. Sistema**  | Temperatura general del sistema                    |
| **Ventiladores**   | Velocidad de los ventiladores (RPM)                |
| **Volumenes**      | Espacio usado / total de cada volumen montado      |

[CAPTURA: Panel del NAS QNAP con temperaturas y volumenes]

### 10.4 Base de datos MariaDB

Muestra estadisticas de la base de datos de la aplicacion:

| Indicador          | Que significa                                           |
|--------------------|---------------------------------------------------------|
| **Tamano**         | Espacio total que ocupa la base de datos (en MB)        |
| **Tablas**         | Numero de tablas en la base de datos                    |
| **Conexiones**     | Numero de conexiones activas                            |
| **Ultimo backup**  | Fecha y hora de la ultima copia de seguridad            |

[CAPTURA: Panel de MariaDB con tamano, tablas, conexiones y ultimo backup]

---

## Guia de interpretacion de colores

### Barras de infraestructura

| Color      | Rango de uso    | Significado                            |
|------------|-----------------|----------------------------------------|
| Verde      | 0% -- 60%       | Todo funciona con normalidad           |
| Amarillo   | 60% -- 80%      | Uso alto, a vigilar                    |
| Rojo       | Mayor de 80%    | Uso critico, posible problema          |

### Temperaturas

| Color      | Significado                                      |
|------------|--------------------------------------------------|
| Normal     | Temperatura dentro del rango esperado            |
| Amarillo   | Temperatura elevada (atencion)                   |
| Rojo       | Temperatura critica (posible problema de hardware)|

---

## Resumen rapido

| Seccion                 | Que muestra                                      |
|-------------------------|--------------------------------------------------|
| KPIs Centros            | Total, activos, cerrados, criticos, FlexWAN, DCT |
| Tipo de sede            | Distribucion grafica por tipo de sede            |
| Equipos gestionados     | Equipos activos, gestionables, con IP, con switch|
| Lineas activas          | Total y desglose por tipo de linea               |
| Equipos por modelo      | Los 12 modelos mas frecuentes                    |
| Incidencias abiertas    | Total y desglose por tipo                        |
| Pedidos pendientes      | LOGOS, BJ, ATLAS                                 |
| Infraestructura         | Estado de servidores, NAS y base de datos        |

> **Recuerda:** Todo el panel se actualiza automaticamente cada 2 minutos. Si necesitas datos al momento, puedes recargar la pagina manualmente con **F5**.

---

*Fin del manual -- Modulo Inicio v1.5*
