# 08 · Con el firmware instalado: qué hace solo y los pocos interruptores que conviene conocer

> Versión web (más extensa): https://www.leotun.com/es/guides/router-firmware?utm_source=github&utm_content=router-08

Tras instalar el firmware de este sitio o comprar un equipo ya preparado, lo único que tienes que hacer es iniciar sesión con tu cuenta en la página de administración. Este artículo trata de lo que el firmware **hace por su cuenta** y de los pocos interruptores que quizá tengas que tocar; para empezar, consulta la [01](01-plug-and-play-router.md); para el enrutamiento dividido, la [03](03-router-split-routing.md), y para vincular y sustituir un router, la [05](05-mac-binding-and-replacing.md).

## Lo que hace por su cuenta

| Qué | Cómo funciona | Qué tienes que hacer tú |
|---|---|---|
| Actualizaciones de componentes y de la lista de enrutamiento dividido | Comprueba al arrancar y descarga cualquier actualización, que **se aplica en el siguiente arranque**; la lista de sitios bloqueados que se usa para acceder a servicios extranjeros desde China también se actualiza sola cada día | Nada; los cambios de dirección de las líneas y las webs añadidas a la lista se recogen automáticamente |
| Código de país del wifi | Detecta el país en el que está al conectarse a internet y ajusta automáticamente la potencia inalámbrica y los canales | Justo después de instalarlo, **conecta primero un cable de red** para que se conecte a internet una vez; es normal que la señal sea más débil antes de eso |
| Gestión del vencimiento | Cuando la cuenta caduca deja de pasar por la VPN; la red local sigue funcionando con normalidad | Se recupera solo al renovar, sin volver a iniciar sesión |
| Vinculación del router | El primer inicio de sesión registra este router en la cuenta | Desvincúlalo en la web antes de cambiar de router |

Solo una actualización de versión mayor de todo el firmware exige instalar el archivo sysupgrade. Ocurre pocas veces al año, y la web te avisará.

## Lo que quizá tengas que tocar

- **Modo de enrutamiento**: Split routing (dividido, predeterminado) / Global (todo por la VPN) / Direct (directo). Si una web no carga, cambia primero a Global para comprobarlo: si con Global carga, es que no está en la lista, así que pasa la dirección al servicio de atención al cliente para que la añadan; si tampoco carga con Global, el problema es de la propia web.
- **Región**: se elige en la página de administración. Elige la región de China para ver contenido chino desde el extranjero, y una región extranjera para acceder a servicios extranjeros desde China.
- **Blocked sites only** (solo las webs bloqueadas van por la VPN): una casilla en «VPN settings» (ajustes de VPN), en la sección de enrutamiento dividido inteligente, marcada por defecto. Solo se aplica al sentido de acceso a servicios extranjeros desde China (estás en China y elegiste una región extranjera). Marcada, solo las webs y servicios bloqueados pasan por la VPN (según una lista de sitios bloqueados que se actualiza sola cada día, más servicios como Telegram que se conectan a direcciones fijas); las webs chinas y las extranjeras que ya cargan bien desde China (webs de empresas extranjeras, descargas de Apple y Microsoft, plataformas de juegos y similares) conectan directamente, sin rodeos. Desmárcala para volver al comportamiento anterior: webs chinas directas y todo lo demás por la VPN. Si estando en China una web extranjera no carga, desmárcala (o cambia temporalmente a Global) y vuelve a probar; si entonces carga, la web está bloqueada pero aún no está en la lista, así que envía la dirección al servicio de atención al cliente. El firmware instalado antes de octubre de 2026 todavía no muestra esta casilla (el nuevo comportamiento predeterminado ya se aplica mediante las actualizaciones automáticas); para cambiarlo, contacta con atención al cliente, que puede hacerlo a distancia. El sentido de acceso a China desde el extranjero no se ve afectado por este interruptor.
- **Seleccionar automáticamente la línea más rápida**: está debajo de la región, desactivada por defecto, y se recomienda cuando la calidad de la red es mala.

  | | Desactivada (predeterminado) | Activada |
  |---|---|---|
  | Qué línea se usa | Siempre la región que elegiste | Elige automáticamente, entre las líneas disponibles, la de menor latencia y poca pérdida de paquetes; luego vuelve a medir periódicamente y cambia sola si empeora |
  | País de salida | La región elegida | Con la región de China elegida: solo elige entre líneas de China, y la salida sigue en China; con una región extranjera elegida: elige entre todas las líneas extranjeras, y **el país de salida puede ser distinto de la región elegida** (por ejemplo, elegiste Japón pero en realidad sales por Singapur) |
  | Para qué sirve | Situaciones que necesitan un país fijo: ver los servicios de streaming de un país concreto, bancos y cuentas sensibles a la región | Una red doméstica inestable o una región que se atasca a menudo, cuando solo quieres velocidad y te da igual por qué país sales |

  Al accionar el interruptor, la página de administración muestra un aviso de que se está cambiando la selección automática y bloquea la página hasta que termina. La red se corta brevemente durante ese tiempo; es normal. El apartado de salida actual de la página de administración muestra qué línea se está usando realmente.
- **Contraseña de administración y contraseña del wifi**: los valores de fábrica son predeterminados y públicos; cámbialos nada más iniciar sesión.

## Teles, TV box y dispositivos de los mayores de la familia

- Basta con conectarlos al wifi de este router o por cable, y la edición para China continental de una app se reproduce enseguida; las ediciones internacionales (iQIYI, WeTV) tienen otro catálogo, así que instala la edición para China continental.
- Un dispositivo está conectado pero no pasa por la VPN, o las webs bloqueadas no cargan mientras todo lo demás funciona: lo más probable es que tenga configurado su propio DNS privado («DNS privado» de Android, el DNS seguro del navegador), así que el router no puede ver qué sitio está buscando; desactívalo.
- Quieres que un dispositivo conecte siempre directamente (un ordenador del trabajo que tiene que conectarse a la VPN de la empresa): conéctalo al wifi del router de arriba o del módem.

## Preguntas frecuentes

**¿El plan Individual puede usar un router?** Sí. Individual, Familiar y Empresa admiten router, sin necesidad de cambiar de plan.

**¿Cuántas plazas de dispositivo ocupa el router?** Una; los dispositivos que hay detrás no cuentan.

**¿El firmware tiene alguna puerta trasera?** Está compilado a partir de OpenWrt, con solo el componente que se conecta a la VPN y las reglas de enrutamiento dividido añadidos; la VPN solo registra la duración de la conexión y el tráfico total, para la facturación.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-08) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-08) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
