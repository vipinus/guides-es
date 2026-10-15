# 12 · Cómo prepararte para viajes de negocios y turismo

Para un viaje corto al extranjero o un viaje de trabajo a China no necesitas un router ni estudiar protocolos: instala el cliente de Cisco (Cisco Secure Client) en el móvil, prueba a conectar una vez antes de salir y funcionará nada más aterrizar. Los dos sentidos son lo mismo: fuera de China, cuando necesites Google, el correo de la empresa y los mapas, elige una región extranjera cercana; en China, cuando quieras ver vídeo chino o entrar en la banca en línea china, elige la región de China. Este artículo cubre diez minutos de preparación antes de salir, dos trampas habituales de las redes de hoteles y aeropuertos, y cómo usar la banca en línea y las apps de pago.

## Diez minutos antes de salir

1. Instala Cisco Secure Client en el móvil (App Store / Google Play, o el instalador de la página de Cisco de este sitio), inicia sesión en este sitio, haz clic en una bandera para copiar la dirección de una región e introdúcela; luego conecta una vez con el usuario y la contraseña de tu cuenta de este sitio para confirmar que funciona.
2. Copia las direcciones de dos regiones más y guárdalas en el cliente: una cerca de tu destino y otra de reserva. Allí la red será distinta, y la mejor región a menudo no es la misma.
3. Apunta los cuatro dominios (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) y el acceso a al menos un grupo de soporte, para poder encontrar a alguien si algo falla en un lugar cuya red no conoces.
4. Instálalo también en el portátil, o usa la extensión de proxy web; si en un ordenador de la empresa no se puede instalar un cliente, esta sigue funcionando.

## Después de aterrizar

- Si has cambiado a una SIM local o has activado la itinerancia, el cliente conecta sin más y no hay que reconfigurar nada; si los datos en itinerancia ya salen del país de por sí, conectarte a la línea solo sirve para fijar la región de salida.
- Fuera de China, cuando necesites Google, Gmail, el correo de la empresa y los mapas: elige una región extranjera cercana para tener la mejor velocidad.
- En China, cuando quieras ver Tencent Video e iQIYI, escuchar NetEase Cloud Music o entrar en la banca en línea china: elige la región de China. Las webs chinas salen con una IP china y las extranjeras siguen saliendo por el extranjero, así que conectarte a la región de China estando en China no te impide seguir usando Gmail.
- Si desde China no conecta una región extranjera: cambia de región, pasa a los datos móviles y, si aun así falla, cambia a Hiddify u OpenVPN; los bloqueos de los tres protocolos son independientes entre sí.

## Dos trampas de las redes de hoteles, aeropuertos y cafeterías

- Portal de inicio de sesión (portal cautivo): tras conectarte al wifi, completa primero la autenticación en el navegador y luego activa la línea. Un cliente configurado para conectarse automáticamente lo intentará antes de la autenticación y fallará; espera un momento o vuelve a conectar a mano.
- Restricciones de UDP: bastantes redes de hoteles y aeropuertos limitan o bloquean UDP. Cisco funciona sobre TLS y no le afecta, que es también la razón por la que Cisco es la primera recomendación para viajar; si usas Hiddify o la red Privada y va lento o se corta, cambia a Cisco.

## Banca en línea, pagos, 12306

Estas apps registran la IP de inicio de sesión, y saltar una y otra vez entre el extranjero y China es lo que más fácilmente dispara el control de riesgos. Cuando tengas que hacer un trámite, conéctate primero a la región de China y luego abre la app; al terminar, cierra la app y después desconecta. Mientras viajas, no uses el mismo banco en línea alternando a menudo entre los dos tipos de red.

Los códigos de verificación por SMS que nunca llegan no tienen nada que ver con la línea; es un problema de itinerancia del número de teléfono. Antes de salir, activa la itinerancia de tu número chino o cambia a una tarifa que pueda recibir códigos en el extranjero.

## Preguntas frecuentes

**El viaje es de solo unos días. ¿Tengo que comprar un mes?** No. Pide la prueba gratuita de 24 horas, o recarga puntos y paga por días: el plan Individual cuesta 1 punto al día, unos 0,32 USD diarios, perfecto para unos pocos días.

**¿Pueden conectarse a la vez el móvil y el portátil?** Sí. Según el plan, una cuenta permite 2 / 4 / 8 dispositivos en línea a la vez (Individual / Familiar / Empresa), y el plan Individual es justo un móvil más un portátil.

**¿Por qué se recomienda Cisco para viajar y no Hiddify?** En una red desconocida, lo que más preocupa es que UDP esté restringido. Cisco funciona sobre TLS, igual que al visitar una web HTTPS, y pasa casi en cualquier sitio; Hiddify es más rápido en redes con mucha pérdida de paquetes, pero no funciona cuando UDP está restringido. Lo más fiable es instalar los dos y cambiar cuando uno no funcione.

**¿Usar la región de China en el extranjero hará más lentas las webs locales?** Las webs locales van más fluidas con conexión directa: desconecta cuando termines con el contenido chino, o conéctate solo cuando lo necesites.

## Para seguir leyendo

- [Descarga y configuración de Cisco AnyConnect](https://www.leotun.com/es/anyconnect?utm_source=github&utm_content=china-access-12)
- [Cómo debe configurar un estudiante en el extranjero una VPN hacia China](https://www.leotun.com/es/guides/students?utm_source=github&utm_content=china-access-12)
- [Cómo contactar con nosotros y no perder el contacto](https://www.leotun.com/es/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [VPN hacia China: gratis o de pago](https://www.leotun.com/es/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/travel?utm_source=github&utm_content=china-access-12

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-12) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-12) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
