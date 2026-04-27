# Manual de Usuario: Módulo Stock

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Stock                              |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo Stock permite gestionar el inventario de material de red del CGE. Tiene dos vistas: **Stock EECC** (equipos en empresas colaboradoras por delegación) y **Stock Almacén**. Las cantidades son editables directamente en la tabla y los cambios se guardan automáticamente.

---

## 2. Acceder al módulo

Al entrar en Stock verás dos botones de navegación:

- **Stock EECC**: inventario de equipos distribuidos por delegación.
- **Stock Almacén**: inventario del almacén central.

Pulsa el botón de la vista que necesites.

---

## 3. Stock EECC

### 3.1. Ver la tabla de stock

La tabla muestra todos los equipos con las siguientes columnas:

| Columna       | Descripción                                | Editable |
|---------------|--------------------------------------------|----------|
| Fabricante    | Fabricante del equipo                      | No       |
| LORCET        | Código LORCET del equipo                   | No       |
| Descripción   | Descripción del equipo                     | No       |
| Santiago      | Cantidad en la delegación de Santiago      | **Sí**   |
| Coruña        | Cantidad en la delegación de Coruña        | **Sí**   |
| Lugo          | Cantidad en la delegación de Lugo          | **Sí**   |
| Ourense       | Cantidad en la delegación de Ourense       | **Sí**   |
| Pontevedra    | Cantidad en la delegación de Pontevedra    | **Sí**   |

![Tabla de Stock EECC mostrando las columnas de fabricante, descripción y las delegaciones con campos editables](./imagenes/captura-01-tabla-de-stock-eecc-mostrando-las-column.png)

### 3.2. Buscar equipos

1. Usa el **campo de búsqueda** en la barra superior.
2. Escribe cualquier texto (fabricante, descripción, LORCET, etc.).
3. La tabla se filtra en **tiempo real** mientras escribes, mostrando solo las filas que coinciden.

![Campo de búsqueda con un texto escrito y la tabla filtrada mostrando solo las filas que coinciden](./imagenes/captura-02-campo-de-busqueda-con-un-texto-escrito-y.png)

### 3.3. Modificar cantidades

1. Localiza el equipo en la tabla.
2. Pulsa sobre el **campo numérico** de la delegación que quieras modificar.
3. Escribe el **nuevo valor**.
4. Pulsa fuera del campo o pasa al siguiente (Tab).
5. El cambio se **guarda automáticamente** en la base de datos.

> **Nota:** No hay botón de guardar. Los cambios se envían automáticamente al modificar el valor.

### 3.4. Exportar stock

En la barra superior hay botones para exportar la tabla:

| Formato   | Descripción                                              |
|-----------|----------------------------------------------------------|
| **CSV**   | Fichero de texto separado por comas (abrir con Excel)    |
| **Excel** | Fichero .xlsx nativo de Excel                            |
| **PDF**   | Documento PDF en formato apaisado                        |

1. Pulsa el botón del formato deseado.
2. Se descargará automáticamente el fichero con todos los datos de la tabla.

![Botones de exportación CSV, Excel y PDF en la barra superior](./imagenes/captura-03-botones-de-exportacion-csv-excel-y-pdf-e.png)

---

## 4. Stock Almacén

La vista de Stock Almacén funciona de forma similar a Stock EECC:

- Muestra los equipos del almacén central.
- Los campos **Cantidad** y **Stock Mínimo** son editables inline.
- Los cambios se guardan automáticamente.

> **Nota:** Esta vista puede estar en desarrollo. Si no aparece contenido, consulta con el equipo técnico.

---

## 5. Consejos de uso

- **Para actualizar stock rápidamente:** usa Tab para saltar de un campo numérico al siguiente sin necesidad de usar el ratón.
- **Para buscar un equipo concreto:** escribe parte del nombre del fabricante o la descripción en el buscador.
- **Para tener una copia:** exporta a Excel antes de hacer cambios importantes.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
