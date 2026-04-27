# Manual de Usuario: Módulo Grilloweb

| Campo       | Valor                              |
|-------------|------------------------------------|
| **Módulo**  | Mantenimiento > Grilloweb          |
| **Versión** | 1.5                                |
| **Fecha**   | Abril 2026                         |
| **Para**    | Operadores CGE SERGAS              |

---

## 1. Descripción general

El módulo Grilloweb permite hacer seguimiento de las **incidencias de Telefónica (INC)** a través del portal Grilloweb. Puedes suscribirte a incidencias para recibir actualizaciones automáticas, gestionar las INC activas y consultar su estado.

---

## 2. Pantalla principal

Al entrar en Grilloweb verás:

- **Barra superior** con los botones "Gestionar INC" y "+ Nueva INC".
- **INC disponibles**: incidencias activas del equipo a las que aún no estás suscrito.
- **Mis INC**: incidencias a las que ya estás suscrito.

[CAPTURA: Pantalla principal de Grilloweb mostrando las secciones de INC disponibles y Mis INC]

---

## 3. Suscribirse a una incidencia

### 3.1. Suscribirse a una INC nueva

1. Pulsa el botón **+ Nueva INC**.
2. Se desplegará un formulario con 3 campos:
   - **ID Incidencia**: el número de INC de Telefónica (ejemplo: INC-0032190991).
   - **Usuario Telefónica**: tu usuario de Telefónica (ejemplo: t123456).
   - **Contraseña Telefónica**: tu contraseña de Telefónica.
3. Pulsa **Suscribirse**.
4. El sistema verificará las credenciales contra Grilloweb.
5. Si todo es correcto, la INC aparecerá en la sección **Mis INC**.

[CAPTURA: Formulario de nueva suscripción con los campos ID Incidencia, Usuario y Contraseña]

> **Nota sobre seguridad:** Las credenciales solo se usan para obtener la cookie de sesión de Grilloweb. No se almacenan en la base de datos.

### 3.2. Suscribirse a una INC disponible

- Si en la sección **INC disponibles** hay incidencias que ya siguen otros compañeros, puedes suscribirte pulsando el botón **Suscribirse** de esa INC.
- No necesitas introducir credenciales de nuevo (ya se obtuvieron previamente).

---

## 4. Consultar el estado de una INC

En la sección **Mis INC**, cada tarjeta de incidencia muestra:

- **Estado** de la INC
- **Severidad**
- **Último log** o comentario registrado
- Información adicional: responsable, fecha prevista, etc.

El sistema hace **polling automático cada 5 minutos**: consulta el portal Grilloweb y actualiza la información sin que tengas que recargar la página.

---

## 5. Notificaciones por correo

Cuando el sistema detecta un cambio en una INC (cambio de estado, nueva actuación o nuevos comentarios), envía automáticamente un **correo de notificación** a cgp.sergas@telefonica.com.

---

## 6. Desuscribirse de una INC

1. En **Mis INC**, localiza la tarjeta de la INC.
2. Pulsa el botón **Desuscribirse**.
3. La INC desaparecerá de tu lista personal.
4. La INC sigue activa para otros operadores que estén suscritos.

---

## 7. Gestionar INC (eliminar seguimiento)

1. Pulsa el botón **Gestionar INC** en la barra superior.
2. Se desplegará un panel con la lista de todas las INC activas.
3. Pulsa **Eliminar** junto a la INC que quieras desactivar.

> **Importante:** Al eliminar una INC, esta desaparece de las listas de **todos los operadores**, no solo de la tuya. Los datos históricos se conservan en la base de datos.

[CAPTURA: Panel de gestión mostrando la lista de INC con el botón Eliminar junto a cada una]

---

## 8. Resumen del flujo habitual

1. Se abre una INC en Grilloweb → **suscribirse** desde la BDU.
2. El sistema hace **seguimiento automático** cada 5 minutos.
3. Si hay cambios, recibes **correo de notificación**.
4. Cuando la INC se resuelve → **desuscribirse** o **eliminar seguimiento**.

---

*Manual para operadores CGE SERGAS. Versión 1.5 — Abril 2026.*
