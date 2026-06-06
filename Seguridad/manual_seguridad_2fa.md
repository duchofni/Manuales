# BDU — Manual de Verificación en dos pasos (2FA)

| | |
|---|---|
| **Aplicación** | BDU (Base de Datos Unificada) |
| **Versión** | 2.1 |
| **Fecha** | Junio 2026 |
| **Para** | Operadores y administradores CGE SERGAS |

---

## Índice

1. [Qué es la verificación en dos pasos](#1-qué-es-la-verificación-en-dos-pasos)
2. [Configurar el 2FA la primera vez](#2-configurar-el-2fa-la-primera-vez)
3. [Acceder a partir de ahora](#3-acceder-a-partir-de-ahora)
4. [Mi seguridad: reconfigurar el 2FA](#4-mi-seguridad-reconfigurar-el-2fa)
5. [Para administradores: resetear el 2FA de un usuario](#5-para-administradores-resetear-el-2fa-de-un-usuario)
6. [Preguntas frecuentes](#6-preguntas-frecuentes)

---

## 1. Qué es la verificación en dos pasos

La verificación en dos pasos (2FA) añade un **segundo candado** al acceso a la BDU. Además de nuestro usuario y contraseña del dominio, necesitamos un **código de 6 dígitos** que genera una app en el móvil y que cambia cada 30 segundos.

Así, aunque alguien conozca o haya guardado nuestra contraseña, **no podrá entrar sin el código**. El 2FA es **obligatorio**: no podemos usar la BDU sin configurarlo.

Nos sirve cualquiera de estas apps (gratuitas): **Google Authenticator**, **Microsoft Authenticator**, **FreeOTP**, o también **Vaultwarden** y **KeePassXC** si ya las usamos.

---

## 2. Configurar el 2FA la primera vez

La primera vez que entramos tras activarse el 2FA, después de poner usuario y contraseña aparece la pantalla **"Configura tu verificación en dos pasos"**.

1. Abrimos nuestra app de autenticación en el móvil y elegimos **añadir una cuenta nueva**.
2. **Escaneamos el código QR** que muestra la pantalla. Si no podemos escanear (por ejemplo, para guardarlo en Vaultwarden o KeePass), copiamos la **clave manual** que aparece debajo del QR.
3. La app empieza a mostrar un **código de 6 dígitos** que cambia cada pocos segundos.
4. Escribimos ese código en el campo **"Código de 6 dígitos"** y pulsamos **Activar 2FA**.

Si el código es correcto, entramos directamente a la BDU. A partir de ese momento el 2FA queda activado para nuestro usuario.

> **Importante:** conviene guardar también la **clave manual** en un sitio seguro (Vaultwarden). Si perdemos el móvil, esa clave nos permite volver a añadir la cuenta en una app nueva.

---

## 3. Acceder a partir de ahora

Cada vez que iniciamos sesión:

1. Ponemos usuario y contraseña del dominio como siempre.
2. Aparece la pantalla **"Verificación en dos pasos"**.
3. Abrimos la app, miramos el **código de 6 dígitos** del momento y lo escribimos.
4. Pulsamos **Verificar** y entramos.

Si nos equivocamos de código varias veces, por seguridad la sesión se cancela y volvemos a la pantalla de usuario y contraseña.

---

## 4. Mi seguridad: reconfigurar el 2FA

Si cambiamos de móvil, podemos volver a configurar el 2FA nosotros mismos:

1. Pulsamos sobre **nuestro nombre** (👤) en la cabecera, arriba a la derecha.
2. En la pantalla **"Verificación en dos pasos"** pulsamos **Reconfigurar 2FA**.
3. Escaneamos el nuevo QR con la app y confirmamos con un código.

Al reconfigurarlo, el código anterior deja de ser válido.

---

## 5. Para administradores: resetear el 2FA de un usuario

Si un compañero ha **perdido el acceso a su app** (móvil perdido, app borrada) y no puede entrar, un administrador de la BDU puede resetear su 2FA. Solo pueden hacerlo los miembros del grupo **`admins_bdu`** del dominio.

1. Pulsamos el icono de **engranaje** (⚙️) de la cabecera para abrir el **Panel de administración**.
2. En la tarjeta **"Seguridad · 2FA"** vemos la lista de usuarios que tienen 2FA configurado.
3. Pulsamos **Resetear 2FA** en la fila del usuario afectado y confirmamos.

A partir de ese momento, ese usuario volverá a ver la pantalla de configuración en su próximo inicio de sesión y configurará el 2FA de nuevo con su móvil. Cada reseteo queda registrado.

---

## 6. Preguntas frecuentes

**He perdido el móvil y no puedo entrar.**
Pedimos a un administrador (grupo `admins_bdu`) que resetee nuestro 2FA (apartado 5). Después configuramos el 2FA de nuevo en el móvil nuevo.

**El código que pongo da siempre error.**
Casi siempre es por la **hora del móvil**. El código depende de la hora exacta: si el reloj del móvil está desajustado, los códigos no coinciden. Activamos la **hora automática** del móvil y probamos de nuevo. Se admite un pequeño desfase (±30 s).

**¿Necesito internet en el móvil para el código?**
No. La app genera el código sin conexión, solo con la hora.

**¿Puedo usar la misma cuenta en dos apps/dispositivos?**
Sí, si al configurar guardamos la **clave manual**, podemos añadirla en varias apps (por ejemplo, móvil + Vaultwarden) y todas generarán el mismo código.
