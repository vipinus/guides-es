# 07 · ¿Te conviene un router? Cómo elegir entre los cuatro modelos

> Versión web (más extensa): https://www.leotun.com/es/guides/router?utm_source=github&utm_content=router-07

El router resuelve el problema de «demasiados dispositivos, y algunos no admiten un cliente»: la VPN se configura una sola vez en el router, y la tele, la consola, el altavoz inteligente y el móvil de los mayores de la familia pasan por ella automáticamente, sin instalar nada. Solo hace falta un router en el que se pueda instalar firmware y diez minutos para instalarlo. **Las cuentas Individual, Familiar y Empresa pueden usar router.**

## Cuándo te conviene y cuándo no

| Te conviene | No te conviene |
|---|---|
| Tienes en casa dispositivos que no admiten un cliente, como un TV box, una consola, un Apple TV o un altavoz inteligente | Solo tienes un móvil y un ordenador y sobre todo viajas por trabajo: instalar un cliente es más ligero |
| La familia es numerosa y no quieres enseñar a cada uno con su dispositivo | Vives en una residencia o en un piso compartido y no controlas la red |
| Tienes dispositivos que deben estar conectados las 4 horas (NAS, cámaras que suben grabaciones) | Tu router principal es un módem bloqueado por el operador y no puedes conectar un segundo router: un router de viaje es una solución intermedia |
| Una oficina en China o una familia entera que accede de forma estable a servicios extranjeros desde China, con enrutamiento dividido en el router y sin que los dispositivos noten nada | |

## Instalar el firmware o comprar un equipo ya preparado

Por los dos caminos acabas con el mismo firmware. La diferencia está en quién lo instala y quién responde si algo falla.

- **Instalarlo tú**: ya tienes un router compatible con OpenWrt (más de 1000 modelos). El firmware se compila en línea en la web y recibes el enlace por correo en 3 a 5 minutos; después sigue paso a paso [02 · Instalar el firmware tú mismo](02-flash-firmware-yourself.md) (tiene vídeo). Para quien se maneja bien con la configuración técnica y quiere ahorrarse el coste del equipo.
- **Comprar un equipo ya preparado**: enviamos un GL.iNet con el firmware ya instalado; para los tres pasos al sacarlo de la caja, consulta la [01](01-plug-and-play-router.md). Para quien no quiere complicarse, o para regalárselo a familiares que no son técnicos.

Por cualquiera de los dos caminos, el firmware actualiza sus componentes solo, sin tener que volver a instalarlo, y cuando cambian las direcciones de las líneas tampoco tienes que tocar la configuración.

## Cuatro routers, según cómo los vayas a usar

| Modelo | Tipo | Precio | Incluye | Qué es | Ideal para |
|---|---|---|---|---|---|
| GL-MT300N-V2 | Mini | 200 USD | 12 meses de servicio | Cabe en la palma de la mano y se alimenta por USB (funciona con una batería externa); solo wifi de 2,4 GHz, puertos de 100 Mbps | Una persona de viaje: cable de red o wifi del hotel, un móvil y un portátil para navegar y ver vídeo en 1080p. No sirve como router principal de casa |
| **GL-MT3000** | De viaje | 300 USD | 24 meses de servicio | Wi‑Fi 6 de doble banda con puerto de 2,5G, algo más grande que la palma de la mano | Router principal de un hogar pequeño (tele, TV box, varios móviles y ordenadores) y lo bastante pequeño para llevarlo en la mochila |
| GL-MT6000 | De sobremesa | 400 USD | 24 meses de servicio | Dos puertos de 2,5G más cuatro gigabit, antenas externas, la mayor potencia de procesamiento | Casas grandes, muchos dispositivos (una docena o más), banda ancha de más de un gigabit, 4K y consolas, o una oficina pequeña. Se queda fijo como único router |
| GL-XE3000 | Móvil | 400 USD | 24 meses de servicio | 5G/4G y batería integrados; con una SIM es una red independiente, y también admite cable de red | Sitios sin banda ancha fija: autocaravanas, obras, ferias, alquileres cortos; o como respaldo de la línea de casa |

Los meses incluidos son del plan Individual; en Familiar son la mitad y en Empresa la cuarta parte, el mismo valor en todos los casos. Envío gratis a todo el mundo, normalmente en 3–14 días, y devolución en 30 días.

### Elección rápida según tu caso

- Viajas solo, duermes en hoteles y tienes un presupuesto ajustado → GL-MT300N-V2
- Un piso o un hogar pequeño donde la tele y el TV box necesitan vídeo chino o extranjero → GL-MT3000
- Sobre todo en casa, pero quieres llevártelo en algún viaje → GL-MT3000
- Una casa grande, muchos dispositivos, banda ancha de más de un gigabit o una oficina compartida → GL-MT6000
- Sin banda ancha, o pasas casi todo el tiempo en la carretera → GL-XE3000
- Para unos padres que no son técnicos → GL-MT3000, comprado ya preparado: se enchufa y funciona

## Por qué el GL-MT3000 es nuestra primera recomendación

- **Un equipo, dos papeles.** Tiene potencia de sobra para ser el router principal de un hogar pequeño y es lo bastante pequeño para viajar con él. Es el único de los cuatro que hace las dos cosas.
- **No se quedará anticuado pronto.** El Wi‑Fi 6 y el puerto de 2,5G dejan margen frente a la mayoría de las bandas anchas domésticas. El mini solo tiene wifi de 2,4 GHz y puertos de 100 Mbps, que en casa se convierten en el cuello de botella.
- **Las cuentas salen.** 300 USD con 24 meses de servicio del plan Individual, frente a 200 USD con 12 meses del mini. Contando el servicio incluido, los 100 USD de más te dan un equipo claramente mejor y un año extra.
- **Es el que mejor conocemos.** Nuestro equipo de pruebas es este modelo, el firmware nuevo se comprueba primero en él y el [vídeo tutorial de instalación](02-flash-firmware-yourself.md) lo usa. Si tienes un problema, tenemos el mismo equipo sobre la mesa para comparar.

Cuándo no elegirlo: para una casa grande, muchos dispositivos o banda ancha de más de un gigabit, ve directamente al GL-MT6000; sin banda ancha fija, el GL-XE3000; si es solo para una persona de viaje y lo que más importa es el precio, basta con el GL-MT300N-V2.

## Los tres problemas más habituales al empezar

- **Señal wifi débil, solo 20 dBm**: el firmware ajusta automáticamente la potencia inalámbrica según la normativa del país en el que estás, y solo pasa al nivel de tu país después de que el router se haya conectado a internet una vez. Justo después de instalarlo, conecta primero un cable de red.
- **Las webs chinas van lentas** (estando en China): el enrutamiento dividido está desactivado y todo pasa por la línea. Vuelve a poner el modo en enrutamiento dividido: al acceder a servicios extranjeros desde China, por defecto solo las webs bloqueadas usan la línea, y las webs chinas y las extranjeras que ya cargan bien desde China van directas.
- **En China, una web extranjera no carga**: en «VPN settings» (ajustes de VPN), en la sección de enrutamiento dividido inteligente, desmarca «Blocked sites only» (solo las webs bloqueadas van por la VPN), o cambia temporalmente a «Global», y vuelve a probar; si entonces carga, la web está bloqueada pero aún no está en la lista, así que envía la dirección al servicio de atención al cliente.
- **Estás fuera de China y quieres contenido chino**: elige Reverse Split (enrutamiento dividido inverso). El modo inverso da la vuelta al sentido: solo las IP de China continental pasan por la línea de vuelta a China, y todas las demás webs usan directamente tu banda ancha local. El vídeo, la música y las apps chinas ven una dirección china, mientras que las webs y el streaming locales no dan ningún rodeo. El firmware elige el sentido según dónde está el router, así que rara vez tendrás que cambiarlo. Consulta [03 · Enrutamiento dividido en el router](03-router-split-routing.md).
- **Un dispositivo no pasa por la VPN, o las webs bloqueadas no cargan mientras todo lo demás funciona**: ese dispositivo tiene configurado su propio DNS privado («DNS privado» de Android, el DNS seguro del navegador), así que el router no puede ver qué sitio está buscando; desactívalo.

## Preguntas frecuentes

**¿El router cuenta como un dispositivo?** Ocupa una plaza de la cuenta (según el plan: Individual 2, Familiar 4, Empresa 8 dispositivos en línea a la vez), y los dispositivos que hay detrás no cuentan por separado.

**¿Sirve para ver vídeo de China estando en el extranjero?** Sí, elige la región de China para la línea. El router mete toda la red local en la VPN, y el IPv6 y el DNS de los dispositivos no pueden salir por fuera, así que los avisos de «restricción por derechos de autor» aparecen menos que cuando un móvil se conecta por su cuenta. Consulta la [06](06-unlock-chinese-video-with-router.md).

**¿El firmware tiene una puerta trasera?** Se compila a partir de OpenWrt, añadiendo solo el componente que se conecta a la VPN y las reglas de enrutamiento dividido; la VPN solo registra la duración de la conexión y el tráfico total para la facturación, y no registra lo que visitas.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-07) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-07) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
