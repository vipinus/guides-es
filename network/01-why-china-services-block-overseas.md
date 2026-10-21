# 01 · Cómo funciona el acceso a China desde el extranjero

## Lo que ves

Estás fuera de China, abres iQIYI, Bilibili o NetEase Cloud Music y te sale «Este contenido solo está disponible en China continental»; la banca en línea y 12306 (la web de trenes) directamente no cargan, o el código de verificación nunca llega.

## Solo hay una causa: dónde está registrada tu IP

Cuando tu dispositivo se conecta a internet, tu operador le asigna una dirección IP pública. Existe un registro mundial de estas direcciones que indica a qué país y a qué operador pertenece cada una. Las plataformas chinas de vídeo y música compran derechos solo para **China continental** y legalmente no pueden emitir fuera, así que te rechazan en cuanto ven una IP extranjera.

Los bancos y las webs de billetes siguen otra lógica. Para ellos no es cuestión de derechos de autor sino de control de riesgos: un inicio de sesión desde una IP extranjera se considera de alto riesgo y se bloquea sin más.

## Cómo se soluciona

Hay que conseguir que la IP que ve el servidor sea de China continental. Para eso, tu tráfico va primero a un servidor situado en China continental, que visita la web de destino en tu nombre. La web ve la IP de ese servidor y te deja pasar.

Eso es lo que hace una «línea hacia China»: tu tráfico sale a internet con una IP de China continental.

## Tres ideas equivocadas habituales

- **Cambiar el DNS no sirve.** El DNS solo traduce nombres de dominio a direcciones; la web de destino mira tu IP de origen, no el DNS que usas.
- **Algunas plataformas también miran la región del sistema.** Además de la IP, unas pocas comprueban el idioma del dispositivo y la región de la tienda de apps; en ese caso cambia también la región del sistema.
- **La velocidad depende de la calidad de la línea entre los dos extremos.** El cuello de botella es el enlace transfronterizo entre el extranjero y China continental, así que importa más elegir un punto de entrada cercano a ti y con buena ruta hacia China que las especificaciones del propio servidor.

## Para seguir leyendo

- [Qué método de conexión conviene en cada situación](02-choose-your-connection-method.md)
- [Lista de comprobación cuando no conecta, va lento o se corta](../troubleshooting/01-cannot-connect-slow-drops.md)

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=network-01) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=network-01) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
