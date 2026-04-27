# Manual de Usuario: Módulo KPIs Inelcom

| Campo       | Valor                                      |
|-------------|--------------------------------------------|
| **Módulo**  | Mantenimiento > Herramientas > KPIs Inelcom|
| **Versión** | 1.5                                        |
| **Fecha**   | Abril 2026                                 |
| **Para**    | Operadores CGE SERGAS                      |

---

## 1. Descripción general

El módulo KPIs Inelcom muestra un dashboard con los indicadores de cumplimiento SLA del contrato Inelcom, calculados sobre las incidencias cerradas. Permite ver el rendimiento por período, consultar el detalle de las incidencias fuera de umbral y exportar los datos.

---

## 2. Seleccionar período

Al entrar en KPIs verás unos botones de período en la parte superior:

| Botón            | Período que muestra                            |
|------------------|------------------------------------------------|
| **Semana**       | La semana anterior completa (lunes a domingo)  |
| **Mes**          | El mes anterior completo                       |
| **Año**          | El año anterior completo                       |
| **Fecha concreta** | Rango personalizado de fechas               |

- Por defecto está seleccionada **Semana**.
- Al cambiar de período, los datos se actualizan automáticamente.

[CAPTURA: Barra superior del dashboard con los botones de período y la etiqueta mostrando el rango de fechas]

### 2.1. Seleccionar fecha concreta

1. Pulsa el botón **Fecha concreta**.
2. Se desplegará un panel con dos campos de fecha: **Desde** y **Hasta**.
3. Selecciona las fechas deseadas.
4. Pulsa **Aplicar**.

[CAPTURA: Panel de fechas desplegado con los campos Desde y Hasta y el botón Aplicar]

---

## 3. Leer los indicadores

El dashboard muestra **4 bloques KPI** en una cuadrícula:

### 3.1. T.Resp (Tiempo de Respuesta)

Mide cuánto se tarda en responder al cliente desde que se abre la incidencia.

| Tipo de incidencia   | Umbral máximo |
|----------------------|---------------|
| VOZ                  | 5 minutos     |
| DATOS                | 15 minutos    |
| DATOS 4G/5G          | 40 minutos    |
| Modificaciones       | 5 minutos     |
| SOP TI L1            | 5 minutos     |
| SOP TI L3            | 5 minutos     |

- Se muestra el número de incidencias **dentro** y **fuera** de umbral para cada tipo.
- También aparecen las incidencias **sin fecha de respuesta** (advertencia).
- El **SLA global** aparece como porcentaje con un badge de color.

### 3.2. T.Reg (Tiempo de Registro)

Mide cuánto se tarda en registrar el GDIA desde la apertura de la incidencia.

| Urgencia | Umbral máximo |
|----------|---------------|
| U1       | 15 minutos    |
| U2       | 30 minutos    |
| U3       | 90 minutos    |

- Las incidencias de VOZ con reposición están excluidas de este cálculo.
- Se muestran las incidencias **sin GDIA** (advertencia).

### 3.3. T.Sol (Tiempo de Solución)

Mide cuánto se tarda en resolver la incidencia.

| Urgencia | Umbral máximo |
|----------|---------------|
| U1       | 4 horas       |
| U2       | 12 horas      |
| U3       | 24 horas      |

### 3.4. T.N1 (Tiempo N1 CGE)

Mide cuánto tarda el primer nivel del CGE en actuar.

| Urgencia | Umbral máximo |
|----------|---------------|
| U1       | 30 minutos    |
| U2       | 90 minutos    |
| U3       | 180 minutos   |

[CAPTURA: Dashboard completo con los 4 bloques KPI mostrando las gráficas donut y las filas de datos]

### 3.5. Gráficas

Cada bloque tiene:
- Una **gráfica donut** que muestra el porcentaje de cumplimiento SLA.
- Una **gráfica de tendencia** (línea) que muestra la evolución dentro del período.

---

## 4. Ver detalle de incidencias (modal)

1. Pulsa sobre cualquier **fila** de un bloque KPI (por ejemplo, "VOZ: 2 fuera de umbral").
2. Se abrirá un **modal** con la lista de esas incidencias.
3. La tabla del modal muestra:
   - ID de la incidencia
   - Centro
   - Tipo
   - Asunto
   - Fecha de apertura
   - Tiempo real (el que se tardó)
   - Umbral (el máximo permitido)
   - Enlace para **editar** la incidencia directamente
4. Pulsa fuera del modal o en la X para cerrarlo.

[CAPTURA: Modal de detalle mostrando la tabla de incidencias fuera de umbral con las columnas descritas]

---

## 5. Exportar datos

En la barra superior hay dos botones de exportación:

- **Excel**: descarga un fichero `.xlsx` con todos los datos del período seleccionado.
- **PDF**: descarga un fichero `.pdf` con las tablas de KPIs.

1. Selecciona primero el período deseado.
2. Pulsa **Excel** o **PDF**.
3. Se descargará el fichero automáticamente.

---

## 6. Interpretación de colores

| Color del badge/donut | Significado                         |
|-----------------------|-------------------------------------|
| **Verde**             | SLA cumplido (buen rendimiento)     |
| **Naranja**           | SLA cerca del límite                |
| **Rojo**              | SLA incumplido                      |

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
