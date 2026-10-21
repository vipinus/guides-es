# 09 · Cómo funciona el enrutamiento dividido del router

> Versión web (más extensa): https://www.leotun.com/es/guides/router-smart-split?utm_source=github&utm_content=router-09

Todos lo llaman «enrutamiento dividido inteligente», y aun así algunos routers resultan incómodos de usar. Para saber qué es el enrutamiento dividido, consulta la [03](03-router-split-routing.md); este artículo solo trata de lo que debería hacer, de los síntomas que ves cuando falta una parte y de cómo lo hace nuestro router.

## En una frase

Lo que debería hacer el enrutamiento dividido: cada web, **junto con sus imágenes, su vídeo y su inicio de sesión**, va por la VPN o conecta directamente según dónde esté, y **todos los dispositivos de la casa siguen las mismas reglas**. Cuando solo se hace una parte, aparecen los síntomas de abajo.

## Síntomas, uno por uno

| Lo que ves | Lo que pasa por detrás |
|---|---|
| Con el enrutamiento dividido activado, las webs chinas van incluso más lentas | Las webs chinas se toman por extranjeras y todo da un rodeo por el extranjero y vuelve |
| La página carga, pero el vídeo se queda cargando, las imágenes no aparecen y el inicio de sesión se cuelga | La lista solo incluye el sitio principal, y el vídeo, las imágenes y el inicio de sesión de esa misma web van por otro camino |
| Estás en el extranjero con la línea hacia China activada y la app de vídeo sigue diciendo «仅限中国大陆» (solo para China continental) | Parte del tráfico no entró en la VPN y la web vio una dirección extranjera |
| En el móvil se reproduce, pero en la tele o el TV box no; un ordenador no hay manera de que pase por la VPN | Ese dispositivo tiene su propia configuración de red y se salta el router |
| Las apps de banca y de pago avisan de vez en cuando de un «inicio de sesión desde otra ubicación» | El tráfico de la misma app sale un momento por China y al siguiente por el extranjero |
| El enrutamiento dividido desaparece mientras lo usas (tras reiniciar o reconectar, o todo pasa por la VPN o nada) | La configuración no se guardó |

Ninguno de estos casos **da un error**. El router muestra «Connected» (conectado) todo el tiempo, por eso son los más difíciles de diagnosticar, y mucha gente acaba pensando que la línea es mala.

## Lo que debería hacer el enrutamiento dividido

- Una web va por un solo camino junto con sus páginas, imágenes, vídeo e inicio de sesión, sin separarse
- Al decidir «china o extranjera» se coloca del lado correcto, y las webs chinas no dan rodeos
- Todos los dispositivos de la casa siguen las mismas reglas, y cambiar la configuración de red en el propio dispositivo no permite saltárselas
- El sentido cambia automáticamente con la región elegida (acceder a China desde el extranjero y acceder a servicios extranjeros desde China son dos juegos de reglas opuestos)
- La lista se actualiza sola, sin volver a instalar el firmware
- La configuración se guarda: no cambia tras reiniciar o reconectar; y si lo desactivas, no se vuelve a activar a escondidas

## El enrutamiento dividido inteligente de nuestro router

| | Cómo se hace |
|---|---|
| Interruptor | Activado por defecto; elegir una región de China = sentido de acceso a China desde el extranjero, elegir una región extranjera = sentido de acceso a servicios extranjeros desde China, y se aplica automáticamente. El sentido de acceso a servicios extranjeros desde China tiene además una casilla «Blocked sites only» (solo las webs bloqueadas van por la VPN) en «VPN settings» → enrutamiento dividido inteligente, marcada por defecto; desmarcada = webs chinas directas y todo lo demás por la VPN. El firmware instalado antes de octubre de 2026 todavía no muestra esta casilla; contacta con atención al cliente para que lo cambien a distancia |
| Lista | Organizada por «web completa»: las páginas van junto con las fuentes de vídeo, imágenes e inicio de sesión que usan |
| Acceso a servicios extranjeros desde China | Por defecto solo las webs y servicios bloqueados pasan por la VPN (según una lista de sitios bloqueados que se actualiza sola cada día, más servicios como Telegram que se conectan a direcciones fijas); las webs chinas y las extranjeras que ya cargan bien desde China (webs de empresas extranjeras, descargas de Apple y Microsoft, plataformas de juegos) conectan directamente, sin rodeos, a la misma velocidad que sin el router |
| Dispositivos de casa | Todos gestionados por igual; aunque cambies la configuración de red en el propio dispositivo, sigue las reglas; no hay «puerta trasera» para saltarse el router |
| Actualizaciones | La lista y las reglas se actualizan automáticamente al arrancar el router; la lista de sitios bloqueados también se actualiza sola cada día |
| Memoria | Se mantiene tras reconectar o reiniciar; si lo desactivas, se queda desactivado |
| Red local | A las impresoras, el NAS y las cámaras se accede directamente, como siempre |

**El único caso en que hace falta tu ayuda**: cuando un móvil o un navegador tiene activado un ajuste cifrado como «DNS privado» o «DNS seguro», el dispositivo cifra sus propias consultas y el router no puede verlas. Si un dispositivo se comporta raro, o las webs bloqueadas no cargan mientras todo lo demás funciona, desactiva primero ese tipo de ajuste.

## Compruébalo tú mismo

1. Estás en China (acceso a servicios extranjeros): Baidu y Taobao, y las webs extranjeras que ya cargan bien desde China, como las descargas de Apple y Microsoft, van a velocidad normal; las webs extranjeras bloqueadas cargan y el vídeo se reproduce.
2. Estás en el extranjero (acceso a China): elige cualquier episodio en Tencent Video o iQIYI y se reproduce, sin el mensaje «仅限中国大陆» (solo para China continental); las webs locales de bancos y de compras funcionan como siempre.
3. Prueba todos los dispositivos, sobre todo la tele y el TV box; si alguno se comporta raro, revisa primero «DNS privado / DNS seguro» y luego confirma que está conectado al wifi de este router y no al del módem.
4. Una web no carga con el enrutamiento dividido: cambia temporalmente a «Global». Si con Global carga y con el enrutamiento dividido no, es que aún no está en la lista; envía la dirección al servicio de atención al cliente para que la añadan, y llegará con la actualización automática. En China también puedes desmarcar «Blocked sites only» en la sección de enrutamiento dividido inteligente y volver a probar; si entonces carga, también está bloqueada pero aún no está en la lista.

## Preguntas frecuentes

**¿Tengo que activar yo el enrutamiento dividido inteligente?** No. Queda activado en cuanto inicias sesión con tu cuenta y eliges una región.

**¿Hay que configurar por separado el acceso a China desde el extranjero y el acceso a servicios extranjeros desde China?** No. El sentido lo decide automáticamente la región elegida.

**¿Afecta a las impresoras o al NAS?** No. A los dispositivos de la red de casa se accede directamente, como siempre.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-09) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-09) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
