# 05 · Cómo detectar programas VPN peligrosos

Todo tu tráfico pasa por las manos de una app VPN, y puede mirar lo que quiera. Hay dos tipos de producto en el mercado con los que conviene tener especial cuidado: uno es lo que en este mundillo se llama una «VPN roja», con respaldo de los reguladores, que exige tu identidad real en nombre del cumplimiento normativo y entrega los registros; el otro es el acelerador gratuito de origen desconocido, que se financia con tus datos, con tu dispositivo o con algo que te instala. Lo que tienen en común es que «funcionan bien»; el problema está donde no lo ves. Abajo tienes diez señales que puedes comprobar tú mismo, qué hacer si ya has instalado una y una autoprueba de tres minutos.

## Por qué un programa VPN es más arriesgado que una app normal

Una VPN funciona a nivel de sistema: recibe el tráfico de todos los programas del dispositivo, incluidos los que ni sabes que se están ejecutando en segundo plano. Una app normal filtra los datos que ella misma ha recopilado; una VPN filtra todo lo que haces en ese dispositivo. Por eso el listón para elegir un programa VPN tiene que estar mucho más alto que para elegir una app normal.

«Yo la he usado y no ha pasado nada» no es una prueba de seguridad. El registro, la entrega de datos y la inyección ocurren en el servidor o en segundo plano y no se notan desde el lado del usuario; cuando algo sale mal suele ser meses después, y ya no se puede rastrear qué programa fue.

## Diez señales

- Origen desconocido: el instalador llega por un chat de grupo, una nube compartida o un código QR, sin web oficial ni ficha en una tienda de apps. Un cliente legítimo viene de una tienda de apps, de la web oficial del desarrollador o de una página de publicaciones donde se puede comprobar la firma.
- Te pide instalar un certificado raíz: durante la instalación te pide «confiar en el certificado» o «instalar el perfil» y exige confiar en una autoridad de certificación (CA). Con el certificado raíz instalado, puede abrir todo tu tráfico HTTPS, incluidos la banca en línea y el correo. Una VPN normal no necesita este paso.
- Demasiados permisos: una VPN que pide contactos, SMS, registro de llamadas, ubicación precisa y acceso a la fototeca. Una VPN solo necesita el permiso para montar un túnel; lo demás no le sirve para nada.
- Exige registro con nombre real: para darte de alta pide un documento de identidad, un escaneo facial o vincular un número de móvil de China continental. Así es como una VPN supuestamente «conforme a la ley» ata tu identidad a tus registros de tráfico; un servicio legítimo solo necesita un correo electrónico.
- Protocolo propietario + cliente de código cerrado: solo puedes usar su propia app y no admite ningún protocolo estándar (AnyConnect, OpenVPN, WireGuard, Hiddify), así que no puedes usar un cliente de código abierto de terceros para comprobar qué transmite realmente.
- Gratis y sin fuente de ingresos visible: sin plan de pago, sin anuncios, sin clientes empresariales, y aun así funciona año tras año. El ancho de banda de salida en China continental se cobra por uso, y un servicio que no cobra siempre lo recupera por otro lado.
- Sin empresa, sin soporte, sin historial: no se encuentra quién lo gestiona, no hay a quién contactar, el dominio se registró hace menos de un año y cambia a menudo de nombre y de fachada.
- Tráfico anómalo en segundo plano: el dispositivo sigue subiendo datos aunque no lo estés usando, y la batería y los datos se gastan rápido. Puede que esté usando tu dispositivo como salida para otras personas, o sincronizando tus datos.
- Su publicidad insiste en que es «oficial», «registrada» y «legal y conforme a la normativa», e insinúa que todo lo demás es ilegal: es el discurso más típico de una «VPN roja», y su «cumplimiento» consiste en registrar y entregar datos.
- Las valoraciones en la tienda de apps son unánimes, las reseñas se parecen entre sí y el número de descargas no guarda proporción con el de reseñas: son falsas.

## Cómo comprobarlo

1. Fíjate en el protocolo: si la web oficial dice qué protocolo usa y si se puede usar un cliente de terceros. Con un servicio al que puedes conectarte con clientes de código abierto o estándar como OpenVPN, AnyConnect, Hiddify y Tailscale, puedes capturar los paquetes tú mismo y ver qué se transmite.
2. Fíjate en los permisos: tras instalarla, ve a los ajustes del sistema para ver qué permisos ha pedido, desactiva todo lo que no sea la VPN y mira si sigue funcionando. Si no funciona, desinstálala.
3. Fíjate en los certificados: en iOS, Ajustes → General → VPN y gestión de dispositivos; en Android, Ajustes → Seguridad → Cifrado y credenciales → Credenciales de confianza → Usuario; en Windows, «Entidades de certificación raíz de confianza» en el administrador de certificados. Si hay un certificado que instaló ella, bórralo y desinstala la app.
4. Comprueba las fugas: tras conectar, abre una prueba de fugas de DNS y una página de prueba de IPv6 para ver si tanto la resolución como la dirección pasan por sus servidores; luego abre una web HTTPS y comprueba si el emisor del certificado es la CA original.
5. Comprueba quién hay detrás: si la web oficial presenta a la empresa o al equipo, cuántos años lleva funcionando y dónde está el soporte; si las reglas de reembolso están por escrito; si la política de privacidad dice claramente qué se registra.

## Qué hacer si ya has instalado una

1. Desinstala el programa y luego revisa los lugares mencionados arriba y borra los certificados y perfiles que haya instalado.
2. Cambia las contraseñas: banca en línea, correo y las cuentas que más uses, sobre todo aquellas en las que iniciaste sesión mientras la usabas.
3. En las cuentas con verificación en dos pasos activada, revisa el historial de inicios de sesión y elimina cualquier dispositivo que no reconozcas.
4. Si estaba instalada en un router, restablece los valores de fábrica y vuelve a instalar un firmware oficial o de confianza.

## Cómo te dejamos comprobarlo

Todos los clientes de LeoTun proceden de fabricantes oficiales y de organizaciones de código abierto conocidas: Cisco, OpenVPN, Hiddify y Tailscale, replicados tal cual y sin modificar, y en cualquier momento puedes sustituir la copia descargada de este sitio por el cliente oficial o de código abierto. Los protocolos son todos estándar y se pueden comprobar capturando paquetes.

Para registrarte solo necesitas un correo electrónico, sin número de teléfono ni documento de identidad. Solo guardamos la información necesaria para la facturación; no registramos lo que visitas, no inyectamos anuncios y no vendemos datos.

No instalamos certificados ni pedimos los contactos ni la ubicación. Si algún día nuestro cliente te pide instalar un certificado raíz, seguro que no somos nosotros.

## Preguntas frecuentes

**¿Todo lo gratuito es inservible?** Los clientes de la comunidad de código abierto (OpenVPN, Hiddify, Tailscale) son gratuitos y de confianza; el riesgo está en un «servicio gratuito», no en el «software gratuito». Con un servicio gratuito, fíjate en de qué vive.

**¿Algo es seguro por estar en una tienda de apps?** Estar publicado solo demuestra que pasó la revisión automática de la tienda; no significa que el servidor no registre. Fíjate en los permisos, el registro con nombre real, el protocolo y quién hay detrás, entre las diez señales de arriba; la tienda no comprueba eso por ti.

**¿Qué es una supuesta «VPN roja»?** El nombre que se usa en este mundillo para una VPN con respaldo de los reguladores, que exige registro con nombre real en nombre del cumplimiento normativo y conserva los registros. Suelen anunciarse como «oficiales» y «legales» y funcionan con normalidad; el problema es que tu identidad y todos tus registros de tráfico quedan atados.

**¿Cómo sé si una VPN ha registrado mi contenido?** Desde el lado del usuario no se puede saber; solo puedes fijarte en cuántas formas de comprobarlo te da: si el protocolo es estándar, si el cliente es de código abierto, si la política de privacidad es concreta y si se puede averiguar quién la gestiona. Si no cumple ninguna de las cuatro, da por hecho que registra.

**¿El firmware de router también tiene este tipo de riesgo?** Sí; un «firmware para saltarse la censura» de origen desconocido puede secuestrar toda la red de casa. Instala solo OpenWrt oficial o un firmware cuyo código se pueda revisar; el firmware de este sitio se compila a partir de OpenWrt, añadiendo solo los componentes para conectar con la línea y las reglas de enrutamiento dividido.

## Para seguir leyendo

- [En qué nos diferenciamos de otras VPN](https://www.leotun.com/es/guides/why-us?utm_source=github&utm_content=network-05)
- [VPN hacia China: gratis o de pago](https://www.leotun.com/es/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Qué hacer cuando Tencent Video muestra una restricción por derechos de autor en el extranjero](https://www.leotun.com/es/guides/overseas-video?utm_source=github&utm_content=network-05)
- [Quiénes somos: cómo está construido y qué registramos](https://www.leotun.com/es/about?utm_source=github&utm_content=network-05)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=network-05) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=network-05) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
