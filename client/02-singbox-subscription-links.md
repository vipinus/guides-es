# 02 · Cómo importar un enlace de suscripción (Hiddify, Clash, Shadowrocket)

> Versión web (más extensa): https://www.leotun.com/es/guides/singbox-subscription?utm_source=github&utm_content=client-02

El «enlace de suscripción» que te da un proveedor de líneas proxy no es más que una dirección HTTPS de la que el cliente descarga una configuración completa: servidor, puerto y credenciales van incluidos, así que no hay que escribir nada a mano. La página de Hiddify de LeoTun te da lo mismo, y directamente en tres formatos, de modo que Hiddify, Clash y Shadowrocket toman cada uno el suyo y no hay que convertir nada.

## Los tres botones de la ventana emergente

Inicia sesión en la web → página de Hiddify → haz clic en la bandera de una región. Aparece un código QR con tres botones debajo. Los botones se agrupan **por tipo de suscripción**, no por sistema operativo, así que el móvil y el ordenador muestran los mismos:

| Clientes que aparecen en el botón | Subtítulo | Qué se copia al hacer clic |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | Suscripción sing-box | En el móvil, el enlace de importación `sing-box://import-remote-profile?url=…`, que abre la app; en el ordenador, la URL de configuración `https://…` tal cual, para pegarla. La configuración ya incluye las reglas de enrutamiento y una regla que rechaza el IPv6, así que no hace falta envolverla en una «plantilla de suscripción» |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Suscripción Clash | Una URL de suscripción en formato Clash (YAML), para pegar en la lista de suscripciones / perfiles del cliente |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Enlace para compartir | Una sola línea `hysteria2://…`, que lleva solo el nodo, sin reglas de enrutamiento |

- Cuando los nombres no caben en una línea, se desplazan en bucle; es normal.
- **Al hacer clic en un botón, el código QR de arriba también cambia a ese tipo**, para que el cliente correspondiente lo pueda escanear. Al abrirse la ventana, el código QR es el de Hiddify / sing-box, y si otros clientes lo escanean directamente da «Invalid QR code» (código QR no válido): primero haz clic en el botón de tu cliente y luego escanea o pega.
- La ventana «Importar todas las regiones · selección automática» de la parte superior de la página solo tiene los dos primeros botones, sin enlace para compartir.

**Conversión de suscripciones**: webs de terceros que convierten un formato en otro. LeoTun te da los tres formatos directamente, así que **no hace falta convertir nada**; dar a una web de conversión un enlace que contiene tus credenciales equivale a entregarle tu cuenta a un tercero, así que no lo hagas.

## Familia Hiddify / sing-box: el primer botón

1. Instala Hiddify (Android: la página de descargas de la web o Google Play; iOS: App Store; la app de escritorio cubre Windows / macOS / Linux). El núcleo sing-box va incluido.
2. Haz clic en la bandera de una región y aparecerá el código QR.
3. Móvil: toca el primer botón y pásate a Hiddify, que te ofrecerá añadirlo desde el portapapeles; o usa «Scan QR code» (escanear código QR) en Hiddify desde otro dispositivo. Ordenador: haz clic en el mismo botón, que copia una dirección https://, y luego en Hiddify «+» → «Add from clipboard» (añadir desde el portapapeles), y guarda.
4. Toca conectar y permite el permiso de VPN la primera vez. Para añadir otra región, haz clic en otra bandera; cada región es un perfil independiente.

## Familia Clash: el segundo botón

Con Clash Meta (mihomo), Clash Verge, FlClash, Stash y similares, haz clic en el botón «Suscripción Clash» y pega la URL copiada en la lista de suscripciones / perfiles del cliente. No hace falta ningún conversor de suscripciones.

**Los clientes de la familia Clash no deben usar el enlace para compartir**: no pueden importar una sola línea `hysteria2://` como perfil.

## Otros clientes: el tercer botón

Haz clic en el botón «Enlace para compartir» y luego usa «Import from clipboard» (importar desde el portapapeles) en NekoBox / Shadowrocket / v2rayN / v2rayNG y similares, o escanea el código QR de arriba después de hacer clic en el botón. Un enlace para compartir no lleva reglas, así que tendrás que configurar tú el enrutamiento y el IPv6: si estás en el extranjero y quieres ver contenido de China, envía los dominios chinos por el nodo y desactiva el IPv6.

Los clientes que aparecen en el botón después de v2rayN admiten todos hysteria2, pero el enlace para compartir usa un formato ampliado de hysteria2 que algunos clientes no saben leer; si la importación falla o no conecta, cambia a Hiddify.

## Clientes que no sirven

| Cliente | Por qué |
|---|---|
| Surge | Admite hysteria2, pero solo lee su propio formato de configuración, así que ninguno de los tres tipos encaja |
| Quantumult X | No admite este tipo de línea |
| El Clash original, Clash for Windows | Al núcleo le falta hysteria2; usa en su lugar un cliente con núcleo mihomo |

## ¿Caduca la suscripción?

- **No caduca con el tiempo.** El token de la URL de suscripción está ligado a tu cuenta y sigue funcionando mientras la cuenta esté vigente; renovar o cambiar de plan no obliga a volver a importar.
- **Cambiar la contraseña invalida al instante la URL antigua.** Así se revoca el acceso si pierdes un móvil o se filtra un enlace; tras cambiarla, vuelve a escanear el código.
- **Cuando la cuenta caduca**, la URL devuelve 401; en cuanto renuevas, no hace falta sustituir el perfil que ya tienes.
- **Los perfiles importados antes de septiembre de 2026** no tienen la regla que rechaza el IPv6; bórralos e impórtalos de nuevo.

Si ya lo importaste pero no conecta, consulta [Solución de problemas 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Preguntas frecuentes

**¿Qué diferencia hay entre una suscripción de Hiddify y una de Clash?** El formato es distinto (JSON frente a YAML) y cada cliente no reconoce la suscripción del otro, pero los nodos en sí funcionan con ambos. LeoTun te da las dos directamente: los clientes de la familia Clash hacen clic en el botón «Suscripción Clash» y no deben usar el enlace para compartir.

**¿Un perfil puede contener todas las regiones?** Al importar desde una bandera obtienes un perfil por región, y cambias entre ellos en la lista de perfiles del cliente; así, si cambia la dirección de una región, solo se ve afectada esa región. Para importar de una vez todas las regiones fuera de China y dejar que el cliente elija automáticamente, haz clic en «Importar todas las regiones · selección automática» en la parte superior de la página (solo tiene los botones de suscripción sing-box y suscripción Clash).

**¿Puedo enviar el código QR a mi familia?** El código QR contiene las credenciales de tu cuenta; quien lo reciba tendrá tu cuenta. Compartirlo con la familia está permitido (dispositivos simultáneos según el plan: Individual 2, Familiar 4, Empresa 8), pero no lo publiques en ningún sitio público; si se filtra, cambia la contraseña y dejará de funcionar.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
