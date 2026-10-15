# 04 · En qué nos diferenciamos de otras VPN

Las VPN del mercado se dividen más o menos en tres tipos: las grandes marcas internacionales pensadas para usuarios de todo el mundo, los proveedores de líneas proxy (los «jichang» de los círculos de habla china, que revenden suscripciones proxy) y todo tipo de programas gratuitos. LeoTun tiene servidores propios desde 2006 y se dedica a una sola cosa: mantener la conexión estable en los dos sentidos para quien está en China continental y para quien, desde fuera, necesita llegar a China. Este artículo nos compara punto por punto con esos tres tipos de producto, explica a quién le conviene cada uno y cómo trabajamos nosotros, para que lo tengas claro antes de pagar.

## Lo que somos, en una frase

Somos un servicio **optimizado específicamente para la red de China continental**, no un revendedor de líneas internacionales. La calidad de las salidas internacionales de China Telecom, China Unicom y China Mobile es muy distinta; ajustamos cada operador por separado y recomendamos regiones diferentes para cada uno. Tenemos nodos de llegada dentro de China, para que incluso quien tiene una banda ancha mediocre cuente con un punto de entrada estable. Y vamos adaptando puertos y protocolos a medida que cambia la red en China, en lugar de configurarlo todo una vez y olvidarnos.

En el otro sentido, si estás fuera de China y necesitas servicios chinos, basta con elegir la región de China con la misma cuenta: las webs chinas salen por una IP china y las webs de fuera de China siguen saliendo fuera de China. Acceder a China desde el extranjero y acceder a servicios extranjeros desde China son los dos sentidos de lo mismo.

## Frente a las grandes marcas internacionales

- Sus puntos fuertes: decenas de países, miles de servidores, apps maduras y políticas de no registro auditadas por terceros. Si estás en Europa o América y solo quieres cifrar el tráfico en un wifi público o ver el streaming de otro país, son una buena opción.
- Sus puntos débiles: el producto no está diseñado para la red china. La huella de un protocolo propietario es fija, y en cuanto se identifica dentro de China deja de funcionar toda la app; no tienen nodos de llegada en China, así que para ver vídeo chino desde el extranjero o no ofrecen la función o usan IP de Hong Kong o Taiwán, que Tencent Video e iQIYI bloquean igualmente.
- Lo que hacemos nosotros: solo protocolos estándar (AnyConnect, OpenVPN, Hiddify, Tailscale, proxy web HTTPS), con clientes que vienen de los propios fabricantes o de la comunidad de código abierto. Lo que se puede bloquear es como mucho una dirección concreta, y basta con cambiar de dirección; el cliente no desaparece de la tienda.
- Lo que hemos decidido: 24 regiones, cada una respaldada por varias máquinas, y al conectar se elige automáticamente la menos cargada; los clientes son las versiones oficiales de los fabricantes y de la comunidad de código abierto, y se configuran escaneando un código QR o importando con un clic; no tenemos informe de auditoría de terceros; lo que registramos y lo que no está escrito en la página «Sobre nosotros», y confiamos en explicarlo con claridad más que en un sello.

## Frente a los proveedores de líneas proxy

- Sus puntos fuertes: son baratos, tienen muchos nodos, funcionan en cuanto pegas un enlace de suscripción, y a quien le gusta trastear con clientes le encanta esa libertad.
- Sus puntos débiles: la mayoría son particulares o equipos pequeños que alquilan máquinas en el extranjero y revenden tráfico, sin llegada propia en China, y la calidad de la salida depende de las líneas alquiladas; es habitual que desaparezcan con el dinero, cambien de nombre o cierren, y pagar un año no garantiza que puedas usarlo el año entero; el cliente queda casi por completo en tus manos, y cuando algo falla nadie se hace responsable.
- Lo que hacemos nosotros: las máquinas son nuestras, y las salidas en China son máquinas propias registradas con nombre real en proveedores de nube de China continental; una cuenta tiene seis métodos de conexión, y la solución de router para toda la casa y el grupo de soporte 24 horas son cosas que los proveedores de líneas proxy no tienen; funcionamos desde 2006 hasta hoy, y las cuentas, las fechas de vencimiento y los precios no cambiaron con el cambio de nombre.
- Nuestros precios: plan Individual 4 USD al mes, Familiar 8 USD y Empresa 16 USD, lo que incluye máquinas propias, seis métodos de conexión y el grupo de soporte 24 horas; tú solo eliges la región, y detrás de cada región el sistema elige la máquina menos cargada, así que no tienes que medir velocidades ni escoger nodos.

## Frente a los programas gratuitos

- Su punto fuerte: no cuestan nada y bastan para consultar algo de vez en cuando.
- Sus puntos débiles: el ancho de banda de salida en China continental se paga por uso, así que un servicio gratuito solo se sostiene amontonando usuarios, limitando la velocidad o vendiendo datos; los que son extensiones del navegador solo hacen de proxy para las páginas web, y el vídeo, las apps y el DNS del sistema no pasan por ellos; los instaladores de origen desconocido son un riesgo en sí mismos (consulta «Cómo detectar programas VPN peligrosos»).
- Lo que hacemos nosotros: la prueba gratuita de 24 horas no pide tarjeta de crédito y sirve para comprobar el servicio; el pago por días (con puntos) es para quien lo usa de vez en cuando; cuando un amigo que invitas paga, cada uno recibe 20 días (según el plan Individual), una fuente de tiempo gratis a largo plazo.
- Cómo lo organizamos: el tiempo gratis sale de la prueba de 24 horas y de las recompensas por invitación; para un uso continuado se paga por meses, por años o por días.

## Seis métodos de conexión, una sola cuenta

Red Privada (Tailscale): inicias sesión una vez y se queda en línea para siempre; la región se cambia desde el menú. Cisco AnyConnect: la mejor compatibilidad, integrado en el sistema o con cliente oficial. OpenVPN: para routers, NAS y Linux. Proxy Web: solo pasa por él el navegador y, por diseño, no tiene conexión que se pueda caer. Hiddify: resiste la pérdida de paquetes y da la mejor velocidad. Router: acceso para todos los dispositivos de la casa, incluidos teles, decodificadores y los dispositivos de los mayores.

Cada red tiene un método que le va mejor, por eso tienes los seis: con la misma cuenta cambias cuando quieras, de Hiddify a AnyConnect si la red del campus restringe UDP, o al Proxy Web si la banda ancha va a tirones. Para elegir, consulta «Qué método de conexión conviene en cada situación».

## Normas de la cuenta

- Las cuentas tienen tres planes, Individual, Familiar y Empresa, con 2, 4 y 8 dispositivos en línea a la vez respectivamente; las regiones, el tráfico y los métodos de conexión son iguales en los tres. No hay límite de dispositivos donde instalarlo, solo de conexiones simultáneas. Cuando los dispositivos en línea a la vez superan el límite del plan, puedes subir temporalmente de tipo de cuenta (el tiempo restante se convierte a valor equivalente según el precio) y volver cuando termines.
- Puedes cambiar entre los tres planes en cualquier momento, y el tiempo restante se convierte a valor equivalente (Familiar y Empresa cuestan 2 y 4 veces el precio del Individual); los tres planes admiten router, y para una sola persona basta con el Individual.
- Los reembolsos son proporcionales al tiempo usado, se pueden pedir en cualquier momento y se tramitan a mano; no prometemos una fecha concreta de abono.
- Velocidad: garantizamos que YouTube se reproduce con fluidez incluso en la hora punta de la noche, siempre que tu banda ancha sea buena: China Unicom en el norte o China Telecom en el sur. La excepción es la banda ancha compartida de urbanización (la que reparte un único acceso entre todo un complejo residencial). Si una región va lenta, cambia de región o de método de conexión.
- Las configuraciones de Hiddify y OpenVPN llevan incorporada tu cuenta, y al cambiar la contraseña las configuraciones antiguas dejan de valer: si pierdes el móvil o se filtra un enlace, un cambio de contraseña lo recupera todo, y después solo tienes que volver a importar.

## Cómo trabajamos

- Solo guardamos la información necesaria para la facturación. No registramos lo que visitas, no insertamos anuncios y no vendemos datos.
- Todos los clientes vienen de fabricantes oficiales y de organizaciones de código abierto conocidas: Cisco, OpenVPN, Hiddify y Tailscale, replicados tal cual, sin modificar; la configuración se hace escaneando un código QR o importando con un clic.
- La región de China funciona con máquinas en China continental, y todas sus IP de salida están en China continental.

## Preguntas frecuentes

**¿Son ustedes más seguros que las grandes marcas internacionales?** La fuerza del cifrado es comparable; los dos usamos protocolos estándar. La diferencia está en el modelo de confianza: las grandes marcas se apoyan en informes de auditoría; nosotros solo guardamos la información necesaria para la facturación, y todos los clientes vienen de fabricantes oficiales y de organizaciones de código abierto conocidas.

**¿Por qué no ofrecen cientos de nodos como los proveedores de líneas proxy?** Más nodos no significa más estabilidad. Detrás de cada una de nuestras regiones hay varias máquinas, y al conectar el sistema elige la menos cargada, así que no tienes que hacer pruebas de velocidad ni escoger nodos; cuando se bloquea una dirección se sustituye automáticamente, y no tienes que cambiar la dirección en tu cliente.

**¿Podría salir más barato?** El plan Individual cuesta 4 USD al mes, y cuanto más tiempo compras mayor es el descuento (5 % → 10 % → 20 %); por días, con puntos, sale por unos 0,32 USD al día; cuando un amigo que invitas paga, cada uno recibe 20 días más (según el plan Individual), sin límite de personas. Además, al registrarte tienes una prueba gratuita de 24 horas.

**¿Cómo puedo comprobar lo que dicen?** Pide la prueba de 24 horas, conéctate a la región de China en la hora punta de la noche y mira un episodio en Tencent Video, conéctate a una región extranjera y abre YouTube, y comprueba la ubicación registrada de la IP y una página de prueba de IPv6. La lista de comprobaciones está en «Cómo elegir una VPN hacia China».


## Para seguir leyendo

- [Qué método de conexión conviene en cada situación](https://www.leotun.com/es/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Cómo detectar programas VPN peligrosos](https://www.leotun.com/es/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [VPN hacia China: gratis o de pago](https://www.leotun.com/es/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [Sobre nosotros: cómo está montado y qué registramos](https://www.leotun.com/es/about?utm_source=github&utm_content=network-04)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/why-us?utm_source=github&utm_content=network-04

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=network-04) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=network-04) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
