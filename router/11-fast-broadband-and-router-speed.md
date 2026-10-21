# 11 · Banda ancha de un gigabit o de 2 Gbps con router: qué decide la velocidad

La banda ancha doméstica es cada vez más rápida, así que la pregunta sale a menudo: si mi línea es de un gigabit, o incluso de 2 Gbps, ¿qué velocidad tendré a través de un router con VPN?

## La respuesta corta

Para el tráfico que pasa por el túnel, la velocidad la decide el tramo que sale de China. **El cuello de botella no es la línea de tu casa, sino el tramo que sale de China.** Garantizamos que YouTube se reproduce con fluidez. La velocidad exacta depende de lo que se explica abajo.

El tráfico hacia servicios chinos no usa el túnel y sigue yendo a toda la velocidad de tu banda ancha. Consulta [10 · ¿Se verán afectados el NAS, la impresora y las cámaras?](10-nas-printer-camera-behind-router.md)

## Cuatro cosas que deciden la velocidad

**1. El tramo internacional**
La capacidad internacional la comparte todo el mundo y no tiene nada que ver con lo rápida que sea tu tarifa de casa. De 20:00 a 23:00 hora de Pekín es la hora punta en todo el país; en esa franja elige una región con el semáforo en verde. Si sigue lento, la causa habitual es la banda ancha local (banda ancha compartida de urbanización, o un operador y una región que no casan; mira el punto siguiente). Consulta [Por qué a veces va rápido y a veces lento](../network/06-why-sometimes-fast-sometimes-slow.md).

**2. Tu operador y la región que eliges**
Cada operador sale de China por un camino distinto, y acertar con la región importa más que cualquier otra cosa:
- China Unicom en el norte: prueba primero Japón y Corea
- China Telecom en el sur: prueba primero el Sudeste Asiático
- Otros operadores: prueba primero las regiones de entrada en China

**3. El propio router**
El tráfico tiene que cifrarse antes de entrar en el túnel, y ese trabajo lo hace el procesador del router. Los modelos son muy distintos:
- GL-MT300N-V2 (mini): puertos de 100 Mbps. Suficiente para 1080p en un móvil o un portátil, pero no está a la altura de una línea rápida
- GL-MT3000 (de viaje): puede con un hogar pequeño. El primer router para la mayoría
- GL-MT6000 (de sobremesa): puerto de 2,5G. Para muchos dispositivos, 4K y consolas

Con una línea rápida y una casa con mucho uso, elige el MT3000 o el MT6000, no el mini.

**4. Los últimos metros en casa**
Conecta por cable la tele y el ordenador de sobremesa siempre que puedas. El wifi en un bloque de pisos abarrotado sufre muchas interferencias, y muchas veces «la línea va lenta» resulta estar dentro de casa.

## Si notas que va lento, prueba esto en orden

1. Cambia de región. Prueba dos o tres y quédate con la que aguante a esa hora del día.
2. Activa «Seleccionar automáticamente la línea más rápida» en la página de administración. Elige la línea con menor latencia y pérdida, y cambia cuando eso varía. Ten en cuenta que entonces el país de salida puede ser distinto de la región que elegiste.
3. Conecta por cable el dispositivo en el que ves vídeo.
4. Comprueba si solo pasa con esa web. Si en ese mismo momento otras webs van rápido, la lenta tiene un problema en su extremo.

## Cómo saberlo antes de comprar

Regístrate y usa la prueba gratuita de 4 horas, sin tarjeta de crédito. Conéctate a la hora del día en que más lo usas, por ejemplo por la noche, y mira un vídeo de YouTube en HD. Lo que ves en un móvil o un portátil se parece mucho a lo que te dará el router. Decide lo del router después.

## Preguntas frecuentes

**¿Por qué no me dicen sin más cuántos megas?** Porque la cifra es distinta para cada persona y cada hora. Garantizamos que YouTube se reproduce con fluidez incluso en la hora punta de la noche, siempre que tu banda ancha sea buena: China Unicom en el norte o China Telecom en el sur. La excepción es la banda ancha compartida de urbanización (la que reparte un único acceso entre todo un complejo residencial). Usar la prueba gratuita de 4 horas y probarlo una vez tú mismo es la medición más fiable.

**¿El test de velocidad da una cifra baja, pero el vídeo va bien?** Es normal. Los servidores de los test de velocidad tienen sus propios momentos de saturación y de calma, y dos pruebas con un minuto de diferencia pueden variar al doble. Juzga por lo que de verdad quieres hacer.

**¿Un router más caro lo hará más rápido?** Solo si el cuello de botella es el router, por ejemplo un modelo mini con una línea rápida. Cuando el cuello de botella es el tramo internacional, un router nuevo no cambia nada y otra región sí.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-11) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-11) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
