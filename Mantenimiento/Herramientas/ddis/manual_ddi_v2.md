# Manual de Usuario: Módulo DDIs GDIA

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > DDIs GDIA          |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo DDIs permite gestionar los **DDI (Direct Dial-In)** de voz para GDIA. Puedes buscar un centro, ver sus DDIs disponibles, marcar un DDI como usado (queda bloqueado durante 60 días) y consultar el historial de usos.

---

## 2. Buscar un centro

1. Escribe el **nombre del centro** en el campo de búsqueda.
2. Aparecerán sugerencias mientras escribes.
3. Selecciona el centro deseado.
4. Pulsa **Ver DDIs**.

[CAPTURA: Campo de búsqueda de centro con desplegable de sugerencias]

---

## 3. Ver DDIs del centro

Tras seleccionar un centro, se mostrará:

- **Nombre del centro** y estadísticas (total de DDIs, disponibles, bloqueados).
- **Tabla de DDIs** con las siguientes columnas:

| Columna        | Descripción                                           |
|----------------|-------------------------------------------------------|
| Número DDI     | El número de teléfono DDI                             |
| Estado         | Disponible o Bloqueado                                |
| Fecha de uso   | Fecha en que se marcó como usado por última vez       |
| Operador       | Quién lo usó                                          |
| Acción         | Botón para marcar como usado (solo si está disponible)|

[CAPTURA: Tabla de DDIs de un centro mostrando DDIs disponibles y bloqueados con sus datos]

### 3.1. Filtrar DDIs

- Usa el **campo de filtro** encima de la tabla para buscar por número DDI o administrativo.
- El filtrado es en tiempo real mientras escribes.

### 3.2. Paginación

- Si hay muchos DDIs, la tabla se pagina automáticamente.
- Usa los controles de página en la parte inferior.

---

## 4. Asignar (marcar) un DDI

1. Localiza el DDI disponible que quieras usar.
2. Pulsa el botón **Marcar** en la columna de acción.
3. El DDI quedará **bloqueado durante 60 días**.
4. Se registrará tu usuario y la fecha actual.
5. La tabla se actualizará automáticamente.

> **Nota:** Los DDIs bloqueados no se pueden volver a marcar hasta que pasen los 60 días.

[CAPTURA: DDI recién marcado como usado mostrando el estado Bloqueado, la fecha y el operador]

---

## 5. Historial de usos

Debajo de la tabla de DDIs se muestra el **historial** de usos del centro:

| Columna          | Descripción                                  |
|------------------|----------------------------------------------|
| Número DDI       | El DDI que se usó                            |
| Operador         | Quién lo marcó                               |
| Fecha de uso     | Cuándo se marcó                              |
| Estado bloqueo   | Si aún está dentro del período de 60 días    |

---

## 6. Flujo habitual

1. Se necesita un DDI para abrir un GDIA.
2. **Buscar** el centro afectado.
3. **Ver DDIs** disponibles.
4. **Marcar** el DDI elegido.
5. Usar ese número DDI en el GDIA.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
