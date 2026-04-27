# Manual de Usuario: Submódulo DCT

| Campo       | Valor                                                   |
|-------------|---------------------------------------------------------|
| **Módulo**  | Mantenimiento > Preventivo > DCT                        |
| **Versión** | 1.0                                                     |
| **Fecha**   | Abril 2026                                              |
| **Para**    | Operadores CGE SERGAS                                   |

---

## 1. ¿Qué es el submódulo DCT?

Los Dispositivos de Control de Tensión (DCT) son aparatos instalados en los centros de salud que vigilan el suministro eléctrico. Cuando hay un corte de luz, el DCT envía un SMS; cuando vuelve la luz, envía otro SMS avisando.

Este submódulo:

- Recibe esos SMS automáticamente desde los ~405 DCTs del parque SERGAS.
- Registra cada corte y recuperación en base de datos.
- Envía un correo al CGP cada vez que detecta un corte o una recuperación.
- Permite consultar al DCT su estado (temperatura, alarmas) mediante un test.
- Genera estadísticas por provincia, área sanitaria, mes y top de centros con más cortes.
- Exporta informes profesionales en Excel o PDF para enviar al cliente.

No hace falta que hagas nada para que funcione: los SMS se procesan solos y los correos se envían solos. Solo entras aquí cuando quieres consultar información o lanzar tests.

---

## 2. Cómo llegar al submódulo

1. En el menú de la BDU, ve a **Mantenimiento**.
2. Entra en **Preventivo**.
3. Pulsa la tarjeta **DCT · Dispositivos de Control de Tensión**.

Aparece el panel principal con los KPIs del parque, un buscador para lanzar un test y los últimos 50 eventos.

---

## 3. Panel principal (dashboard)

### 3.1. Barra de KPIs

En la parte superior verás 5 tarjetas:

- **Total DCTs**: cuántos DCTs hay operativos en el parque.
- **Cortes 24h**: cuántos cortes se han registrado en las últimas 24 horas.
- **Cortes 30d**: cuántos en los últimos 30 días.
- **Tests 7d**: cuántos tests se han lanzado esta semana.
- **Timeouts 30d**: cuántos tests no respondieron a tiempo (ver sección Tests).

### 3.2. Buscador para lanzar test individual

Debajo de los KPIs tienes un campo de texto. Escribe el nombre del centro o el nº DCT y se autocompleta. Pulsa sobre un resultado → se abre el botón **🔍 Lanzar #016#**. Más detalle en la sección 6.

### 3.3. Últimos eventos

Tabla con los 50 eventos más recientes, columnas:

| Columna | Significado |
|---|---|
| Fecha | Cuándo llegó el SMS |
| Centro | Nombre del centro |
| Tipo | Corte ⚡ / Recuperación ✓ / Respuesta test 🔍 / Alerta GSM 📶 / Desconocido |
| SMS | Vista previa del texto recibido (al pasar el ratón ves el completo) |

### 3.4. Botones de navegación

Arriba del todo:

- **📋 Ver todos los centros**: listado completo de los ~405 DCTs con filtros.
- **📜 Histórico**: todos los eventos con filtros avanzados y paginación.
- **📊 Estadísticas**: gráficos y KPIs, botones de exportar informe.
- **⚙ Configuración**: panel de envío de comandos.

---

## 4. Listado de centros

Pulsa **📋 Ver todos los centros** desde el panel principal. Ves los ~405 DCTs en una tabla con:

- Filtro por **Área Sanitaria**.
- Filtro por **Provincia**.
- **Buscador** libre (nombre de centro, nº DCT).
- Filtro por **estado del último evento** (OK / corte pendiente de recuperación / sin eventos aún).

Cada fila tiene enlaces al historial de ese centro y al buscador del panel (para lanzarle un test).

---

## 5. Histórico de eventos

Pulsa **📜 Histórico** desde el panel principal. Ves todos los eventos (no solo los 50 últimos) con:

- Filtro por **tipo** (corte, recuperación, respuesta test, alerta GSM, desconocido).
- Filtro por **centro**.
- Filtro por **rango de fechas**.
- **Paginación**.

Útil para:
- Repasar la actividad de un centro concreto.
- Confirmar si un corte fue reportado y cuánto duró hasta el restore.
- Auditar qué tests han ido bien y cuáles han fallado.

---

## 6. Lanzar un test individual

Un "test" consiste en enviar el SMS **#016#** al DCT. El DCT responde con un mensaje que incluye las temperaturas (interna y externa), los rangos de alarma y si tiene activada la alerta de corte eléctrico.

### 6.1. Cómo lanzarlo

1. En el panel principal, escribe el centro en el buscador.
2. Pulsa sobre el resultado.
3. Aparece el botón **🔍 Lanzar #016#**. Pulsa.
4. Se envía el SMS y se crea un test en estado **pendiente**.

### 6.2. Ver la respuesta

- La respuesta del DCT llega por SMS en unos segundos (hasta 1-2 min dependiendo de la cobertura).
- El evento aparece en **Últimos eventos** como tipo **🔍 Respuesta test**.
- En la lista de tests (Tareas → Test DCT) puedes ver la asociación con el test pendiente y los valores extraídos.

### 6.3. Si no responde

Si pasan **7 minutos** sin respuesta, el test se marca automáticamente como **timeout** (al entrar a cualquier panel de tests).

Posibles causas:
- DCT apagado o sin cobertura.
- SIM del DCT de baja.
- DCT físicamente dañado.

Desde el detalle del lote puedes **reintentar individual** para volver a lanzar #016# al mismo centro.

---

## 7. Test DCT Masivo (tarea semanal)

Se lanza desde **Mantenimiento → Tareas → Test DCT** (no desde aquí). Envía #016# a los ~405 DCTs para verificar la salud del parque. Tarda ~5 horas porque los SMS salen en lotes de 20 cada 10 min (evita saturar Movistar).

Consulta el manual del módulo **Tareas** para el detalle completo.

---

## 8. Estadísticas

Pulsa **📊 Estadísticas** desde el panel principal.

### 8.1. Filtros

Arriba tienes dos desplegables:
- **Rango**: Últimos 30 días / 90 días / 1 año / Histórico completo.
- **Top**: cuántos centros mostrar en el gráfico de top (10 / 20 / 50 / 100).

Pulsa **Aplicar** para refrescar.

### 8.2. Gráficos

- **Top N centros con más cortes** (barras horizontales).
- **Cortes por Provincia** (donut + tabla).
- **Cortes por Área Sanitaria** (donut + tabla).
- **Cortes por mes (últimos 12)** (barras).

### 8.3. KPIs

- **Cortes totales**: número real de incidencias eléctricas en el rango seleccionado (ver nota técnica abajo).
- **Recuperaciones**: SMS de RESTORED recibidos.
- **Centros afectados**: cuántos centros han tenido al menos una incidencia.

> **Nota técnica importante:** un "corte" no equivale siempre a recibir el SMS LOST. Muchos DCTs no logran enviarlo porque al cortarse la luz del centro la batería del DCT no aguanta, o la torre GSM Movistar de la zona también se queda sin luz. En esos casos solo llega el SMS RESTORED cuando vuelve la electricidad. El KPI cuenta cada incidencia real aunque solo llegue uno de los dos SMS.

### 8.4. Exportar informe

Dos botones junto al filtro:

- **⬇ Excel**: descarga un fichero `.xlsx` con 2 hojas (Resumen Visual con logos y gráficos + Detalle con tablas).
- **📄 PDF**: lo mismo pero convertido a PDF automáticamente.

Usa el rango y top seleccionados en los filtros. Apto para enviar al cliente.

---

## 9. Configuración (envío de comandos)

Pulsa **⚙ Configuración** desde el panel principal.

### 9.1. Catálogo de comandos

Verás una lista de comandos SMS soportados por el DD5241 con:
- Código (ej. `#016#`).
- Nombre y descripción.
- Qué respuesta esperar.

### 9.2. Formulario de envío

Por cada comando puedes elegir el destino:

1. **Individual**: selector de centro. Envía el comando solo a ese DCT.
2. **Masivo por AS**: selector de Área Sanitaria. Envía a todos los DCTs activos de esa área.
3. **Masivo total**: a los ~405 DCTs (requiere confirmación escribiendo MASIVO).
4. **Manual**: introduces un número de teléfono arbitrario (para depuración).

### 9.3. Auditoría

Todo envío queda registrado en la tabla de auditoría `DCT_Comandos` con fecha, usuario LDAP, comando, destino y número de centros afectados.

---

## 10. Correos automáticos de alerta

Cada vez que se detecta un **corte** o una **recuperación** se envía un correo automático a:

- **Destino**: `cgp.sergas@telefonica.com`
- **Asunto**:
  - `CORTE SUMINISTRO ELECTRICO - <NOMBRE CENTRO>` si es corte
  - `SUMINISTRO ELECTRICO RESTAURADO - <NOMBRE CENTRO>` si es recuperación
- **Cuerpo**: fecha, número remitente del DCT y el texto SMS recibido.

No hay configuración a cambiar — funciona en cuanto entra un SMS válido. Si en algún momento necesitas modificar el destinatario, hay que editar el fichero `lib/correo.php` (pedir al equipo técnico).

---

## 11. Resumen rápido de botones

| Botón | ¿Dónde? | ¿Qué hace? |
|---|---|---|
| 📋 Ver todos los centros | Panel principal | Abre listado de ~405 DCTs con filtros |
| 📜 Histórico | Panel principal | Todos los eventos con filtros + paginación |
| 📊 Estadísticas | Panel principal | Gráficos y KPIs, botones de export |
| ⚙ Configuración | Panel principal | Catálogo comandos + envío |
| 🔍 Lanzar #016# | Resultado del buscador | Envía test al DCT seleccionado |
| Aplicar | Estadísticas | Refresca gráficos con los filtros |
| ⬇ Excel | Estadísticas | Descarga informe xlsx |
| 📄 PDF | Estadísticas | Descarga informe pdf |
| 🔍 Reintentar | Detalle de lote masivo | Relanza #016# a un DCT fallido |

---

## 12. Preguntas frecuentes

**¿Por qué hay DCTs que solo envían el RESTORED y no el LOST?**
Porque cuando se corta la luz en el centro, la batería interna del DCT no siempre aguanta lo suficiente para mandar el SMS, o la torre de móvil Movistar de la zona también se queda sin electricidad y no hay red para enviar. Es un comportamiento conocido y esperado.

**¿Y si recibo solo el LOST y nunca el RESTORED?**
Suele indicar que el DCT se ha quedado sin batería o que sigue sin luz cuando ya debería haber vuelto. Normalmente un técnico de mantenimiento visita el centro para comprobarlo. El KPI de cortes cuenta la incidencia igualmente aunque no llegue el RESTORED.

**¿Cuánto tarda el informe en Excel / PDF?**
Entre 5 y 30 segundos según el rango seleccionado (histórico completo tarda más). Si pasan más de 1 minuto sin respuesta, revisa con el equipo técnico — suele ser el convertidor de PDF atascado.

**¿Puedo enviar un SMS distinto a #016# a un DCT?**
Sí, desde **⚙ Configuración**. Están todos los comandos del catálogo soportado por el DD5241. Si falta alguno, hay que ampliar `lib/comandos.php` (pedir al equipo técnico).

**¿Los correos los recibo yo?**
Los correos automáticos de alerta se envían a `cgp.sergas@telefonica.com` (lista del CGP). Si no los ves, puede ser filtro de spam o que tu cuenta no esté en esa lista.

---

*Manual para operadores CGE SERGAS. Versión 1.0 — Abril 2026.*
