# Manual de Usuario: Módulo Licencias OXE/CISCO

| Campo       | Valor                                    |
|-------------|------------------------------------------|
| **Módulo**  | Mantenimiento > Tareas > Licencias       |
| **Versión** | 1.5                                      |
| **Fecha**   | Abril 2026                               |
| **Para**    | Operadores CGE SERGAS                    |

---

## 1. Descripción general

El módulo Licencias permite realizar el **seguimiento mensual** de las licencias de telefonía: OXE (Alcatel), CISCO (CUCM), NGN y SBC. Incluye un dashboard con gráficas, formularios de entrada de datos, recogida automática por SSH, gestión de capturas de pantalla y generación de informes en PDF.

---

## 2. Dashboard principal

Al entrar en Licencias verás el dashboard con:

### 2.1. Tabla de meses

- Lista de todos los meses registrados con su **progreso** (porcentaje completado).
- Cada mes muestra el estado de 5 secciones: **OXE**, **CISCO**, **Capturas**, **NGN**, **SBC**.
- Los meses completos aparecen marcados como tales.

### 2.2. Alertas

- Si alguna licencia tiene menos del **5% libre** en el último mes, aparecerá una alerta en rojo.

### 2.3. Gráficas

El dashboard muestra 3 gráficas de evolución:
- **OXE**: % de licencias IP libres por nodo (los 6 principales).
- **CISCO**: % disponible medio por cluster (hosp_pro, chus, c061_pro).
- **NGN**: picos históricos APV/AUIP.

[CAPTURA: Dashboard de Licencias mostrando la tabla de meses, las alertas y las 3 gráficas de evolución]

### 2.4. Acceso rápido

- Botón para **crear o abrir** el mes actual.
- Selector de **mes histórico** (año + mes) para consultar datos anteriores.

---

## 3. Crear un nuevo mes

1. En el dashboard, pulsa el botón de **acceso rápido al mes actual**, o selecciona un año y mes concreto.
2. Si el mes no existía, se creará automáticamente.
3. Se abrirá la vista de **detalle del mes**.

---

## 4. Detalle de un mes

La vista de detalle muestra una **barra de progreso** con las 5 secciones:

| Sección    | Descripción                                   |
|------------|-----------------------------------------------|
| OXE        | Datos de licencias de los 12 nodos Alcatel    |
| CISCO      | Datos de licencias CISCO por cluster          |
| Capturas   | Capturas de pantalla de los sistemas          |
| NGN        | Datos de picos NGN                            |
| SBC        | Datos de codecs SBC                           |

Cada sección tiene un icono que indica si está completada. Pulsa en el enlace de cada sección para acceder a su formulario.

[CAPTURA: Vista de detalle de un mes con la barra de progreso mostrando las 5 secciones]

---

## 5. Formulario OXE

### 5.1. Rellenar datos de los nodos

1. Accede a la sección **OXE** desde el detalle del mes.
2. Verás una tabla con los **12 nodos** OXE (Santiago, Coruña, Lugo, Ourense, Pontevedra, Vigo, Ferrol, Barbanza, H. Cee, Burela, Verín, 061).
3. Para cada nodo, rellena los campos:
   - **IP**: Instaladas y Usadas
   - **Analógicas**: Instaladas y Usadas
   - **Digitales**: Instaladas y Usadas
   - **Consolas 4059**
   - **G729 Server**: Usadas y Total
   - **Links SIP**: Usados y Total
   - **Links H323**: Usados y Total
4. Debajo de la tabla verás **badges de colores** con el % de IP libre por nodo:
   - **Verde**: más del 15% libre (correcto)
   - **Naranja**: entre 5% y 15% libre (alerta)
   - **Rojo**: menos del 5% libre (crítico)
5. Pulsa **Guardar datos OXE**.

[CAPTURA: Formulario OXE con la tabla de nodos y los badges de porcentaje debajo]

### 5.2. Recoger datos OXE automáticamente

En lugar de rellenar a mano, puedes recoger los datos directamente de los equipos:

1. Pulsa **Recoger automáticamente**.
2. Introduce tus **credenciales SSH** (usuario y contraseña).
3. Pulsa **Lanzar recogida**.
4. Aparecerá una **barra de progreso** mientras se conecta a cada nodo.
5. Al terminar, verás una **tabla con los datos recogidos**.
6. Revisa los datos y pulsa **Guardar** para almacenarlos en la base de datos.

[CAPTURA: Recogida automática OXE mostrando la barra de progreso y los datos pendientes de guardar]

---

## 6. Formulario CISCO

1. Accede a la sección **CISCO** desde el detalle del mes.
2. Verás una tabla con filas para cada **tipo de licencia** (11 tipos: UC Manager Enhanced Plus, Enhanced, Basic, Essential, Emergency Responder, Speech Connect, SRST, CUWL, Telepresence, Unity Connection Basic/Enhanced).
3. Para cada tipo, hay columnas por **cluster**: hosp_pro, chus, c061_pro, c061_pre, hosp_pre.
4. En cada celda, introduce las licencias **Instaladas** y **Usadas**.
5. El **% libre** se calcula automáticamente en tiempo real al cambiar los valores.
6. Pulsa **Guardar datos CISCO**.

[CAPTURA: Formulario CISCO con la tabla de tipos de licencia por cluster y los porcentajes calculados]

> **Nota:** También puedes importar datos CISCO desde un fichero CSV/Excel pulsando el botón correspondiente.

---

## 7. Formulario SBC

1. Accede a la sección **SBC** desde el detalle del mes.
2. Verás filas de **codecs** con campos:
   - **Nombre** del codec
   - **Canales totales**
   - **Canales usados**
3. Rellena los datos y pulsa **Guardar datos SBC**.

---

## 8. Importar NGN

1. Accede a la sección **NGN** desde el detalle del mes.
2. Importa los datos de picos NGN.
3. Para cada serie puedes ver el nombre, fecha de pico y porcentaje de ocupación.
4. Hay un **modal con gráficas** que muestra la evolución histórica de los datos NGN.

[CAPTURA: Sección NGN con los datos importados y el botón para ver las gráficas]

---

## 9. Generar PDF

1. Desde el detalle del mes, pulsa **Generar PDF**.
2. El PDF se genera en segundo plano. Verás un indicador de progreso.
3. Cuando esté listo, aparecerá un **enlace de descarga**.
4. El PDF incluye:
   - Datos OXE con tablas y gráficas
   - Datos CISCO con tablas
   - Capturas de pantalla
   - Datos NGN con gráficas
   - Datos SBC

[CAPTURA: Enlace de descarga del PDF generado]

---

## 10. Capturas de pantalla

### 10.1. Ver capturas

1. Accede a la sección **Capturas** desde el detalle del mes.
2. Verás las capturas organizadas por tipo (CUCM CHUS, CUCM C1-C3, CUCM 061, UCCX, SSM, SBC, EOM, IVR, etc.).
3. Cada captura muestra una **vista previa** de la imagen.

### 10.2. Subir una captura

1. En el tipo de captura correspondiente, pulsa **Subir**.
2. Selecciona el fichero de imagen.
3. La captura se subirá y aparecerá la vista previa.

### 10.3. Eliminar una captura

1. Pulsa el botón de **eliminar** junto a la captura que quieras borrar.
2. Confirma la eliminación.

[CAPTURA: Sección de capturas mostrando varias imágenes con los botones Subir y Eliminar]

---

## 11. Flujo de trabajo mensual recomendado

1. **Crear el mes** actual desde el dashboard.
2. **Recoger datos OXE** automáticamente (o rellenar manualmente).
3. **Rellenar datos CISCO** (manual o importar).
4. **Rellenar datos SBC**.
5. **Importar datos NGN**.
6. **Subir las capturas** de pantalla de cada sistema.
7. **Generar el PDF** del mes.
8. Revisar el PDF descargado.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
