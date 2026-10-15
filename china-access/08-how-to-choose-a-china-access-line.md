# 08 · Cómo elegir una línea hacia China: de dónde sale la IP china y en qué fallan las gratuitas

> Versión web (más extensa): https://www.leotun.com/es/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Una línea hacia China hace una sola cosa: que las peticiones que envías desde el extranjero lleguen a Tencent Video, NetEase Cloud Music o tu banco en línea chino desde una IP de **China continental**. Así que fíjate primero en dos puntos: si la salida es de verdad una IP de China continental y si hay tráfico del dispositivo que se la salta. La velocidad, el precio y el cliente vienen después.

## De dónde sale la IP china

El proveedor tiene que tener sus propios servidores dentro de China continental. Los proveedores de nube chinos exigen registro con nombre real para poner en marcha una máquina y cobran el ancho de banda por uso, así que el coste es muy superior al de las máquinas en el extranjero. Por eso casi todos los servicios legítimos hacia China son de pago, y por eso el número de salidas en China es limitado.

Un sustituto habitual es hacer pasar máquinas de Hong Kong, Taiwán o Japón por «líneas hacia China». Esas direcciones sirven para algunas secciones de Bilibili de Hong Kong, Macao y Taiwán, pero Tencent Video, iQIYI y Youku siguen mostrando la restricción por derechos de autor, y la banca en línea y 12306 también te tratan como si estuvieras en el extranjero. **Cómo distinguirlo: tras conectar, consulta dónde está registrada la IP; solo cuenta si dice «China · alguna provincia».**

## Cinco cosas que comprobar antes de elegir

| Punto | Cómo comprobarlo | Cómo se ve cuando falla |
|---|---|---|
| Región de salida | Consulta dónde está registrada la IP tras conectar | Direcciones de Hong Kong, Taiwán, Japón o Corea |
| IPv6 y DNS | Busca «test ipv6» y abre una página de prueba | El campo de IPv6 muestra el país en el que estás → las webs de vídeo te seguirán bloqueando; consulta [Solución de problemas 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| Cliente | Si usa un protocolo estándar (AnyConnect, OpenVPN, Hiddify) | Solo hay una app propia, y si la retiran te quedas sin nada que usar |
| Ancho de banda | Reproduce en 1080p entre las 20:00 y las 23:00, hora de Pekín | Rápido de día y cargando sin parar por la noche |
| Varios dispositivos y router | Cuántos dispositivos por cuenta y si un router puede conectar a toda la casa | Hay que pagar cada dispositivo por separado |

## Por qué las líneas gratuitas hacia China se cortan una y otra vez

El problema no es que sea «gratis», sino la estructura de costes. El ancho de banda de salida en China continental se paga por uso, y un servicio gratuito solo puede elegir una de tres: meter a varios miles de personas en una sola máquina, con lo que todos sufren tirones en hora punta; limitar el tráfico y el tiempo, con lo que a mitad de camino salta un aviso de pago; o ganar dinero de otra forma, inyectando anuncios, recopilando el historial de navegación o usando tu dispositivo como salida para otras personas.

Las extensiones de navegador gratuitas «hacia China» tienen otro punto ciego: solo pasan por el proxy las peticiones web del navegador, y ni el reproductor de vídeo, ni las apps, ni el DNS del sistema pasan por ellas; por eso es tan habitual que «la página abre pero el vídeo no se reproduce».

Para consultar algo de vez en cuando, lo gratuito basta. Para seguir series, escuchar música y usar la banca en línea, el tiempo que te ahorra una línea de pago estable vale mucho más que la suscripción. Pide primero la prueba de 24 horas, pruébala una vez en la hora punta de la noche y luego decide.

## Cómo debe configurarlo cada uno: estudiantes en el extranjero, viajeros y familias

- **Estudiantes en el extranjero**: las redes de las residencias suelen tener IPv6, así que usa un cliente que bloquee el IPv6; para la banca en línea, CHSI y 12306, conéctate a la línea hacia China solo cuando lo necesites y desconecta al terminar, para reducir el control de riesgos de la cuenta.
- **Viajes cortos**: instala un cliente Cisco o Hiddify en el móvil e importa escaneando el código QR; funciona nada más aterrizar.
- **Una familia entera que vive en el extranjero a largo plazo**: conecta a la línea un router con el firmware instalado, y la tele, el decodificador y los móviles de los mayores no necesitan configuración; consulta [Desbloquear webs de vídeo chinas con un router](../router/06-unlock-chinese-video-with-router.md).

## Una autoprueba de 5 minutos

1. Conéctate a la línea hacia China; la consulta de IP muestra una provincia de China continental.
2. La página de prueba de IPv6 lo muestra como no disponible, o también como una dirección de China continental.
3. Abre en Tencent Video cualquier serie exclusiva de China; se reproduce.
4. Reproduce otra vez en 1080p después de las 20:00, hora de Pekín; no se queda cargando una y otra vez.
5. Cambia a otra salida en China y repite los tres primeros pasos.

## Preguntas frecuentes

**¿Hay diferencia entre una VPN hacia China y un acelerador hacia China?** No en lo esencial. Un «acelerador» suele ser una app adaptada por una empresa de juegos o de vídeo que solo cubre aplicaciones concretas; una VPN es un túnel para todo el dispositivo.

**¿Puedo ver Tencent Video con un nodo de Hong Kong?** No: la licencia solo cubre China continental.

**¿Cuántos dispositivos por cuenta?** En LeoTun, las conexiones simultáneas dependen del plan: Individual 2 dispositivos, Familiar 4 dispositivos, Empresa 8 dispositivos. Un router cuenta como un dispositivo, y los dispositivos que hay detrás no se cuentan aparte. Si hay más en línea a la vez que el límite de tu plan, puedes subir temporalmente de tipo de cuenta (el tiempo restante se convierte a valor equivalente según el precio) y volver después.

**¿Puedo usar Clash?** Sí. LeoTun ofrece una suscripción sing-box, una suscripción Clash y un enlace para compartir de hysteria2. Con Clash Meta, Clash Verge, FlClash, Stash y similares, haz clic en el botón «Suscripción Clash» y pega la URL en la lista de suscripciones del cliente; no hace falta ningún conversor de suscripciones, y no uses el enlace para compartir. El Clash original y Clash for Windows no sirven, porque a su núcleo le falta hysteria2. Esta suscripción envía por el nodo todo excepto tu red local por defecto, así que no hay que cambiar nada para el vídeo chino; si añades tus propias reglas, no pongas los dominios chinos en «direct» (directo).

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-08) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-08) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
