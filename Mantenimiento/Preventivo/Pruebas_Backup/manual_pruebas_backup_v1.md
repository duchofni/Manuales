# Manual de Usuario: Submódulo Pruebas Backup

| Campo       | Valor                                                   |
|-------------|---------------------------------------------------------|
| **Módulo**  | Mantenimiento > Preventivo > Pruebas Backup             |
| **Versión** | 1.0                                                     |
| **Fecha**   | Mayo 2026                                               |
| **Para**    | Operadores CGE SERGAS                                   |

---

## Índice

1. [Para qué sirve este submódulo](#1-para-qué-sirve-este-submódulo)
2. [Cómo accedemos al submódulo](#2-cómo-accedemos-al-submódulo)
3. [Estructura del ciclo anual](#3-estructura-del-ciclo-anual)
4. [Abrir un nuevo ciclo](#4-abrir-un-nuevo-ciclo)
5. [Pantalla del ciclo en curso](#5-pantalla-del-ciclo-en-curso)
6. [Programar las semanas de una fase](#6-programar-las-semanas-de-una-fase)
7. [Coordinar la prueba con el centro](#7-coordinar-la-prueba-con-el-centro)
8. [Realizar la prueba — flujo Checklist + Marcar](#8-realizar-la-prueba--flujo-checklist--marcar)
9. [Estadísticas y exportación](#9-estadísticas-y-exportación)
10. [Cierre automático del ciclo](#10-cierre-automático-del-ciclo)
11. [Resumen rápido de botones](#11-resumen-rápido-de-botones)
12. [Preguntas frecuentes](#12-preguntas-frecuentes)

---

## 1. Para qué sirve este submódulo

Pruebas Backup nos ayuda a planificar y registrar las **pruebas periódicas** de las líneas de respaldo de los centros del parque SERGAS. Cada año comprobamos que las líneas REDUNDANTE y REDUNDANTE-2 funcionan: si la línea principal cae, la respaldo asume el servicio sin cortes.

Lo que hace el submódulo:

- Selecciona automáticamente los centros que entran en el ciclo (los que tienen redundancia real, no aquellos con sólo 1-2 accesos).
- Los reparte por fases según horario y criticidad.
- Nos permite repartir los centros por semanas (planificación trimestral o anual).
- Lleva registro de **fecha coordinada con el centro** y **fecha realizada**.
- Asocia un **checklist** Excel a cada prueba (con OnlyOffice integrado, lo rellenamos en línea).
- Cierra el ciclo automáticamente cuando todos los centros están realizados.

> Centros con menos de 3 accesos efectivos (PRINCIPAL + REDUNDANTE + REDUNDANTE-2) **no entran** en el ciclo, salvo que el centro esté marcado como **Crítica** y tenga al menos 2. Las líneas METROLAN, RTLD, DIBA y FIBRA OSCURA no cuentan a estos efectos.

---

## 2. Cómo accedemos al submódulo

1. Abrimos la **Web BDU** en el navegador.
2. En la barra superior pulsamos **Mantenimiento**.
3. Pulsamos la tarjeta **Preventivo** y seleccionamos **Pruebas Backup**.

> **Atajo:** también podemos llegar directamente con `?m=mantenimiento&sub=preventivo&proyecto=pruebas_backup` añadido al final de la URL.

---

## 3. Estructura del ciclo anual

Cada año es un **ciclo independiente** con su propio listado de centros. Solo puede haber un ciclo abierto a la vez.

Estados:

| Estado    | Qué significa                                                                                       |
|-----------|-----------------------------------------------------------------------------------------------------|
| Abierto   | Estamos trabajando en él: podemos coordinar fechas, programar semanas y marcar pruebas realizadas.  |
| Cerrado   | El año está terminado. Lo seguimos viendo en modo lectura, pero no podemos modificar nada.          |

Los centros se reparten en **4 fases** según su horario y criticidad:

| Fase | Nombre        | Centros                          |
|------|---------------|----------------------------------|
| 1    | Mañana        | Horario sólo de mañana.          |
| 2    | Extendido     | Horario extendido.               |
| 3    | 24H           | 24 horas, no críticos.           |
| 4    | Crítica       | 24 horas y marcados como críticos.|

La fase se calcula al abrir el ciclo y queda **fija para todo el año**, aunque el centro cambie de horario después.

---

## 4. Abrir un nuevo ciclo

Cuando entramos al submódulo y todavía no hay ningún ciclo abierto (o el último está cerrado), arriba a la derecha vemos un botón **🔓 Abrir ciclo YYYY**.

Pasos:

1. Pulsamos **🔓 Abrir ciclo YYYY**.
2. Confirmamos en el aviso emergente.
3. El sistema crea el ciclo, calcula los centros y las fases, y nos lleva al ciclo recién abierto.

> No podemos abrir un ciclo si hay otro abierto. Hay que cerrar (o terminar) el actual antes.

> Tampoco podemos reabrir un año que ya existe. Si necesitamos uno cerrado, lo seleccionamos en el desplegable de años para verlo en modo lectura.

---

## 5. Pantalla del ciclo en curso

La pantalla del ciclo tiene 4 zonas, de arriba abajo:

### 5.1. Cabecera

- **Selector de años**: cambiamos rápido entre los ciclos existentes.
- **📊 Estadísticas**: abre la subvista de KPIs y gráficos del año.
- **⬇ Excel**: descarga el listado actual filtrado en xlsx.
- **🔓 Abrir ciclo YYYY+1** (sólo si el año actual está cerrado): inicia el siguiente ciclo.

### 5.2. KPIs del ciclo

Una fila de tarjetas con:

- **Total** de centros del ciclo.
- **Realizados**.
- Por fase, **realizados / total**.
- Una **barra de progreso** con el porcentaje global.

### 5.3. Filtros de la tabla

- **Buscador** libre (nombre del centro, número administrativo o nemónico).
- **Fase**: filtra por una de las 4.
- **Semana**: filtra por semana ISO o "sin asignar".
- **Estado**: pendiente de coordinar / coordinada / realizada.
- Botón **📅 Programar semanas** (sólo si el ciclo está abierto). Ver [sección 6](#6-programar-las-semanas-de-una-fase).

### 5.4. Tabla de centros

| Columna       | Contenido                                                              |
|---------------|------------------------------------------------------------------------|
| Centro        | Nombre + chip ⚠ si es crítico + tipo de centro.                        |
| Horario       | Texto del horario.                                                     |
| Principal     | Servicio, Tipolinea, Administrativo y Nemónico de la línea PRINCIPAL.  |
| Redundante    | Idem para REDUNDANTE.                                                  |
| Redundante-2  | Idem para REDUNDANTE-2 (puede no existir).                             |
| Fase          | 1..4 con color por fase.                                               |
| Sem           | Semana ISO programada (— si aún no asignada).                          |
| F. Coordinada | Fecha y hora pactadas con el centro (editable inline).                 |
| F. Realizada  | Botones **Marcar** y **📋 Checklist** (ver [sección 8](#8-realizar-la-prueba--flujo-checklist--marcar)). |
| Usuario       | Quién marcó la prueba como realizada.                                  |

---

## 6. Programar las semanas de una fase

Sirve para repartir los centros de una fase en bloques semanales. Por ejemplo, queremos repartir los **120 centros de Fase 2** en grupos de 10 desde la **semana 14**.

Pasos:

1. Pulsamos **📅 Programar semanas**.
2. Rellenamos:
   - **Fase** (1, 2, 3 o 4).
   - **Centros/semana** (por defecto 10).
   - **Semana inicial** (por defecto la semana ISO actual).
   - Marcamos **Sobrescribir** sólo si queremos pisar las semanas ya asignadas.
3. Pulsamos **Aplicar** y confirmamos.

El sistema reparte los centros por orden alfabético: el primer bloque a la semana inicial, el segundo a +1, etc. Tope duro en la semana 52.

> Por defecto **sólo asigna a centros sin semana**. Si ya programamos antes y queremos reorganizar, tenemos que marcar **Sobrescribir**.

> Tras Aplicar volvemos al mismo año donde estábamos (no nos saca al selector de años).

---

## 7. Coordinar la prueba con el centro

Cuando llamamos al centro para concertar la prueba, registramos la fecha y hora pactadas:

1. En la fila del centro, pulsamos en el campo **F. Coordinada**.
2. Elegimos fecha y hora.
3. Se guarda solo. Aparece un botón ✕ para borrar la fecha si la cancelamos.

> El estado de la fila cambia automáticamente a **coordinada** y podemos filtrarla con el desplegable Estado.

---

## 8. Realizar la prueba — flujo Checklist + Marcar

Cuando vamos a hacer la prueba con el centro **seguimos un flujo en dos pasos para evitar olvidos**:

### 8.1. Abrir el checklist

1. En la fila del centro, pulsamos **📋 Checklist**.
2. Se nos abre una pestaña nueva con el **checklist en OnlyOffice**, ya con el centro identificado y listo para rellenar.
3. Rellenamos los apartados durante la prueba (firma de quién la hace, líneas probadas, observaciones, etc.).
4. Los cambios se guardan automáticamente cada pocos segundos. Cuando terminemos podemos cerrar la pestaña.

> **El botón Marcar está deshabilitado hasta que pulsamos Checklist por primera vez.** Esto garantiza que la prueba quede documentada antes de cerrarla en BDU.

> Si volvemos otro día, el checklist se conserva con todo lo que hayamos rellenado: el botón **📋 Checklist** abre el mismo fichero del centro, no genera uno nuevo.

> Cada año tiene su propio checklist por centro. El del año pasado queda archivado en el NAS del centro y no se pierde.

### 8.2. Marcar la prueba como realizada

1. Una vez completado el checklist, en la misma fila pulsamos **Marcar**.
2. Confirmamos en el aviso emergente.
3. La fila pasa a **realizada**, con la fecha y hora actuales y nuestro usuario.

> Si nos equivocamos, podemos pulsar el ✕ junto a la fecha para borrar la marca de realizada (y volver a marcarla más tarde).

### 8.3. ¿Dónde queda el checklist?

Cada centro tiene su propia carpeta en el NAS:

```
/mnt/centros/<id_centro>/MANTENIMIENTO/Pruebas_Backup/<año>/checklist.xlsx
```

Lo podemos ver también desde el módulo **Centros → Documentación** (pestaña MANTENIMIENTO).

---

## 9. Estadísticas y exportación

### 9.1. Estadísticas (📊)

Pulsamos **📊 Estadísticas** en la cabecera. Vemos:

- Progreso por fase.
- Progreso por semana ISO.
- Top de centros pendientes ordenados por días desde la fecha coordinada.
- Ratio de centros con/sin coordinación.

### 9.2. Exportación a Excel (⬇)

Pulsamos **⬇ Excel**. Descargamos el listado actual con los filtros aplicados (fase, semana, estado, búsqueda).

> El botón Excel **respeta los filtros activos**, así que podemos exportar por ejemplo "todos los centros de Fase 2 de la semana 18 que estén pendientes".

---

## 10. Cierre automático del ciclo

Cuando todos los centros del ciclo están **marcados como realizados**, el sistema **cierra el ciclo automáticamente**:

- El estado pasa a **✓ cerrado** (chip al lado del título).
- Quedan registradas la fecha de cierre y el usuario que marcó la última prueba.
- A partir de ese momento la pantalla pasa a modo lectura: no hay botones Marcar ni edición de fechas.
- Aparece la opción **🔓 Abrir ciclo YYYY+1** para empezar el siguiente año.

> Si el cierre se hizo por equivocación, no se puede reabrir desde la web. Hay que pedir al equipo de desarrollo que vuelva a abrir el año a mano (es excepcional y queda registro).

---

## 11. Resumen rápido de botones

| Botón                 | Dónde aparece                  | Qué hace                                                                |
|-----------------------|--------------------------------|-------------------------------------------------------------------------|
| 🔓 Abrir ciclo YYYY   | Cabecera (si no hay abierto)   | Crea el ciclo del año YYYY y carga los centros.                         |
| 📊 Estadísticas       | Cabecera                       | Subvista con KPIs y gráficos del ciclo.                                 |
| ⬇ Excel               | Cabecera                       | Descarga el listado filtrado.                                           |
| 📅 Programar semanas  | Encima de la tabla             | Reparte los centros de una fase por semanas ISO.                        |
| ✕ (al lado de fecha)  | Celda F. Coordinada            | Borra la fecha coordinada.                                              |
| 📋 Checklist          | Celda F. Realizada             | Abre el checklist Excel del centro en OnlyOffice (pestaña nueva).       |
| Marcar                | Celda F. Realizada             | Marca la prueba como realizada (sólo se habilita tras pulsar Checklist).|
| ✕ (junto a hora)      | Celda F. Realizada (realizada) | Borra la marca de realizada.                                            |

---

## 12. Preguntas frecuentes

### ¿Por qué no veo a uno de mis centros en el ciclo?

Probablemente no cumple el filtro: tiene menos de 3 accesos válidos (PRINCIPAL + REDUNDANTE + REDUNDANTE-2 sin contar METROLAN/RTLD/DIBA/FIBRA OSCURA), o está marcado como cerrado en el módulo Centros, o su Horario_id no es 1, 2 o 3.

### Han abierto un nuevo centro a mitad de año, ¿se añade?

Sí. La página, al cargar, sincroniza el listado: añade los nuevos que cumplan el filtro y elimina los que se hayan cerrado durante el ciclo. La fase de los ya existentes no se toca.

### Pulso 📋 Checklist y no se abre nada

- Comprobamos que el navegador no haya bloqueado el popup. Si bloquea, lo permitimos para `bdu.sergascge.local` y reintentamos.
- Si sale **"Plantilla maestra no encontrada"**, hay que avisar al CGE: la plantilla `/mnt/documentacion/plantillas/pruebas_backup/checklist.xlsx` no está disponible.
- Si sale **"Carpeta del centro no existe en NAS"**, tampoco existe `/mnt/centros/<id>/`. Lo arreglamos creando el centro en el módulo Centros (lo crea automáticamente al abrir su ficha).

### Quiero regenerar el checklist desde la plantilla limpia

Hay que borrar a mano `/mnt/centros/<id>/MANTENIMIENTO/Pruebas_Backup/<año>/checklist.xlsx`. La próxima vez que se pulse 📋 Checklist se vuelve a copiar la plantilla maestra.

### ¿Y si la plantilla cambia a mitad de ciclo?

Los centros que **ya tengan checklist** conservan el suyo (con todo lo rellenado). Los que **aún no lo tengan** cogerán la versión nueva la primera vez que pulsen 📋 Checklist.

### ¿Puedo borrar una fila del listado?

No directamente. Las altas y bajas se gestionan automáticamente: si un centro ya no cumple el filtro o se marca como cerrado, sale del listado al recargar.

### Veo un centro de fase 4 que no debería ser crítico

La fase queda **congelada** al abrir el ciclo. Si el centro cambió de criticidad después, en el ciclo en curso seguirá apareciendo en su fase original. En el próximo ciclo del año siguiente se recalculará.
