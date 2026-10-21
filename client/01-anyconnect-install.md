# 01 · Cisco AnyConnect: instalar, conectar y actualizar en todas las plataformas

> Versión web (más extensa): https://www.leotun.com/es/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect es el cliente VPN empresarial de Cisco. Hoy su nombre oficial es **Cisco Secure Client**, y funciona igual. No necesitas ningún archivo de certificado ni importar un perfil: introduces la dirección, tu cuenta y tu contraseña, y ya puedes conectarte. Si quieres saber si funciona en China y a qué cambiar cuando no conecta, consulta [Acceder a servicios del extranjero desde China, guía 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) (en chino).

## Instalación

| Plataforma | Qué instalar | Dónde conseguirlo |
|---|---|---|
| Windows 10 o posterior | Cisco Secure Client 5.x | [La página de Cisco en la web](https://www.leotun.com/es/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (la última versión compatible; ya no se actualiza) | Igual que arriba |
| macOS | Cisco Secure Client 5.x | Igual que arriba |
| iOS | Cisco Secure Client | App Store; si la tienda no lo muestra, instala OpenConnect, de código abierto, que usa el mismo protocolo |
| Android | Cisco Secure Client | Google Play, o el APK de la página de la web |
| Linux | El instalador de la página de la web, u openconnect desde los repositorios de tu distribución | Igual que arriba |

En Windows también existe OpenConnect-GUI, de código abierto; la misma cuenta funciona con él.

## Conectar en cuatro pasos

1. Abre el cliente y escribe la dirección del servidor en el campo de dirección. Si eres usuario de LeoTun, **haz clic en la bandera de una región** en la web para copiar su dirección.
2. Introduce tu cuenta (el correo con el que te registraste) y tu contraseña.
3. Cuando veas «Connected» (conectado), abre una web que muestre tu IP para confirmar que la salida está en la región que elegiste.
4. Para cambiar de región, usa otra dirección. El cliente recuerda las direcciones que ya usaste, así que la próxima vez puedes elegirla en la lista desplegable.

## Actualizar

No hace falta desinstalar antes: instala la nueva versión encima de la antigua y se conservan las direcciones guardadas. En el móvil, actualiza desde la tienda de apps. Después de una actualización importante del sistema operativo, actualiza primero el cliente y solo entonces ponte a investigar problemas de conexión.

## Mensajes habituales

| Mensaje | Qué significa |
|---|---|
| Login failed (error de inicio de sesión) | Cuenta o contraseña incorrectas, o la cuenta ha caducado |
| Untrusted server certificate (certificado de servidor no fiable) | Lo más probable es que el reloj del sistema esté mal o que la red actual intercepte las conexiones cifradas; prueba con otra red |
| Connection attempt has failed (falló el intento de conexión) | Esa dirección no está accesible por ahora; cambia de región |

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-01) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-01) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
