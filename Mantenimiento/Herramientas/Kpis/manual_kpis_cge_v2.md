# Manual de Usuario: Módulo KPIs CGE

| Campo       | Valor                                          |
|-------------|------------------------------------------------|
| **Módulo**  | Mantenimiento > Herramientas > KPIs CGE        |
| **Versión** | 1.0                                            |
| **Fecha**   | Abril 2026                                     |
| **Para**    | Operadores y administradores CGE SERGAS        |

---

## 1. Descripción general

El módulo **KPIs CGE** es un dashboard analítico de **volumen y tendencias** de incidencias cerradas sobre toda la planta del CGE SERGAS. A diferencia de KPIs Inelcom y KPIs Nubodata —que miden cumplimiento de SLA—, este módulo se centra en **cuántas incidencias hay, cómo evolucionan y dónde se concentran**.

Está pensado para apoyar reuniones de seguimiento, informes mensuales y análisis comparativo entre años.

> **Nota importante:** los datos anteriores a **2022** son residuales de la importación histórica desde Excel y se descartan automáticamente del dashboard. Todas las gráficas y tablas comienzan en 2022.

---

## 2. Filtros globales

En la cabecera del dashboard hay tres filtros que afectan a **todos los bloques** (excepto los selectores propios de cada bloque):

| Filtro             | Comportamiento                                                       |
|--------------------|----------------------------------------------------------------------|
| **Años** (chips)   | Multiselección. Se pulsan los años que se quieren incluir/excluir    |
| **Tipos** (chips)  | Multiselección. Tipos de incidencia: VOZ, DATOS, Modificaciones, SOP TI L1, SOP TI L3 |
| **Área sanitaria** | Selector único. "— Todas —" o una de las 7 áreas SERGAS              |

Junto a los filtros se encuentran los botones **Excel** y **PDF** para exportar el dashboard completo (ver sección [9. Exportar datos](#9-exportar-datos)).

![Cabecera del dashboard con los filtros globales (años, tipos, área) y los botones de exportación](./imagenes/captura-01-cabecera-de-kpis-cge-con-los-filtros-glo.png)

---

## 3. Bloque 1: Volumen anual por tipo

Gráfica de líneas que muestra la **evolución anual** de las incidencias cerradas:

- Una línea **TOTAL** (azul, gruesa) con el total de incidencias del año.
- Una línea por cada **tipo** de incidencia (VOZ, DATOS, Modificaciones, SOP TI L1, SOP TI L3).
- Eje X: años. Eje Y: número de incidencias cerradas.

Permite ver de un vistazo si el volumen total ha subido o bajado y qué tipo está tirando del crecimiento.

![Gráfica de líneas del Volumen anual por tipo, con la serie TOTAL y una línea por tipo de incidencia](./imagenes/captura-02-bloque-volumen-anual-por-tipo.png)

---

## 4. Bloque 2: Evolución mensual comparada por año

### 4.1. Gráfica de líneas

- Una línea por cada año seleccionado.
- Eje X: meses (Ene–Dic). Eje Y: número de incidencias.

Sirve para comparar la **estacionalidad** (qué meses tienen más incidencias) entre años distintos.

![Gráfica de evolución mensual con una línea por año, eje X de Ene a Dic](./imagenes/captura-03-bloque-evolucion-mensual-comparada.png)

### 4.2. Tabla pivot mensual + % diferencia

Debajo de la gráfica, una **tabla pivot** muestra los mismos datos en formato numérico:

- Filas: años.
- Columnas: 12 meses + **Total anual** + **Media mensual**.

Al final de la tabla hay una **fila de "% Diferencia"** que compara dos años a elegir:

1. En el desplegable **Comparar** se elige el año A (base).
2. En el desplegable **contra** se elige el año B (a comparar).
3. La fila amarilla muestra `(B − A) / A × 100` para cada mes y para los totales.
4. Los porcentajes se muestran en **rojo** si el valor sube (más incidencias) y en **verde** si baja.

Por defecto se comparan el último año con el penúltimo de los seleccionados.

![Tabla pivot años por meses con la fila amarilla de % Diferencia y los selectores Comparar/contra](./imagenes/captura-04-tabla-pivot-mensual-con-porcentaje-difer.png)

---

## 5. Bloque 3: Top subtipos y centros

Este bloque resume **dónde y de qué tipo** se concentran las incidencias en un año y tipo concretos.

### 5.1. Controles propios del bloque

| Control | Descripción                                                            |
|---------|------------------------------------------------------------------------|
| **Año** | Año a analizar (por defecto, el último año filtrado en los filtros globales) |
| **Tipo**| Filtro de tipo de incidencia o "Todos los tipos"                       |
| **Top** | Cuántos subtipos mostrar: 5, 10 o 15                                   |

### 5.2. Tablas y gráfica

- **Tabla "Top subtipos"** (izquierda): los N subtipos más frecuentes, con total y porcentaje.
- **Tabla "Top 10 centros"** (derecha): los 10 centros con más incidencias del año/tipo elegido.
- **Gráfica de barras horizontales** (debajo): visualización de los subtipos con su volumen.

Cuando se cambia cualquiera de los selectores (año, tipo o top), las dos tablas y la gráfica se actualizan a la vez.

![Bloque Top subtipos y centros con los selectores año/tipo/top, las dos tablas y la gráfica de barras horizontales](./imagenes/captura-05-bloque-top-subtipos-y-centros.png)

---

## 6. Bloque 4: Evolución por año de los subtipos TOP

Gráfica de líneas que muestra **cómo han evolucionado los subtipos más frecuentes** a lo largo de los años seleccionados:

- Una línea por cada subtipo del Top N (los mismos del bloque anterior).
- Eje X: años. Eje Y: número de incidencias.

Usa los mismos selectores **Tipo** y **Top** del bloque anterior. Útil para detectar subtipos que están aumentando o disminuyendo de forma sostenida.

![Gráfica de líneas con la evolución por año de los subtipos TOP, una línea por subtipo](./imagenes/captura-06-bloque-evolucion-subtipos-top.png)

---

## 7. Bloque 5: Totales y tendencia interanual

Bloque de **6 KPI tiles** con cifras agregadas y la variación interanual. Útil para enseñar de un vistazo cómo va el año en curso respecto al anterior.

| KPI | Significado                                                                       |
|-----|-----------------------------------------------------------------------------------|
| **Total ENE–MES AÑO**       | Total acumulado del año en curso, hasta el mes actual (YTD)        |
| **Total ENE–MES AÑO ANT.**  | Total del mismo periodo del año anterior (mismas semanas)          |
| **Variación interanual**    | `(Actual − Anterior) / Anterior × 100`. Verde si baja, rojo si sube |
| **Cierre AÑO ANT.**         | Total completo del año anterior (12 meses), como referencia        |
| **Media mensual AÑO**       | Media de incidencias por mes del año en curso                      |
| **Media mensual histórica** | Media de las medias anuales de los años anteriores                 |

> **Nota:** la "Variación interanual" compara siempre **el mismo periodo** (no compara 4 meses contra 12, sino 4 contra 4). Cuando el año en curso termina, pasa a comparar cierres completos automáticamente.

![Bloque Totales y tendencia interanual con los 6 KPI tiles](./imagenes/captura-07-bloque-totales-y-tendencia-interanual.png)

---

## 8. Bloque 6: Cortes eléctricos

Análisis específico de **incidencias de DATOS** cuyo comentario menciona un **corte eléctrico** que ha afectado al cliente. La detección se hace automáticamente a partir del campo de comentario de la incidencia.

### 8.1. KPIs y gráficas

Estructura idéntica al bloque anterior:

- **6 KPI tiles**: total YTD actual, total YTD anterior, variación interanual, cierre año anterior, media mensual actual y media histórica.
- **Gráfica anual**: total de cortes por año (una sola línea).
- **Gráfica mensual comparada**: una línea por cada año seleccionado, eje X de Ene a Dic.

![Bloque Cortes eléctricos con los KPIs arriba y las gráficas anual y mensual debajo](./imagenes/captura-08-bloque-cortes-electricos-kpis-y-graficas.png)

### 8.2. Tabla pivot y Top centros con selector

- **Tabla pivot mensual** con los mismos selectores **Comparar/contra** del bloque 2.
- **Tabla Top 10 centros** con los centros que más cortes eléctricos han sufrido.
  - Selector **Año**: año concreto a analizar (por defecto, el año actual).
  - Selector **Mes**: "Todos" o un mes concreto (Enero–Diciembre).
  - El Top se recalcula al instante con los filtros elegidos.

Útil para detectar centros con problemas crónicos de suministro eléctrico que requieren actuación específica.

![Bloque Cortes eléctricos con la tabla pivot mensual y la tabla Top 10 centros con los selectores Año y Mes](./imagenes/captura-09-bloque-cortes-electricos-pivot-y-top.png)

---

## 9. Exportar datos

En la cabecera del dashboard hay dos botones de exportación:

| Botón       | Resultado                                                                    |
|-------------|------------------------------------------------------------------------------|
| **Excel**   | Descarga un fichero `.xlsx` con varias hojas (una por bloque) y las gráficas embebidas |
| **PDF**     | Descarga un `.pdf` generado a partir del Excel (logos en cada página)        |

**Pasos:**

1. Ajustar los filtros globales y los selectores de cada bloque al estado deseado.
2. Pulsar **Excel** o **PDF**.
3. El navegador captura las imágenes de las gráficas en pantalla y las envía al servidor junto con los filtros.
4. Se abre una pestaña nueva con la descarga.

**Hojas que contiene el Excel exportado:**

| Hoja                      | Contenido                                                  |
|---------------------------|------------------------------------------------------------|
| Volumen anual             | Tabla años × tipos + gráfica del bloque 1                  |
| Mensual                   | Tabla pivot años × meses + gráfica del bloque 2            |
| Subtipos TOP              | Tabla Top N subtipos + Top 10 centros + gráfica de barras  |
| Evolución subtipos        | Gráfica del bloque 4 (hoja propia)                         |
| Centros y resumen         | Top 10 centros del bloque 3 + bloque resumen               |
| Cortes mensual            | Tabla pivot cortes + gráfica mensual del bloque 6          |
| Cortes anual              | Gráfica anual de cortes (hoja propia)                      |
| Cortes top                | Tabla Top 10 centros con cortes (año y mes elegidos)       |

> **Nota:** las gráficas que aparecen en el PDF son **exactamente las que se ven en pantalla**. Si se quiere un PDF con un filtro o una comparación distinta, primero se ajusta el dashboard y después se exporta.

![Ejemplo de página del PDF exportado, con los logos de Telefónica y SERGAS en la cabecera y el contenido del bloque](./imagenes/captura-10-ejemplo-de-pagina-pdf-exportado.png)

---

## 10. Diferencias con los otros módulos KPIs

| Aspecto                | KPIs Inelcom              | KPIs Nubodata               | **KPIs CGE**                          |
|------------------------|---------------------------|-----------------------------|---------------------------------------|
| Qué mide               | Cumplimiento SLA          | Cumplimiento SLA tricolor   | **Volumen y tendencias**              |
| Período por defecto    | Semana anterior           | Semana anterior             | **Todos los años** (multiselección)   |
| Origen de datos        | Incidencias BDU           | Incidencias GLPI            | **Incidencias BDU** desde 2022         |
| Acceso                 | Restringido por OU        | Restringido por OU          | **Restringido por OU**                |
| Estructura             | 4 bloques de SLA          | 1 bloque tricolor           | **6 bloques analíticos**              |
| Exportación            | Excel + PDF (logos)       | Excel + PDF (logos)         | **Excel + PDF (logos + 6 gráficas)**  |

---

## 11. Acceso restringido

Como en KPIs Inelcom y KPIs Nubodata, el acceso al módulo está **restringido a determinados usuarios** según su grupo en el directorio Active Directory. Los operadores con cuenta en la unidad organizativa `UO_usuarios_dominio` no pueden entrar a este módulo y verán un mensaje de "Acceso restringido".

Si un usuario debe tener acceso y no lo tiene, contactar con el administrador del sistema.

---

*Manual para operadores y administradores CGE SERGAS. Versión 1.0 — Abril 2026.*
