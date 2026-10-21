# 10 · Cómo debe configurar un estudiante en el extranjero una VPN hacia China

Lo que necesita un estudiante en el extranjero no es «una línea hacia China conectada todo el tiempo», sino poder conseguir una IP china de forma fiable en unas cuantas situaciones concretas: seguir series y escuchar música, entrar en la banca en línea y en apps oficiales, conseguir billetes y, de vez en cuando, revisar a distancia los dispositivos de la familia en China. Cada situación le pide algo distinto a la línea, y las redes de los campus tienen sus propias limitaciones. Este artículo explica, caso por caso, qué hace falta, cómo configurarlo y cuándo desconectar, y termina con una lista de comprobación que se hace en diez minutos antes de empezar el curso.

## Series, música y directos: basta con una IP china, pero hay que cerrar el IPv6

Tencent Video, iQIYI, el anime de Bilibili, NetEase Cloud Music y QQ Music deciden la región por la IP de origen, y basta con conectarse a la línea de China. La trampa en la que más caen los estudiantes es que las redes del campus y de las residencias suelen tener IPv6: el dispositivo prefiere el IPv6, que no pasa por la línea, así que la web de vídeo sigue viendo una dirección extranjera y muestra «restricción por derechos de autor».

La solución es usar una línea o un cliente que rechace el IPv6 dentro del túnel, o desactivar el IPv6 en el dispositivo. Los tres métodos de conexión de LeoTun ya bloquean el IPv6 del lado de la línea, sin tocar el dispositivo; para un diagnóstico detallado, consulta «Qué hacer cuando Tencent Video muestra el aviso de restricción por derechos de autor en el extranjero».

La calidad de imagen depende del ancho de banda internacional. De 20:00 a 23:00 hora de Pekín es la hora punta, que corresponde a la mañana y el mediodía en Europa y Norteamérica; si en esa franja el 1080p se queda cargando una y otra vez, cambia a otra salida de China.

## Banca en línea, Alipay y apps oficiales: entra por la línea de China y desconecta al terminar

Las distintas apps bancarias, Alipay, CHSI (el portal oficial chino de títulos y expedientes académicos) y la Plataforma Nacional de Servicios de Gobierno tratan de forma distinta las IP extranjeras: unas rechazan directamente el inicio de sesión, otras añaden varios pasos de verificación y otras te dejan entrar pero activan el control de riesgos al hacer una transferencia. Lo que tienen en común es que registran tu IP de inicio de sesión, y saltar una y otra vez entre el extranjero y China es lo que más fácilmente te marca como sospechoso.

Qué hacer: cuando tengas que hacer estas gestiones, conéctate primero a la línea de China y luego abre la app; al terminar, cierra la app y después desconecta la línea. No uses la misma app mientras cambias constantemente entre la línea de China y la red local.

Los códigos de verificación por SMS que nunca llegan no tienen nada que ver con la línea: es un problema de itinerancia de un número chino en el extranjero. Antes de salir de China, activa la itinerancia internacional del número o cámbiate a una tarifa que pueda recibir códigos en el extranjero.

## 12306 y la venta de entradas para conciertos: conéctate antes y no cambies al pagar

12306 (la web oficial de billetes de tren de China) a veces pide una verificación adicional desde una IP extranjera, y cuando las entradas vuelan, una verificación de más significa quedarte sin billete. Unos minutos antes de que abra la venta, conéctate a la línea de China, inicia sesión y elige los datos del pasajero, y envía en cuanto llegue la hora. Cuando el pago te lleve a Alipay o a la banca en línea, no toques la línea.

Lo mismo vale para plataformas de entradas como Damai y Maoyan.

## Tres limitaciones de las redes del campus y de las residencias

- IPv6: mira arriba; usa una línea que bloquee el IPv6.
- UDP restringido o limitado: bastantes redes de campus limitan o incluso bloquean el tráfico UDP. El hysteria2 que usa Hiddify va sobre UDP, y en esas redes resulta menos estable que AnyConnect, que va sobre TLS; una misma cuenta puede usar los dos, así que si UDP no funciona, cambia a AnyConnect.
- Portal de acceso (portal cautivo): después de conectarte al wifi del campus, completa primero la autenticación en el navegador y luego activa la línea. Si el cliente está configurado para «conectarse automáticamente al iniciar», intentará conectar antes de la autenticación y fallará; espera un poco más o vuelve a conectar a mano.

## Si pasas las vacaciones en China: la misma cuenta, en sentido contrario

En China necesitarás Google, el correo de tu universidad y las bases de datos de artículos; solo tienes que cambiar la región de la línea de China a Japón, Estados Unidos o una región extranjera cercana, sin cambiar de cuenta. Las 24 regiones de LeoTun están en la misma cuenta, y acceder a China desde el extranjero y acceder a servicios extranjeros desde China son los dos sentidos de lo mismo.

Al conectar desde China, las direcciones de AnyConnect y Hiddify cambian automáticamente para esquivar los bloqueos, y no hace falta cambiar las direcciones guardadas en el cliente; si no conecta, cambia de región o de protocolo.

## Lista de comprobación de diez minutos antes de empezar el curso

1. Instala un cliente (AnyConnect o Hiddify) en el móvil y otro en el ordenador, e inicia sesión o importa escaneando el código QR en cada uno.
2. Conéctate a la línea de China desde el wifi de la residencia y abre una página de prueba de IPv6 para confirmar que el IPv6 no está disponible o muestra una dirección de China continental.
3. Abre Tencent Video y reproduce cualquier episodio para confirmar que no aparece la restricción por derechos de autor.
4. Entra una vez en tu app bancaria para confirmar que puedes acceder; luego cierra la app y desconecta la línea.
5. Apunta el contacto de soporte de tu proveedor de líneas; cuando algo falle, lee primero la guía de solución de problemas y luego pregunta.

## Preguntas frecuentes

**¿Usar una VPN hacia China afecta a mi cuenta de la red de la universidad?** No. La línea solo envía tu tráfico a una salida en China, y lo que ve la red del campus es una conexión cifrada. Las normas de uso de la mayoría de las universidades solo prohíben las descargas ilegales y los ataques, y acceder a servicios de tu país de origen para uso personal no está entre ellos; si tienes dudas, echa un vistazo a la política de uso aceptable de la universidad.

**¿Puedo compartir una cuenta con mi compañero de piso?** Según el plan, una cuenta puede tener 2 (Individual), 4 (Familiar) u 8 (Empresa) dispositivos en línea a la vez, y compartirla con la familia o los compañeros de piso entra dentro de lo que permiten las normas. Pero para cosas como la banca en línea es más seguro que cada uno use su propia cuenta, para evitar que varias personas cambien constantemente en la misma línea y activen el control de riesgos.

**¿Por qué Hiddify va lento en la residencia y AnyConnect va bien?** Lo más probable es que la red del campus restrinja UDP. El protocolo hysteria2 de Hiddify se basa en UDP, y cuando lo limitan va lento o se corta; AnyConnect va sobre TLS, igual que visitar una web HTTPS, y no se ve afectado.

**¿Puedo jugar en servidores chinos con una línea hacia China?** Puedes entrar, pero la latencia depende de tu distancia física a la salida en China. Esa parte de la latencia es fija; es aceptable en juegos por turnos y MOBA, y se nota en los shooters.

**¿La cuenta me sigue sirviendo cuando termine los estudios y vuelva a China?** Sí. La misma cuenta sigue funcionando dentro de China con una región extranjera, para acceder a Google, GitHub, el correo de la universidad y las bases de datos de artículos.

## Para seguir leyendo

- [Qué hacer cuando Tencent Video muestra el aviso de restricción por derechos de autor en el extranjero](https://www.leotun.com/es/guides/overseas-video?utm_source=github&utm_content=china-access-10)
- [Cómo elegir una VPN hacia China](https://www.leotun.com/es/guides/choose-china-vpn?utm_source=github&utm_content=china-access-10)
- [Descarga del cliente AnyConnect](https://www.leotun.com/es/anyconnect?utm_source=github&utm_content=china-access-10)
- [Cliente Hiddify e importación de la suscripción](https://www.leotun.com/es/singbox?utm_source=github&utm_content=china-access-10)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/students?utm_source=github&utm_content=china-access-10

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-10) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-10) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
