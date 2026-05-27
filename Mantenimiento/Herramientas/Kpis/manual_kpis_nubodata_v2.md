# Manual de Usuario: Módulo KPIs Nubodata

| Campo       | Valor                                          |
|-------------|------------------------------------------------|
| **Módulo**  | Mantenimiento > Herramientas > KPIs Nubodata   |
| **Versión** | 1.7                                            |
| **Fecha**   | Mayo 2026                                      |
| **Para**    | Operadores CGE SERGAS                          |

---

## Índice

1. [Para qué sirve este módulo](#1-para-qué-sirve-este-módulo)
2. [Cómo accedemos al módulo](#2-cómo-accedemos-al-módulo)
3. [Tabla superior: incidencias abiertas fuera de SLA](#3-tabla-superior-incidencias-abiertas-fuera-de-sla)
4. [Seleccionar período](#4-seleccionar-período)
5. [Leer los indicadores del dashboard](#5-leer-los-indicadores-del-dashboard)
6. [Ver detalle de incidencias fuera de SLA](#6-ver-detalle-de-incidencias-fuera-de-sla)
7. [Exportar datos](#7-exportar-datos)
8. [Acceso restringido](#8-acceso-restringido)
9. [Diferencias con KPIs Inelcom](#9-diferencias-con-kpis-inelcom)

---

## 1. Para qué sirve este módulo

El módulo **KPIs Nubodata** muestra el cumplimiento del SLA del contrato **Nubodata** (Material No Ibercom). Mide el **tiempo de resolución** de cada incidencia desde su apertura en GLPI hasta la solución, expresado en **horas laborables** (descuenta sábados y domingos enteros).

El SLA aplicado no es fijo: depende de la **urgencia** marcada en la incidencia.

| Urgencia | SLA (horas laborables) |
|----------|------------------------|
| **U1**   | ≤ 24 h |
| **U2**   | ≤ 48 h |
| **U3**   | ≤ 72 h |
| Sin urgencia marcada | Se trata como **U2 (48 h)** |

Cada incidencia se clasifica como **dentro de SLA** (🟢 verde) o **fuera de SLA** (🔴 rojo) comparando su tiempo real de resolución con el SLA que le corresponde por urgencia. No hay zona de tolerancia intermedia.

La pantalla está dividida en **dos secciones** que se ven a la vez:

- **Arriba** — Tabla en tiempo real con las incidencias **NO cerradas** que ya están fuera de SLA. Sirve para reclamarlas antes del cierre.
- **Abajo** — Dashboard con donut, contadores y tendencia de las incidencias **ya cerradas** en el período seleccionado.

---

## 2. Cómo accedemos al módulo

1. Abrimos la **Web BDU** en el navegador.
2. En la barra superior pulsamos **Mantenimiento**.
3. Pulsamos la tarjeta **Herramientas** y, en el acordeón, elegimos **KPIs Nubodata**.

> **Atajo:** también podemos llegar directamente con `?m=mantenimiento&sub=kpis_nubodata` añadido al final de la URL.

---

## 3. Tabla superior: incidencias abiertas fuera de SLA

Lo primero que vemos al abrir el módulo es una tabla con las incidencias **VOZ Material No Ibercom** que están **abiertas** (no cerradas) y que ya han **rebasado su SLA** según su urgencia.

![Tabla superior con las incidencias VOZ Material No Ibercom abiertas que ya están fuera de SLA, mostrando una fila por incidencia con urgencia, SLA aplicado, tiempo abierto y exceso](./imagenes/captura-01-panel-superior-de-kpis-nubodata-con-los.png)

Cada fila muestra:

| Columna             | Contenido                                                                       |
|---------------------|---------------------------------------------------------------------------------|
| **✏️**              | Acceso directo a editar la incidencia en el módulo Incidencias.                 |
| **Centro**          | Nombre del centro afectado.                                                     |
| **SIXPI**           | Ticket del cliente.                                                             |
| **GDIA**            | Ticket interno (Incidencias_Internas).                                          |
| **Asunto**          | Resumen de la incidencia.                                                       |
| **Urg**             | Urgencia marcada: **U1** (rojo), **U2** (naranja) o **U3** (verde).             |
| **SLA**             | SLA aplicado según la urgencia: 24h / 48h / 72h.                                |
| **Apertura GLPI**   | Fecha y hora de la **primera actuación GLPI** de la incidencia.                 |
| **Ticket GLPI (1ª act.)** | Número del primer ticket GLPI registrado y su fecha.                      |
| **Respuesta**       | Fecha de respuesta al cliente (si la hay).                                      |
| **Solución**        | Vacía en la práctica, porque estas incidencias aún están abiertas.              |
| **T. abierto (lab.)** | Tiempo transcurrido desde la apertura GLPI, en horas laborables.              |
| **Exceso**          | Cuánto ha rebasado ya el SLA correspondiente (en horas laborables).             |

Si no hay incidencias abiertas fuera de SLA, vemos el mensaje **"Sin incidencias VOZ Material No Ibercom abiertas fuera de SLA"**.

> **Cómo usar la tabla:** revisamos cada fila para reclamar las que se han pasado de plazo. Pulsamos el icono ✏️ para abrir directamente la edición de la incidencia.

---

## 4. Seleccionar período

Debajo de la tabla superior está el dashboard de incidencias cerradas. Sus filtros de período son:

| Botón                | Período que muestra                                       |
|----------------------|-----------------------------------------------------------|
| **Semana**           | Semana anterior completa (lunes a domingo). Activo por defecto. |
| **Mes**              | Mes anterior completo. Despliega un selector con todos los meses disponibles para elegir otro. |
| **Año**              | Año anterior completo. Despliega un selector con los años disponibles para elegir otro. |
| **📅 Fecha concreta**| Rango personalizado de fechas mediante panel desplegable. |

### 4.1. Elegir un mes o un año concreto

- Al pulsar **Mes** aparece un desplegable con los meses disponibles. Lo cambiamos y los datos se recalculan al instante.
- Igual con **Año**: aparece un desplegable con los años disponibles.

### 4.2. Rango de fechas personalizado

1. Pulsamos **📅 Fecha concreta**.
2. Se despliega un panel con **Desde** y **Hasta**.
3. Elegimos las fechas.
4. Pulsamos **Aplicar**.

> El período seleccionado solo afecta al **dashboard inferior**. La tabla superior siempre muestra el estado actual (no depende del período).

---

## 5. Leer los indicadores del dashboard

El dashboard inferior se calcula sobre las incidencias **cerradas** dentro del período seleccionado.

![Dashboard de KPIs Nubodata con la donut bicolor verde/rojo, los contadores de dentro y fuera de SLA, el porcentaje de cumplimiento, los chips por urgencia y la gráfica de tendencia](./imagenes/captura-02-dashboard-de-kpis-nubodata-con-la-grafic.png)

### 5.1. Donut bicolor

La donut representa la distribución de las incidencias cerradas:

- 🟢 **Dentro SLA** — verde
- 🔴 **Fuera SLA** — rojo

En el centro de la donut vemos el porcentaje global de incidencias dentro de SLA.

### 5.2. Filas detalle

Debajo de la leyenda aparecen las filas con los conteos exactos:

| Fila                       | Significado                                                            |
|----------------------------|------------------------------------------------------------------------|
| 🟢 **Dentro de SLA**       | Incidencias resueltas dentro del SLA de su urgencia.                   |
| 🔴 **Fuera de SLA**        | Incidencias que rebasaron su SLA (incumplimiento).                     |
| **Total incidencias**      | Suma de las dos filas anteriores.                                      |

Ambas filas son **clickables**: abren el modal con el detalle de las incidencias de esa zona ([sección 6](#6-ver-detalle-de-incidencias-fuera-de-sla)).

### 5.3. Porcentaje de cumplimiento

Justo debajo de las filas vemos:

> **% cumplimiento (SLA por urgencia)** — *valor* — *badge*

El badge cambia según el cumplimiento global:

| Badge          | Significado                          |
|----------------|--------------------------------------|
| **CUMPLE**     | ≥ 90 % de incidencias dentro de SLA. |
| **NO CUMPLE**  | < 90 % de cumplimiento.              |
| **Sin datos**  | No hay incidencias cerradas en el período. |

### 5.4. Desglose por urgencia (chips)

Debajo del porcentaje aparecen unas **píldoras** con el desglose por urgencia. Solo se muestran las urgencias que tienen incidencias en el período.

Cada chip indica:

- **U1 / U2 / U3 / Sin urg.** — identificador de la urgencia.
- **≤24h / ≤48h / ≤72h / ≤48h** — el SLA aplicado.
- **N/M** — incidencias dentro de SLA sobre el total de esa urgencia.
- **X%** — porcentaje de cumplimiento de esa urgencia.

El color del porcentaje del chip:

- **Verde** — ≥ 90 % de cumplimiento.
- **Naranja** — entre 70 % y 89 %.
- **Rojo** — menos del 70 %.

> **Ejemplo:** un chip `U2 · ≤48h · 9/10 · 90,0%` (verde) nos dice que de las 10 incidencias U2 del período, 9 se resolvieron dentro de las 48 h laborables.

### 5.5. Gráfica de tendencia

Debajo del bloque hay una gráfica de barras apiladas (verde + rojo) que muestra la **evolución del cumplimiento** dentro del período seleccionado (por días, semanas o meses según el período activo).

---

## 6. Ver detalle de incidencias fuera de SLA

1. Pulsamos sobre una de las filas clickables (Verde o Rojo).
2. Se abre un **modal** con la tabla de las incidencias.
3. La tabla del modal muestra estas columnas:

| Columna              | Contenido                                                                      |
|----------------------|--------------------------------------------------------------------------------|
| **ID**               | Identificador interno de la incidencia BDU.                                    |
| **Ticket GLPI**      | Número de ticket en GLPI.                                                      |
| **Centro**           | Centro afectado.                                                               |
| **Asunto**           | Texto resumen de la incidencia.                                                |
| **Urg**              | Urgencia (U1, U2, U3 o —).                                                     |
| **SLA**              | SLA aplicado según la urgencia.                                                |
| **Apertura GLPI**    | Fecha y hora de apertura del primer ticket GLPI.                               |
| **Solución**         | Fecha y hora de solución.                                                      |
| **T. real (lab.)**   | Tiempo de resolución medido en **horas laborables**.                           |
| **Exceso**           | Cuánto se superó el SLA correspondiente (solo en la fila roja).                |

> La fila verde abre el modal en blanco con el mensaje **"Todas dentro de SLA — no hay incumplimientos"**. Las que cumplen no se listan individualmente.

4. Cerramos el modal pulsando **✕** o haciendo clic fuera.
5. En el pie del modal tenemos un enlace **Ver en Incidencias ▶** para abrir el listado completo.

---

## 7. Exportar datos

En la barra superior tenemos dos botones de exportación:

| Botón        | Resultado                                                              |
|--------------|------------------------------------------------------------------------|
| **📊 Excel** | Descarga un fichero `.xlsx` con los datos del período seleccionado.    |
| **🔴 PDF**   | Descarga un `.pdf` con las tablas de KPIs y la cabecera con logos.     |

El fichero exportado refleja el modelo nuevo: secciones **Dentro de SLA (por urgencia)** y **Fuera de SLA (por urgencia)**, con las columnas **Urg** y **SLA** añadidas en cada fila para que se pueda auditar por urgencia.

Pasos:

1. Ajustamos el período al estado deseado.
2. Pulsamos el botón del formato (**📊 Excel** o **🔴 PDF**).
3. El fichero se descarga automáticamente.

> La tabla superior (abiertas fuera de SLA) **no se exporta**, ya que su contenido cambia en tiempo real. Si necesitamos un volcado, hacemos captura de pantalla.

---

## 8. Acceso restringido

El módulo **KPIs Nubodata** está restringido por unidad organizativa de Active Directory. Las cuentas que pertenecen a `UO_usuarios_dominio` no pueden entrar y ven la pantalla de **🔒 Acceso restringido**.

Si nos corresponde el acceso pero no entramos, debemos contactar con el administrador del sistema.

---

## 9. Diferencias con KPIs Inelcom

| Aspecto                    | KPIs Inelcom                              | KPIs Nubodata                                                  |
|----------------------------|-------------------------------------------|----------------------------------------------------------------|
| Contrato                   | Inelcom                                   | Nubodata (Material No Ibercom)                                 |
| Origen de datos            | Incidencias BDU                           | Incidencias BDU con actuación GLPI                             |
| Indicadores                | 4 bloques (T.Resp, T.Reg, T.Sol, T.N1)    | 2 secciones: tabla de abiertas + dashboard de cerradas         |
| Cálculo del tiempo         | Horas naturales                           | **Horas laborables** (sin sábados ni domingos enteros)         |
| Umbrales                   | Por tipo y por urgencia                   | **Por urgencia**: U1 ≤24h · U2 ≤48h · U3 ≤72h                  |
| Modelo de zonas            | Tricolor (verde / naranja / rojo)         | **Bicolor** (verde dentro SLA / rojo fuera SLA)                |
| Tabla en tiempo real       | No                                        | **Sí**: incidencias abiertas que ya superan su SLA             |
| Desglose por urgencia      | Sí, por tipo y urgencia                   | Sí, chips bajo el porcentaje de cumplimiento                   |

---

*Manual para operadores CGE SERGAS. Versión 1.7 — Mayo 2026.*
