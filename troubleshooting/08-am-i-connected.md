# 08 · Cómo confirmar que estás conectado de verdad y por qué región sales

Que el cliente diga «Conectado» no significa que las webs que visitas vean la dirección de la VPN. La forma más fácil de comprobarlo está en la barra superior de este sitio: el campo «Red actual» muestra **cómo te ve este sitio en este momento**: desde qué país, qué provincia o estado y qué red sales. Este artículo explica cómo leer ese campo, cómo comparar antes y después de conectar, cómo saber si cada uno de los seis métodos de conexión está conectado, qué significa el semáforo rojo, amarillo y verde de la lista de regiones y unas cuantas cosas que puedes revisar tú mismo cuando está «conectado pero sigue saliendo lo local».

## Qué muestra «Red actual» en la barra superior

| Posición | Contenido |
|---|---|
| Al principio | La bandera del país donde está la salida; si no se puede identificar el país, se sustituye por un icono de wifi |
| En medio | El nombre de la provincia o estado, en el idioma de la interfaz (EE. UU., Canadá, Australia y otros usan abreviaturas habituales como CA, ON o NSW); Hong Kong, Macao y Singapur muestran directamente el nombre de la región |
| Al final | El nombre de la red: los tres grandes operadores chinos, la red educativa y similares aparecen en la interfaz en chino con nombres cortos como 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom) y 教育网 (red educativa); el resto muestran su marca en inglés (p. ej., Comcast, Bell) |

- **Cuando no se encuentra la provincia o el estado, solo se muestra «bandera · nombre de la red».** No se rellena con el nombre del país; la bandera ya te dice el país.
- En el ordenador, pasa el ratón por encima de este campo y aparecerán el nombre completo de la organización, la provincia o estado, el código de país y la **IP de salida**. Esta IP solo la ves tú, y es lo más útil que puedes tener a mano al contactar con soporte.
- Chrome / Edge en Windows no tienen fuente de banderas, así que la bandera aparece como dos letras (p. ej., JP, US). Significa lo mismo.
- En el ordenador aparece en la barra superior solo después de iniciar sesión; en el móvil se muestra sin iniciar sesión.

## Compara antes y después de conectar y lo sabrás de un vistazo

1. **Con la VPN desactivada**, abre este sitio y echa un vistazo: debería aparecer el operador de tu banda ancha de casa o de tus datos móviles, y la bandera del país en el que estás.
2. **Conecta la VPN** y vuelve al navegador: la bandera cambia a la región que elegiste, y el nombre de la red suele cambiar al de un centro de datos o proveedor de nube en lugar de tu operador de casa.
3. Si las dos son iguales, este navegador no está pasando por la VPN al visitar este sitio. Consulta «Conectado, pero sigue saliendo lo local» más abajo.

**No hace falta recargar la página una y otra vez.** Este campo se vuelve a comprobar automáticamente al volver a la ventana del navegador, lo comprueba unas cuantas veces más en los segundos siguientes a detectar un cambio de red y, además, se actualiza cada diez o veinte segundos mientras la página está abierta. Si justo después de conectar sigues viendo el valor anterior, espera diez o veinte segundos o cambia de ventana; si aún no ha cambiado, recarga a mano.

**Cuando estás en China y has elegido un «punto de entrada en China»**, es normal que la barra superior muestre un país extranjero: los puntos de entrada en China usan enrutamiento dividido, así que las webs chinas salen desde dentro de China y las extranjeras salen por la ruta del extranjero. Este sitio está en el extranjero, así que lógicamente lo que se muestra es el extremo extranjero.

## Cómo saber si cada método de conexión está conectado

| Método | Qué mirar en el cliente | ¿Cambia la barra superior de este sitio? |
|---|---|---|
| Cisco (AnyConnect) | El cliente muestra «Connected» (conectado) | Sí. Con Cisco conectado, todo el tráfico pasa por la VPN |
| Hiddify | El cliente se muestra conectado | Cambia en modo global; con el «enrutamiento automático», depende de la lista |
| OpenVPN | El cliente se muestra conectado | Sí. Por defecto, todo el tráfico pasa por la VPN |
| Red Privada (Tailscale) | El cliente está en línea **y** hay una región seleccionada como Exit Node (nodo de salida) | Solo cambia si hay una salida seleccionada; con None (ninguna), los dispositivos solo se ven entre sí y el tráfico no pasa por la VPN |
| Proxy Web | No hay estado de «conectado»; mira qué modo de región está seleccionado en el icono de la extensión | Solo cambia el navegador que tiene la extensión instalada; las reglas de «auto switch» (cambio automático) pueden hacer que este sitio vaya directo |
| Router | En la página de administración, el estado de la cuenta es normal y se muestra la fecha de vencimiento | Míralo desde un dispositivo conectado al wifi de este router; en modo de enrutamiento dividido, depende de la lista |

El enrutamiento dividido significa que las webs de la lista pasan por la VPN y todo lo demás va directo. Si con el enrutamiento dividido activado la barra superior muestra lo local, no significa necesariamente que no estés conectado: **cambia temporalmente a «global» y vuelve a mirar**. Si cambia, la VPN funciona y simplemente este sitio no está en la lista.

## El semáforo rojo, amarillo y verde de la lista de regiones

En las páginas de Cisco, Hiddify, Proxy Web y OpenVPN hay una pequeña luz debajo de la bandera de cada región, y la misma luz aparece delante de los nombres de las salidas en el cliente de la red Privada. Se calcula automáticamente según el ancho de banda medio en tiempo real de los servidores de esa región, y se actualiza más o menos una vez por minuto:

| Luz | Significado |
|---|---|
| Verde (fija) | Libre |
| Amarilla (parpadeando) | En uso |
| Roja (parpadeando) | Ocupada |
| Sin luz | No se han obtenido datos en ese momento; no significa que el servidor esté caído |

En el ordenador, pasa el ratón por encima de la luz para ver la carga media de la región.

**Qué hacer cuando ves una luz roja:**

- Roja no significa averiada; solo significa que en ese momento hay mucha gente. Si ya estás conectado y la velocidad te basta, déjalo como está.
- Si notas que va lento, cambia a una región con la luz en verde. En Cisco, haz clic en otra bandera de la web para copiar la nueva dirección; en Hiddify, importa la configuración de otra región; en la red Privada, cámbiala en Exit Node; en el Proxy Web, haz clic en otra región en el icono de la extensión.
- Detrás de cada región hay varias máquinas, y al conectar se elige automáticamente la menos ocupada. No hace falta que elijas tú una máquina.
- De 20:00 a 23:00 es la hora punta. En esa franja, elige una región con la luz en verde o cambia de método de conexión; si sigue lento, la causa habitual es la banda ancha local (banda ancha compartida de urbanización, o un operador y una región que no casan). Para elegir región según el operador, consulta «Para seguir leyendo».

## Conectado, pero sigue saliendo lo local

Por orden de frecuencia:

1. **Las reglas de enrutamiento hacen que este sitio vaya directo.** El enrutamiento automático de Hiddify, el «auto switch» de la extensión de Proxy Web y el modo de enrutamiento dividido del router pueden dejar este sitio fuera de la VPN. Cambia temporalmente a global para comprobarlo; quien usa Proxy Web también puede añadir este sitio a las reglas.
2. **El proxy web solo cubre ese navegador.** Si miras desde otro navegador o desde una app del móvil, lógicamente seguirá saliendo lo local.
3. **No hay salida seleccionada en la red Privada.** En línea ≠ pasando por la VPN; cuando Exit Node está en None, los dispositivos solo se ven entre sí.
4. **Estás mirando desde el dispositivo equivocado.** Con la opción del router tienes que mirar desde un dispositivo conectado al wifi de ese router, no desde un móvil conectado al wifi del módem o con datos móviles.
5. **Hay otra VPN u otra herramienta de red mallada activada a la vez.** La VPN de la empresa o el acelerador de otro proveedor se pelearán por las rutas. Deja solo una.
6. **Todavía no se ha actualizado.** Espera diez o veinte segundos, cambia de ventana o recarga a mano una vez.

## La barra superior comprueba la IP; el IPv6 y el DNS, compruébalos aparte

La barra superior mira la dirección IPv4 de la conexión que recibió este sitio. Si muestra lo correcto, solo significa que este navegador pasó por la VPN al visitar este sitio:

- **El IPv6 y el DNS no se ven ahí.** Cuando el navegador visita este sitio por IPv6, el campo simplemente no se muestra; no hará pasar una red equivocada por la real. Si una web de vídeo sigue mostrando el aviso de restricción por derechos de autor, lo más probable es que el IPv6 o el DNS se estén saltando la VPN; consulta [03 · IPv6 y DNS son los que se escapan](03-ipv6-and-dns-leak.md).
- **Las apps guardan en caché su comprobación de región.** La barra superior se consulta de nuevo cada vez y no le afecta la caché; pero las apps de vídeo y música recuerdan la región anterior. Ciérralas del todo y vuelve a abrirlas; consulta [02 · Conectado para acceder a China, pero sigues sin poder verlo](02-still-blocked-after-connecting.md).

## Preguntas frecuentes

**¿Ha desaparecido el campo «Red actual» de la barra superior?** En el ordenador, inicia sesión primero. Si tras iniciar sesión sigue sin mostrarse, lo más probable es que esta conexión haya ido por IPv6 o que de momento no se pueda consultar; espera diez o veinte segundos o recarga. Prefiere no mostrar nada antes que mostrar algo equivocado.

**¿La misma región, pero una IP distinta en dos conexiones?** Es normal. Detrás de cada región hay varias máquinas, y en cada conexión se elige la menos ocupada en ese momento. Una conexión ya establecida no se traslada a otra máquina a mitad de camino.

**¿La provincia que aparece no es la que esperaba?** La barra superior muestra la provincia o estado donde se ubica la IP de salida y solo es precisa hasta ese nivel. Si la bandera coincide, la salida está en el país o la región que elegiste.

**¿Qué debo indicar al contactar con soporte?** Pasa el ratón por encima de ese campo de la barra superior y envía lo que aparece (incluida la IP de salida) junto con el método de conexión, la región que elegiste y la hora en que ocurrió el problema.

## Para seguir leyendo

- [Cómo resolver problemas cuando no conecta, va lento o se corta](https://www.leotun.com/es/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Qué región va más rápido desde China](https://www.leotun.com/es/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Qué método de conexión conviene en cada situación](https://www.leotun.com/es/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Qué es el proxy web y cuándo usarlo](https://www.leotun.com/es/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Qué puede hacer el firmware del router](https://www.leotun.com/es/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Qué hacer cuando Tencent Video muestra el aviso de restricción por derechos de autor en el extranjero](https://www.leotun.com/es/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-08) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-08) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
