# 06 · Desbloquear webs de vídeo chinas desde el extranjero con un router

## Por qué un router en lugar de instalar un cliente en cada dispositivo

- Las teles, los decodificadores, los proyectores y las consolas no pueden instalar un cliente, así que el router es la única opción.
- Con mucha gente en casa, configurar cada dispositivo de cada persona no es realista; configura el router una vez y funciona en cuanto un dispositivo se conecta al wifi.
- El enrutamiento dividido se hace en el router, así que las webs y los dispositivos locales siguen conectando directamente; solo los dominios de vídeo chinos pasan por la línea hacia China, y la velocidad no se resiente.

## Qué necesitas

| Elemento | Notas |
|---|---|
| Un router compatible | Uno ya preparado funciona nada más sacarlo de la caja; si instalas el firmware tú mismo, consulta [Cómo instalar el firmware](02-flash-firmware-yourself.md) |
| Una cuenta | Los planes Individual, Familiar y Empresa admiten la función de router. Tras registrarte, pide primero la prueba gratuita para comprobar todo el proceso: una cuenta nueva está en el plan Individual, con 4 horas de prueba |
| Una red de entrada | El módem o router que ya tienes en casa; el router nuevo va detrás |

## Listo en cinco pasos

1. Conecta el puerto WAN del router nuevo a la red de entrada, enchúfalo a la corriente y espera un minuto.
2. Conecta el móvil al wifi del router nuevo, abre la dirección de administración `http://192.168.11.1` e inicia sesión con tu cuenta.
3. Elige **Split routing** (enrutamiento dividido) como modo. Los dominios de vídeo chinos están en la lista y pasarán automáticamente por la línea hacia China.
4. Cambia la tele y el decodificador a este wifi, o conéctalos por cable a un puerto LAN del router nuevo.
5. Abre iQIYI, Tencent Video o Yangshipin (la plataforma de la CCTV); si se reproduce con normalidad, ya está.

## La lista es pública

Los dominios de vídeo de la lista de enrutamiento dividido se mantienen en un repositorio público: <https://github.com/vipinus/openwrt-2026-video-domains>. Si una plataforma no se reproduce, puedes comprobar si su dominio está en la lista y, si no está, proponerlo.

## Calidad de imagen y ancho de banda

1080p necesita 5 Mbps estables, y 4K, 25 Mbps o más. Si a la hora punta de la noche la reproducción da tirones, elige una región con el semáforo en verde; si sigue dando tirones, la causa habitual es la banda ancha local. Como región de entrada, elige una que esté cerca de ti y tenga buena ruta hacia China continental; prueba un par y guíate por si la reproducción da tirones o no.

## Preguntas frecuentes

- **En el móvil se reproduce pero en la tele no**: la tele sigue conectada al wifi antiguo, o la app de la tele es la edición internacional.
- **Unas plataformas se reproducen y otras no**: el dominio de esa plataforma no está en la lista de enrutamiento dividido. Cambia temporalmente a «Global» para comprobarlo y luego proponlo en el repositorio de la lista.
- **Toda la casa va más lenta con un router antiguo**: el procesador no da abasto con el tráfico cifrado; cambia a un modelo con más rendimiento, consulta [Primeros pasos con un router ya preparado](01-plug-and-play-router.md).

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-06) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-06) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
