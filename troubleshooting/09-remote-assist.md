# 09 · Que el soporte revise a distancia tu ordenador y tu router

Hay problemas que no quedan claros ni después de una docena de capturas de ida y vuelta en el grupo, y que el soporte localiza en dos minutos mirando directamente la pantalla. Este artículo explica cuándo merece la pena pedir asistencia remota, qué programa usar en el ordenador, cómo importar la configuración del servidor de este sitio, cómo pasar los datos de conexión al soporte de forma segura, qué controlas tú durante la sesión, cómo retirar el acceso después y qué tienes que hacer con un router que lleva el firmware de este sitio.

## Cuándo merece la pena pedir asistencia remota

- Ya has seguido una vez la [01 · Lista de comprobación cuando no conecta, va lento o se corta](01-cannot-connect-slow-drops.md) y has preguntado indicando el método de conexión, la región, el texto exacto del error o una captura y la hora en que ocurrió el problema, y aun así no se resuelve.
- No eres capaz de describir los pasos tú mismo: el ajuste está muy escondido, no entiendes el idioma del sistema o el error aparece y desaparece demasiado rápido para capturarlo.
- Estás ayudando a un familiar con su ordenador, no estás a su lado y por teléfono no hay manera de explicarlo.

En el siguiente caso **no uses la asistencia remota**; comunícate por escrito en el grupo:

- Ordenadores gestionados de forma centralizada por una empresa. Las directivas de grupo suelen prohibir ejecutar este tipo de programas, y puede ir contra las normas de la empresa.

## Qué programa usar: RustDesk

La web recomienda [RustDesk](https://rustdesk.com): es de código abierto (AGPL-3.0), así que cualquiera puede auditar el código, y tanto el inicio como el final de una sesión los decides tú con un clic. Funciona en Windows, macOS, Linux, Android e iOS (un iPhone / iPad solo puede controlar otros equipos; no se puede controlar).

Descárgalo desde la [página de contacto](https://www.leotun.com/es/contact#downloads), en «Centro de descargas» → «Asistencia remota», o desde la web oficial rustdesk.com. No uses webs de descarga de terceros que salgan en los buscadores. Los dos lados de la sesión tienen que instalarlo.

## Qué autorizar después de instalarlo

| Sistema | Qué hacer |
|---|---|
| macOS | En «Ajustes del Sistema → Privacidad y seguridad», marca RustDesk tanto en «Grabación de pantalla» como en «Accesibilidad», y luego ciérralo del todo y vuelve a abrirlo. Si solo concedes uno, pasa que «se ve pero no se puede controlar» o la pantalla sale completamente negra. Si dice que «está dañado», consulta la [06](06-antivirus-false-positive.md) |
| Android | Cuando te vayan a asistir, toca «Start service» (iniciar servicio) en RustDesk y permite la grabación de pantalla; para que el soporte pueda tocar en tu pantalla, activa también RustDesk en la «Accesibilidad» del sistema |
| Windows / Linux | Suele funcionar nada más instalarlo |

## Conectar con nuestro propio servidor

La asistencia remota pasa por el servidor de RustDesk propio de este sitio, que también conecta de forma fiable desde China. **Los dos lados de la sesión tienen que importarlo una vez**; los dos extremos solo se encuentran si usan el mismo servidor:

1. Inicia sesión antes en la web y luego, en la [página de contacto](https://www.leotun.com/es/contact#downloads), ve a «Centro de descargas» → «Asistencia remota» → «Conectar con nuestro servidor» y haz clic en «Copiar».
2. En el ordenador, abre en RustDesk «Settings → Network» (ajustes → red), haz clic primero en «Unlock network settings» (desbloquear ajustes de red) y luego en «ID/Relay server» (servidor de ID/relé); en el móvil es «Settings → ID/Relay server».
3. En la ventana que aparece, haz clic en el icono del portapapeles arriba a la derecha (en el móvil, toca «Import», importar). La configuración se rellena automáticamente; haz clic en «OK».

**No pegues la configuración en los campos de texto**; eso provoca el error «failed to lookup address». Esta configuración es solo para cuentas de este sitio. No la reenvíes.

## Pasar el ID y la contraseña de un solo uso al soporte

Abre RustDesk y la pantalla principal muestra el ID de este equipo y una contraseña de un solo uso. Antes de pasarlos, confirma tres cosas:

1. **Lo pediste tú primero.** Describiste el problema en un grupo oficial de los que aparecen en la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-09), y el soporte decidió que hacía falta asistencia remota antes de pasar al siguiente paso. Nuestro equipo de soporte no se dirigirá a ti por iniciativa propia, ni te pedirá que instales software remoto ni un código de conexión; venga quien venga a pedírtelo, verifícalo antes en el grupo oficial.
2. **Envíalos solo por los canales oficiales de soporte**: los contactos de soporte humano que aparecen en la página de contacto. Cualquier chat privado fuera de los grupos que diga ser «soporte de LeoTun» no somos nosotros.
3. **No los publiques en el grupo.** Un grupo es un sitio que ve mucha gente; un ID más una contraseña es como dejar la llave de tu ordenador puesta en la puerta.

## Durante la sesión

- Durante toda la sesión ves en la pantalla lo que se está haciendo, y puedes desconectar en la ventana de RustDesk en cualquier momento.
- Si alguien te pide que minimices la ventana, que te alejes del ordenador o que abras la banca en línea o apps de pago, **desconecta inmediatamente**.
- Cuando haya que introducir la contraseña de tu cuenta, escríbela tú; no se la dictes al soporte.

## Retirar el acceso después

1. Haz clic en desconectar en la ventana de RustDesk y confirma que el otro lado se ha desconectado.
2. Renueva la contraseña de un solo uso para que la que acabas de enviar deje de valer.
3. Cierra RustDesk. Si ya no lo necesitas, puedes desinstalarlo sin más y volver a descargarlo la próxima vez.

## Routers: qué tienes que hacer

En un router con el firmware de este sitio no hace falta instalar ningún programa remoto ni en el router ni en el ordenador, ni enviar al soporte la contraseña de administración del router. Lo único que tienes que hacer es:

- Mantener el router encendido con el cable de red conectado y la cuenta con la sesión iniciada en el router.
- Decirle al soporte, en el grupo oficial, tu cuenta, el modelo de router y los síntomas; el soporte se encarga del resto.
- No desenchufarlo y reiniciarlo una y otra vez mientras están trabajando en él, salvo que el soporte te lo pida.

## Preguntas frecuentes

**¿El soporte me escribirá en privado por su cuenta para decirme que instale software remoto?** No. Siempre que alguien se dirija a ti sin que lo hayas pedido, verifica antes su identidad en el grupo oficial.

**¿Sale «failed to lookup address» al importar?** Lo más probable es que la configuración se pegara en los campos de texto. Vacía esos campos, vuelve a la ventana «ID/Relay server» e importa haciendo clic en el icono del portapapeles arriba a la derecha.

**¿Conectado en macOS pero la pantalla sale negra, o se ve pero no se puede controlar?** Faltan permisos. Marca tanto «Grabación de pantalla» como «Accesibilidad», y luego cierra del todo y vuelve a abrir.

**¿Qué más tengo que hacer cuando termina la sesión?** Desconectar, renovar la contraseña de un solo uso y cerrar el programa. Con estos tres pasos, el otro lado ya no puede volver a conectarse.

## Para seguir leyendo

- [Cómo usar la asistencia remota de RustDesk (guía de la web)](https://www.leotun.com/es/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Qué hacer cuando tu Mac dice que la app «está dañada»](https://www.leotun.com/es/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [Página de contacto: grupos de soporte, soporte humano y correo](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · Cómo contactar con nosotros y no perder el contacto](05-how-to-reach-us.md)
- [01 · Lista de comprobación cuando no conecta, va lento o se corta](01-cannot-connect-slow-drops.md)

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-09) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-09) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
