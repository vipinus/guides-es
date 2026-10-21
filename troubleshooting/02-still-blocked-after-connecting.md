# 02 · Conectado para acceder a China, pero sigues sin poder verlo: qué hacer

Revisa en este orden. Cada paso lleva un minuto.

1. **Confirma que la IP de salida ha cambiado de verdad.** Abre en el navegador una web que muestre la ubicación de tu IP y mira si sale China continental. Si no, la VPN no está funcionando; vuelve a conectar.
2. **Fugas de IPv6 y DNS.** Si la IP de salida es correcta pero la web sigue creyendo que estás en el extranjero, lo más probable es que el IPv6 o el DNS local del dispositivo se estén saltando la VPN. Es el caso más frecuente y tiene su propio artículo: [03 · IPv6 y DNS son los que se escapan](03-ipv6-and-dns-leak.md).
3. **Caché de la app.** Las apps de vídeo y música guardan en caché el resultado de la comprobación de región. Cierra la app del todo y vuelve a abrirla; si no basta, borra los datos de la app.
4. **Versión de la app.** Si instalaste la versión internacional (iQIYI, WeTV), el catálogo es distinto. Cámbiate a la versión de China continental.
5. **Dónde se registró la cuenta.** Unas pocas plataformas limitan el contenido según la región en la que se registró la cuenta, sea cual sea tu IP actual. En ese caso la única solución es usar otra cuenta.
6. **Región e idioma del sistema.** Algunas apps leen la región del sistema. Cambia la región del sistema a China y vuelve a probar.
7. **Región de entrada.** Parte del contenido también cambia entre IP de distintas provincias. Cambia a otro punto de entrada y vuelve a probar.

## Si sigue sin funcionar

Dile al soporte estas cuatro cosas: la web o app a la que quieres acceder, el texto exacto del error, dónde se ubica tu IP de salida actual y el método de conexión que usas. Con eso, el problema se localiza a la primera.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
