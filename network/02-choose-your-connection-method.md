# 02 · Qué método de conexión conviene en cada situación

Una cuenta de LeoTun tiene seis métodos de conexión: red Privada (Tailscale), Cisco (AnyConnect), OpenVPN, Proxy Web, Hiddify y Router. Cada método tiene las situaciones en las que mejor encaja, y este artículo responde por situaciones: primero según el dispositivo que usas, luego según la red en la que estás y, por último, según lo que quieres hacer. Cada situación trae una recomendación, el motivo y una alternativa. Recuerda una cosa: seis métodos con una sola cuenta; siempre hay uno que encaja con tu red.

## Según el dispositivo: con qué te conectas

- Un solo móvil, viajes de trabajo y turismo: Cisco o Hiddify. Cisco conecta en cuanto introduces la dirección en la app oficial y es el más estable; Hiddify se importa escaneando un código QR y va más rápido cuando hay mucha pérdida de paquetes. Alternativa: red Privada.
- Tu propio ordenador (Windows, Mac): Hiddify o red Privada. Hiddify es rápido y trae un interruptor de enrutamiento dividido integrado; la red Privada se queda en línea tras iniciar sesión una sola vez. Alternativa: Cisco.
- Un ordenador de la empresa, sin derechos de administrador: Proxy Web. Solo instalas una extensión del navegador, no necesita derechos de administrador y no toca la configuración de red de la empresa.
- iPhone, dispositivos antiguos: Cisco. Conecta con la VPN integrada en el sistema o con el cliente oficial, no hace falta importar ninguna configuración y es el más compatible.
- NAS (Synology, QNAP), servidores Linux: OpenVPN. Importas un archivo .ovpn y conecta automáticamente al arrancar; la mayoría de estos dispositivos traen el cliente integrado.
- Teles, decodificadores, consolas, el móvil de un familiar mayor: Router. Todo lo que se conecta al wifi pasa por la línea, y no hay que instalar nada en el dispositivo. Los tres planes pueden usarlo.
- Muchos dispositivos de toda la familia o de una oficina: Router, se configura una vez y vale para todos; si además quieres acceder desde fuera al NAS de casa, añade la red Privada.

## Según la red: en qué red estás

- Redes de residencias o de campus, redes de empresa que restringen UDP: Cisco. Funciona sobre TLS, igual que al abrir una web HTTPS, y es el más estable en redes restringidas; Hiddify, la red Privada y OpenVPN funcionan sobre UDP e irán lentos o se cortarán.
- Banda ancha que se corta a menudo, wifi con poca señal: Proxy Web. Funciona petición a petición, sin una conexión permanente, así que, por diseño, no hay conexión que se pueda cortar.
- Banda ancha de urbanizaciones antiguas, datos móviles, mucha pérdida de paquetes: Hiddify. Su protocolo está diseñado para resistir la pérdida de paquetes y da la mejor velocidad en ese tipo de redes.
- El ordenador ya está conectado a la VPN de la empresa: Proxy Web. Dos VPN de todo el equipo funcionando a la vez se pelean por la configuración de red; el proxy web solo se encarga del navegador, así que no se estorban.
- China Mobile, Great Wall y otras bandas anchas, o enlaces internacionales que siempre van inestables: cualquier método, eligiendo un punto de entrada de la región de China. Suele ser la opción más estable en estas redes.

## Según el objetivo: qué quieres hacer

- Estás en el extranjero y quieres ver vídeo chino: cualquier método para todo el dispositivo (Cisco, Hiddify, red Privada, OpenVPN, Router) con la región de China seleccionada; para la tele de casa, Router. No uses el proxy web para vídeo: no llega al canal de red propio del dispositivo, así que la web de vídeo puede seguir viéndote en el extranjero.
- Juegos, llamadas de voz y videollamadas: Hiddify, red Privada o Router, eligiendo la región con menor latencia. El proxy web solo se encarga del navegador; los juegos y las apps de llamadas no pasan por él.
- Trabajo de oficina y búsquedas, solo con el navegador: el proxy web es lo más cómodo; si necesitas conectarte a sistemas internos de la empresa, confirma primero si la VPN de la empresa puede funcionar junto con la nuestra y, si no puede, usa el proxy web.
- Servidores, scripts, línea de comandos: OpenVPN; en un escritorio Linux también puedes usar la red Privada o Hiddify.
- Acceder desde fuera al NAS o a las cámaras de casa: red Privada. Los dispositivos de la misma cuenta se ven entre sí, sin necesidad de abrir puertos en el router.

## Resumen rápido de los seis métodos: ideal para / no apto para

- Red Privada (Tailscale): ideal para varios dispositivos, iniciar sesión una vez y olvidarse, acceder desde fuera a los dispositivos de casa. No apta para redes que restringen UDP (solo puede apoyarse en los relés de Tailscale, que son lentos) ni para funcionar junto con otra VPN.
- Cisco AnyConnect: ideal para redes restringidas, ordenadores de empresa, iPhone y dispositivos antiguos; la mejor compatibilidad. No apto para quien está en China y no quiere que todo el tráfico pase por la línea (hay que ejecutar aparte un script de enrutamiento dividido).
- OpenVPN: ideal para NAS, servidores Linux y routers OpenWrt; importas un archivo y conecta automáticamente al arrancar. No apto para el uso diario en móviles y ordenadores, donde es menos cómodo que Cisco y Hiddify, ni para redes que restringen UDP.
- Proxy Web: ideal cuando no tienes derechos de administrador, ya estás conectado a la VPN de la empresa o la banda ancha se corta a menudo. No apto para apps de vídeo, juegos ni llamadas; solo se encarga del navegador.
- Hiddify: ideal para quien quiere velocidad y para redes con mucha pérdida de paquetes; se importa escaneando un código QR, la misma app en cinco plataformas, enrutamiento dividido integrado. No apto para redes que restringen UDP.
- Router: ideal para toda una familia, una oficina o dispositivos que no pueden instalar un cliente; el firmware trae el enrutamiento dividido integrado y se actualiza solo. No apto para quien solo tiene un dispositivo y sale a menudo (fuera de casa sigue necesitando un cliente).

## Elegir región según tu banda ancha

Un mismo método puede variar varias veces de velocidad de una región a otra; la razón está en la línea de salida de tu operador hacia esa región, no en el servidor. China Unicom en el norte: prueba primero Japón y Corea. China Telecom en el sur: prueba primero el Sudeste Asiático (Singapur, Malasia, Tailandia, Filipinas, Indonesia) o Australia. Otras bandas anchas (China Mobile, Great Wall y similares): prueba primero el punto de entrada de la región de China.

El semáforo rojo, amarillo y verde de la lista de regiones muestra la carga de cada región en directo; entre varias entradas de Japón, elige la que tenga el semáforo en verde. De 20:00 a 23:00 es la hora punta en todo el país; en esa franja elige una región con el semáforo en verde o cambia de método de conexión. Si sigue lento, la causa habitual es la banda ancha local (banda ancha compartida de urbanización, o un operador y una región que no casan).

## Enrutamiento dividido: directo dentro de China, por la línea para el extranjero

Solo quien está en China continental necesita el enrutamiento dividido; fuera de China se usa el modo global, y activar el enrutamiento dividido haría que algunas webs dieran un rodeo. En Hiddify cambias a «Auto split routing» (enrutamiento dividido automático) en el cliente; en el proxy web cambias a «Split routing» (enrutamiento dividido) en la extensión; el router hace el enrutamiento dividido para todos los dispositivos de la red, y su firmware lo trae activado por defecto; con Cisco y OpenVPN todo el tráfico pasa por la línea al conectar, y en la sección «Cisco» está disponible el script de enrutamiento dividido; la red Privada envía todo el dispositivo por la línea.

Si una web no abre con el enrutamiento dividido, cambia primero temporalmente a «Global» para comprobarlo: si con Global abre, es que no está en la lista; si tampoco abre con Global, el problema es de la propia web.

## Cómo cambiar cuando no funciona

1. Cambia primero de región. Si otra región conecta, es que ese servidor no está accesible de forma temporal.
2. Luego cambia de red. Si la banda ancha no funciona, pasa a datos móviles, y al revés; las interferencias en distintos operadores no ocurren a la vez.
3. Luego cambia de método. Si los que funcionan sobre UDP (Hiddify, red Privada, OpenVPN) no van, cambia a Cisco, que funciona sobre TLS; si los métodos para todo el dispositivo se cortan una y otra vez, cambia al proxy web. Los bloqueos de los distintos protocolos son independientes entre sí.
4. Si sigue sin funcionar, consulta la guía de solución de problemas o pregunta en el grupo de soporte, indicando el método de conexión, la región, el texto exacto del error y la hora.

## Preguntas frecuentes

**¿Cuál de los seis métodos es el más rápido?** En redes con mucha pérdida de paquetes, Hiddify; en redes limpias hay poca diferencia, y el cuello de botella es la región y la hora del día, no el método.

**¿Cuál para juegos y llamadas de voz?** Hiddify, red Privada o Router, eligiendo la región con menor latencia. El proxy web solo se encarga del navegador; los juegos y las apps de llamadas no pasan por él.

**¿Se pueden usar los seis métodos a la vez?** En dispositivos distintos, sí; todos los métodos de la misma cuenta comparten el cupo de dispositivos en línea a la vez (Individual 2 dispositivos, Familiar 4 dispositivos, Empresa 8 dispositivos). No ejecutes dos métodos para todo el dispositivo a la vez en el mismo dispositivo (por ejemplo, red Privada y Cisco), porque se pelearán por la configuración de red.

**¿Tengo que elegir entre router y cliente?** No. Usa el router en casa y activa el cliente en el móvil cuando salgas; cada uno cuenta como un dispositivo.

**¿Cuál para Linux?** La red Privada, OpenVPN e Hiddify tienen cliente para Linux; Cisco en Linux usa el OpenConnect de código abierto; OpenVPN en Linux pide el usuario y la contraseña en la primera conexión. Para servidores y NAS, OpenVPN es lo más cómodo.

## Para seguir leyendo

- [En qué nos diferenciamos de otras VPN](https://www.leotun.com/es/guides/why-us?utm_source=github&utm_content=network-02)
- [Qué es la red Privada (Tailscale)](https://www.leotun.com/es/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [Cómo usar OpenVPN y cuándo elegirlo](https://www.leotun.com/es/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Qué es el proxy web y cuándo usarlo](https://www.leotun.com/es/guides/web-proxy?utm_source=github&utm_content=network-02)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/choose-connection?utm_source=github&utm_content=network-02

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=network-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=network-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
