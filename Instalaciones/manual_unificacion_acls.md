# Manual de Usuario: Proyecto Unificación FILTRO_LAN_SEDE

| Campo        | Valor                                |
|--------------|--------------------------------------|
| **Módulo**   | Instalaciones — Proyectos            |
| **Proyecto** | Unificación FILTRO_LAN_SEDE          |
| **Versión**  | 2.1                                  |
| **Fecha**    | Abril 2026                           |
| **Para**     | Operadores CGE SERGAS                |

---

## Índice

1. [Para qué sirve este proyecto](#1-para-qué-sirve-este-proyecto)
2. [Cómo accedemos al proyecto](#2-cómo-accedemos-al-proyecto)
3. [La pantalla principal](#3-la-pantalla-principal)
4. [Filtrar la tabla](#4-filtrar-la-tabla)
5. [Ejecutar el comparador en un centro](#5-ejecutar-el-comparador-en-un-centro)
6. [Interpretar el informe](#6-interpretar-el-informe)
7. [Aplicar el estándar al router y cerrar el centro](#7-aplicar-el-estándar-al-router-y-cerrar-el-centro)
8. [Reejecutar un centro](#8-reejecutar-un-centro)
9. [Exportar a Excel](#9-exportar-a-excel)
10. [Exportar a ZIP](#10-exportar-a-zip)
11. [Estadísticas](#11-estadísticas)
12. [Dudas frecuentes](#12-dudas-frecuentes)

---

## 1. Para qué sirve este proyecto

Todos los routers de los centros SERGAS tienen una **lista de control de acceso** llamada `FILTRO_LAN_SEDE`. Esa lista decide qué tráfico se permite salir de la red del centro hacia el exterior.

Con los años, esa lista se ha ido ensuciando: cada centro tiene la suya con entradas viejas, repetidas u obsoletas. El objetivo del proyecto es **dejar todos los centros con la misma lista limpia y estandarizada**, más un pequeño bloque propio del centro cuando haga falta.

La aplicación lo automatiza:

- **Lee** la configuración actual del router del centro.
- **Compara** entrada por entrada contra el estándar.
- **Clasifica** cada línea (cubierta, eliminar, mantener, sospechosa, etc.).
- **Genera** la lista estándar lista para aplicar al router.
- Nos permite **marcar el centro** cuando ya se ha aplicado.

Hay **346 centros** en el proyecto.

---

## 2. Cómo accedemos al proyecto

1. Abrimos la **Web BDU** en el navegador.
2. En el menú superior pulsamos **Instalaciones**.
3. En la parte superior, abrimos la pestaña **Proyectos**.
4. En la categoría **Mantenimiento**, pulsamos la tarjeta **Unificación FILTRO_LAN_SEDE**.

![Pantalla de Proyectos con las dos categorías (Provisión y Mantenimiento) y la tarjeta de Unificación ACLs marcada](./imagenes/captura-01-pantalla-de-proyectos-con-las-dos-catego.png)

---

## 3. La pantalla principal

Una vez dentro vemos una página con tres zonas:

### 3.1. Cabecera

- A la izquierda, el botón **← Proyectos** para volver.
- En el centro, el título del proyecto.
- A la derecha, el botón **Estadísticas** (ver [sección 11](#11-estadísticas)).

### 3.2. Indicadores (KPIs)

Justo debajo de la cabecera tenemos 4 números grandes y una barra de progreso:

| Indicador           | Qué significa                                                                            |
|---------------------|------------------------------------------------------------------------------------------|
| **Total**           | Cuántos centros tiene el proyecto en total.                                              |
| **Ejecutados**      | Centros donde el estándar ya se ha aplicado al router.                                   |
| **Pdte cliente**    | Centros con el informe ya generado, esperando que el cliente o técnico lo aplique al router. |
| **Pdte ejecutar**   | Centros sin procesar todavía.                                                            |

La **barra de progreso** muestra el porcentaje de centros ya **Ejecutados** sobre el total.

### 3.3. Filtros y acciones

Una barra con:

- Buscador libre (escribimos nombre de centro o nemónico).
- Selector de **Área Sanitaria**.
- Selector de **Estado**.
- Selector de **Tipo router** (Teldat o Cisco).
- Contador de centros que cumplen los filtros.
- Botón **Exportar Excel**.
- Botón **Exportar ZIP**.
- Botón **Marcar seleccionados como aplicados** (solo aparece cuando hay centros marcados con casilla).

### 3.4. Tabla de centros

Una fila por centro. Las columnas son:

| Columna             | Qué muestra                                                  |
|---------------------|--------------------------------------------------------------|
| **Centro**          | Nombre del centro.                                           |
| **Área Sanitaria**  | A qué AS pertenece (Santiago, Coruña…).                      |
| **Tipo sede**       | Categoría de la sede (CS, PAC, Hospital…).                   |
| **Nemónico**        | Identificador del router.                                    |
| **Router**          | Teldat o Cisco. Vacío si aún no se ha ejecutado.             |
| **ACEs**            | Número total de entradas en la ACL del centro.               |
| **OK**              | Cuántas están ya cubiertas por el estándar.                  |
| **WL**              | Cuántas se pueden eliminar (whitelist).                      |
| **IntraLAN**        | Tráfico interno del centro (siempre se mantiene).            |
| **Huérf. +**        | Permits huérfanos (candidatas a revisar).                    |
| **Huérf. −**        | Denys huérfanos.                                             |
| **⚠ AS**            | Anomalías Cross-AS detectadas (en rojo).                     |
| **Fecha**           | Cuándo se ejecutó el comparador.                             |
| **Estado**          | El estado actual del centro.                                 |
| (acciones)          | Botones de la fila (ver siguiente apartado).                 |

### 3.5. Botones de cada fila

Según el estado del centro vemos unos u otros botones:

| Estado              | Botones disponibles                                                          |
|---------------------|------------------------------------------------------------------------------|
| **Pdte ejecutar** ⏳| **▶** (azul) — Ejecutar comparador.                                          |
| **Pdte cliente** 💬 | Casilla + **📄** (verde) Ver informe + **↻** (naranja) Reejecutar.           |
| **Ejecutado** ✓     | **📄** (verde) Ver informe + **↻** (naranja) Reejecutar.                     |

![Tabla principal con varias filas en distintos estados, mostrando los botones de la columna de acciones](./imagenes/captura-02-tabla-principal-con-varias-filas-en-dist.png)

---

## 4. Filtrar la tabla

Podemos combinar varios filtros a la vez. Conforme tecleamos o cambiamos un desplegable, la tabla y los contadores se actualizan al instante.

**Casos típicos:**

- Para revisar solo los centros que ya tienen informe esperando aplicar al router: filtramos **Estado = Pdte cliente**.
- Para empezar a procesar centros pendientes de un área concreta: filtramos **Estado = Pdte ejecutar** + **AS = (la que toque)**.
- Para localizar centros con anomalías: ordenamos visualmente por la columna ⚠ AS o exportamos a Excel y filtramos allí.

> **Importante:** los botones **Exportar Excel** y **Exportar ZIP** descargan solo los centros que cumplen los filtros activos en ese momento.

---

## 5. Ejecutar el comparador en un centro

Cuando un centro está en estado **Pdte ejecutar**, su fila tiene un botón **▶ azul**. Al pulsarlo:

1. La aplicación busca automáticamente la **última configuración del router** en el NAS del centro.
2. Lee la ACL FILTRO_LAN_SEDE.
3. La compara contra el estándar y la whitelist.
4. Genera 3 ficheros de salida y los guarda en el NAS.
5. Nos lleva directamente al **visor del informe** (sin tener que recargar).
6. El estado del centro pasa automáticamente a **Pdte cliente**.

**Si no encuentra la configuración en el NAS,** la aplicación abre la página en **modo manual** y nos muestra un cuadro de texto. Pegamos ahí el `show running-config` del router y pulsamos **Procesar**.

![Página de ejecución en modo automático, mostrando el centro y el resumen de procesado](./imagenes/captura-03-pagina-de-ejecucion-en-modo-automatico-m.png)

---

## 6. Interpretar el informe

El visor tiene **3 pestañas**:

### 6.1. Pestaña Informe

Texto completo con el desglose de la ACL del centro:

- Resumen con totales (cuántas cubiertas, cuántas a eliminar, etc.).
- Cada entrada original del centro etiquetada con su clasificación.
- Bloque final destacando las **anomalías Cross-AS** si las hay.

**Categorías posibles:**

| Categoría                | Qué significa                                                                | Qué hacemos                                                                 |
|--------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **CUBIERTA**             | El estándar ya tiene una entrada equivalente o más amplia.                   | Eliminar del centro — desaparece al aplicar el estándar.                    |
| **ELIMINAR** (whitelist) | Coincide exactamente con la lista blanca de "se puede borrar".               | Eliminar — desaparece al aplicar el estándar.                               |
| **INTRA_LAN**            | Tráfico interno del propio centro.                                            | Mantener siempre. El estándar la conserva.                                  |
| **CATCH_ALL**            | Es el `deny ip any any` o `permit ip any any` final.                          | Se reemplaza por el del estándar.                                           |
| **HUÉRFANA**             | No está cubierta por nada.                                                    | Revisar caso a caso. Suele ir al bloque ACCESOS CENTRO.                     |
| **Cross-AS** ⚠           | Apunta a IPs de otra Área Sanitaria.                                         | Sospechosa — probablemente obsoleta. Confirmamos con el cliente antes de eliminar. |

### 6.2. Pestaña Huérfanas

Aquí están **solo las huérfanas**, en formato listo para pegar en el bloque **ACCESOS CENTRO** del estándar. Es la lista que tenemos que **revisar con el cliente** antes de aplicar.

### 6.3. Pestaña Estándar Teldat

La ACL estándar generada para el centro, en sintaxis **Teldat**, lista para copiar y pegar en el router. Si el centro tuviera Cisco, igualmente se genera en Teldat (sintaxis principal del proyecto) y el técnico la traduce o usa la herramienta de traductor que está en el módulo **Plantillas**.

Características de la ACL generada:

- Está numerada por **bloques** con espacio para crecer (B1: entries 10-1000, B2: 1010-2000, etc.).
- La primera y última entry de cada bloque llevan una `description` identificativa entre comillas: `description "INI SAMBA AREA SANITARIA"`, `description "FIN SAMBA AREA SANITARIA"`.

### 6.4. Botones del visor

En cada pestaña, arriba a la derecha:

- **Copiar** — copia el contenido al portapapeles.
- **Descargar** — descarga un fichero `.txt`.

Y arriba en la cabecera del visor:

- **✓ Marcar como aplicado** (solo aparece si el centro está en Pdte cliente).

![Visor del informe con las 3 pestañas y los botones](./imagenes/captura-04-visor-del-informe-con-las-3-pestanas-y-l.png)

---

## 7. Aplicar el estándar al router y cerrar el centro

El paso de aplicar la ACL al router lo hace el **técnico N1 del CGE**. Una vez aplicado:

### 7.1. Cerrar un centro individual

1. Entramos en el visor de ese centro (botón 📄 verde de su fila).
2. Pulsamos **✓ Marcar como aplicado** en la cabecera.
3. Confirmamos. El centro pasa a **Ejecutado**.

### 7.2. Cerrar varios centros a la vez

1. En la tabla principal filtramos por **Estado = Pdte cliente**.
2. Marcamos las casillas de los centros que queramos cerrar.
3. Aparece el botón **✓ Marcar seleccionados como aplicados (N)** en la barra de filtros (con el número de seleccionados entre paréntesis).
4. Lo pulsamos. Confirmamos.
5. Todos los centros seleccionados pasan a **Ejecutado** y la página se recarga.

> El campo **Usuario** de cada fila se rellena automáticamente con nuestro LDAP al marcar como aplicado.

![Tabla con varias casillas marcadas y el botón de marcado masivo visible](./imagenes/captura-05-tabla-con-varios-checkboxes-marcados-y-e.png)

---

## 8. Reejecutar un centro

A veces hace falta volver a pasar el comparador a un centro ya procesado:

- Se actualizó el estándar o la whitelist.
- El cliente pidió una segunda revisión.
- Hubo un cambio en el router del centro.

Pulsamos el botón **↻ naranja** en la fila del centro. Vuelve a arrancar el proceso completo (descrito en la [sección 5](#5-ejecutar-el-comparador-en-un-centro)) y sobreescribe los ficheros generados.

---

## 9. Exportar a Excel

El botón **⬇ Exportar Excel** en la barra de filtros descarga un fichero `.xlsx` con **solo la tabla** del listado.

- Respeta los **filtros activos**: si filtramos por Lugo + Pdte cliente, solo salen esos centros.
- El Excel tiene la cabecera azul, autofiltro activado y la primera fila congelada.
- Nombre del fichero: `unificacion_filtro_lan_sede_AAAAMMDD_HHMM.xlsx`.

Útil para enviar al cliente, llevar a una reunión, hacer cuentas aparte, generar nuestro propio listado por AS, etc.

---

## 10. Exportar a ZIP

El botón **⬇ Exportar ZIP** descarga un paquete completo con:

- `listado.csv` — la tabla de los centros filtrados, en CSV.
- Una carpeta por cada centro **que ya tiene informe** (Pdte cliente o Ejecutado), con sus tres ficheros:
  - `<nemonico>_informe.txt`
  - `<nemonico>_huerfanas.txt`
  - `<nemonico>_estandar_teldat.txt`

También respeta los filtros activos. Útil para enviar al cliente todo el trabajo de un área sanitaria de una sola vez.

---

## 11. Estadísticas

Pulsamos el botón **📊 Estadísticas** en la cabecera. Se abre una página con:

### 11.1. Indicadores

Los mismos KPIs que el listado, con dos extras:

- **% Completado** — porcentaje de centros ejecutados.
- **Cross-AS ⚠** — total de anomalías Cross-AS detectadas en todos los centros procesados.

### 11.2. Gráficas

Cuatro pares de **donut + barras**, uno al lado del otro:

| Gráfica                | Qué muestra                                                                  |
|------------------------|------------------------------------------------------------------------------|
| **Por AS**             | Reparto de centros entre las 7 áreas sanitarias.                             |
| **Por estado**         | Cuántos centros en cada estado (pdte ejecutar / pdte cliente / ejecutado).   |
| **Por router**         | Cuántos centros Teldat vs Cisco vs sin ejecutar.                             |
| **ACEs clasificadas**  | Sumatorio de las 5 categorías en todos los centros: Cubiertas, Whitelist, IntraLAN, Huérfanas+, Huérfanas−. |

![Página de estadísticas con los KPIs arriba y las 4 gráficas](./imagenes/captura-06-pagina-de-estadisticas-con-los-kpis-arri.png)

Volvemos al listado pulsando el botón **← Volver a la tabla** arriba a la izquierda.

---

## 12. Dudas frecuentes

### Al pulsar ▶ aparece la página en blanco

La aplicación no encontró la configuración del router en el NAS. Avisamos al técnico responsable o usamos el modo manual pegando el `show run` del router.

### Un centro debería estar en el proyecto y no aparece

- Comprobamos en el detalle del centro (módulo Centros) que tiene **Área Sanitaria** asignada.
- Si no está dado de alta en el proyecto, avisamos al administrador para que lo añada a la lista.

### El comparador me marca como ELIMINAR una entrada que el cliente quiere conservar

La entrada está en la whitelist `aces_permitidas_eliminar.txt`. Si el cliente discrepa, lo comunicamos para que se revise el contenido de la whitelist y, si procede, se quite esa línea.

### Una entrada SAMBA aparece como CUBIERTA pero al aplicar el estándar se rompe el tráfico

**No debería ocurrir** — el comparador está diseñado para no tapar entradas SAMBA con whitelists genéricas. Si pasa, avisamos al equipo de desarrollo con el nombre del centro y la entrada concreta.

### Hay muchas anomalías Cross-AS en un centro

Suele ser señal de que el centro tuvo en su día conexiones que ya no existen, o bien que cambió de AS y quedaron entradas viejas. **Revisamos con el cliente antes de descartar nada.**

### ¿Podemos dar marcha atrás tras marcar un centro como aplicado?

Si nos equivocamos, pulsamos **↻ Reejecutar** y se vuelve a generar el informe. El estado queda de nuevo en **Pdte cliente** hasta que se vuelva a aplicar.

### ¿Quién ve los ficheros del NAS?

Cualquier usuario autorizado puede acceder al NAS por SMB. Los ficheros generados están en:

```
/mnt/centros/tareas/unificacion_acls/<area>/<nemonico>/
```

### ¿Cada cuánto debemos revisar el estándar y la whitelist?

Cuando aparezcan muchas huérfanas iguales en centros del mismo AS, es señal de que esa entrada debería incorporarse al bloque del AS en el estándar. Lo comunicamos para actualizar los catálogos.

---

## Soporte

Cualquier incidencia o sugerencia, abrimos un ticket en el sistema habitual o contactamos con el administrador de la aplicación.

---

*Manual para operadores CGE SERGAS. Proyecto Unificación FILTRO_LAN_SEDE v1.6 — Abril 2026.*
