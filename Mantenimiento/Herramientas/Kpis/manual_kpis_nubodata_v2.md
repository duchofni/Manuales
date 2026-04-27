# Manual de Usuario: Módulo KPIs Nubodata

| Campo       | Valor                                          |
|-------------|------------------------------------------------|
| **Módulo**  | Mantenimiento > Herramientas > KPIs Nubodata   |
| **Versión** | 1.5                                            |
| **Fecha**   | Abril 2026                                     |
| **Para**    | Operadores CGE SERGAS                          |

---

## 1. Descripción general

El módulo KPIs Nubodata muestra los indicadores de cumplimiento SLA del contrato **Nubodata** (Material No Ibercom). Mide el tiempo de resolución desde la apertura en GLPI hasta la solución. Su funcionamiento es similar al de KPIs Inelcom pero con métricas propias del contrato Nubodata.

---

## 2. Seleccionar período

En la parte superior verás los botones de período:

| Botón            | Período que muestra                            |
|------------------|------------------------------------------------|
| **Semana**       | La semana anterior completa (lunes a domingo)  |
| **Mes**          | El mes anterior completo                       |
| **Año**          | El año anterior completo                       |
| **Fecha concreta** | Rango personalizado de fechas               |

- Por defecto está seleccionada **Semana**.

### 2.1. Seleccionar fecha concreta

1. Pulsa **Fecha concreta**.
2. Se desplegará un panel con dos campos: **Desde** y **Hasta**.
3. Selecciona las fechas.
4. Pulsa **Aplicar**.

![Panel superior de KPIs Nubodata con los botones de período y el panel de fechas desplegado](./imagenes/captura-01-panel-superior-de-kpis-nubodata-con-los.png)

---

## 3. Leer los indicadores

El dashboard muestra el **SLA de resolución** Nubodata:

### 3.1. Gráfica donut

- Muestra el **porcentaje de cumplimiento** del SLA.
- El color indica el nivel de cumplimiento:

| Color       | Significado                                       |
|-------------|---------------------------------------------------|
| **Verde**   | SLA cumplido, buen rendimiento                    |
| **Naranja** | SLA cerca del límite, hay que prestar atención    |
| **Rojo**    | SLA incumplido, por debajo del umbral aceptable   |

### 3.2. Contadores

- Se muestra el número de incidencias **dentro de umbral** (cumplimiento) y **fuera de umbral** (incumplimiento).

### 3.3. Tendencia

- Una gráfica de barras muestra la **evolución** del cumplimiento a lo largo del período seleccionado.

![Dashboard de KPIs Nubodata con la gráfica donut, los contadores y la gráfica de tendencia](./imagenes/captura-02-dashboard-de-kpis-nubodata-con-la-grafic.png)

---

## 4. Ver detalle de incidencias (modal)

1. Pulsa sobre la zona de incidencias fuera de umbral.
2. Se abrirá un **modal** con la tabla de incidencias que no cumplen el SLA.
3. La tabla muestra:
   - ID de la incidencia
   - Centro
   - Tipo
   - Asunto
   - Fecha de apertura
   - Tiempo real de resolución
   - Umbral máximo permitido
   - Enlace para **editar** la incidencia
4. Cierra el modal pulsando fuera o en la X.

![Modal de detalle de incidencias Nubodata fuera de umbral](./imagenes/captura-03-modal-de-detalle-de-incidencias-nubodata.png)

---

## 5. Exportar datos

En la barra superior:

- **Excel**: descarga un fichero `.xlsx` con los datos del período.
- **PDF**: descarga un fichero `.pdf` con las tablas de KPIs.

1. Selecciona el período.
2. Pulsa el botón del formato deseado.
3. Se descargará automáticamente.

---

## 6. Diferencias con KPIs Inelcom

| Aspecto               | KPIs Inelcom                          | KPIs Nubodata                        |
|-----------------------|---------------------------------------|--------------------------------------|
| Contrato              | Inelcom                               | Nubodata (Material No Ibercom)       |
| Indicadores           | 4 (T.Resp, T.Reg, T.Sol, T.N1)       | Tiempo de resolución GLPI            |
| Origen de datos       | Incidencias BDU                       | Incidencias GLPI                     |
| Estructura dashboard  | 4 bloques con múltiples filas         | 1 bloque principal                   |

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
