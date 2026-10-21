# 03 · Qué es el enrutamiento dividido en el router

> Versión web (más extensa): https://www.leotun.com/es/guides/router-firmware?utm_source=github&utm_content=router-03

## En una frase

Configura la VPN en el router y todos los dispositivos de la casa pasarán por ella automáticamente en cuanto se conecten al wifi. Los dispositivos que no pueden instalar un cliente, como decodificadores, consolas e impresoras, también pueden usarla.

## Qué problema resuelve el enrutamiento dividido

Si todo el tráfico pasa por la VPN, te encuentras con dos problemas: las webs locales van lentas (dan un rodeo) y los dispositivos locales dejan de estar accesibles (la impresora, el NAS y la página de administración del router están en la red local, pero el tráfico se ha enviado fuera).

El enrutamiento dividido funciona dándole al router una lista: los dominios de la lista pasan por la VPN y todo lo demás conecta directamente. En qué sentido depende de dónde estás y a qué lado quieres llegar, y lo decide automáticamente la región que eliges:

- **En el extranjero, con la región de China elegida (acceso a China)**: las webs y apps chinas pasan por la VPN, y todo lo demás conecta directamente.
- **En China, con una región extranjera elegida (acceso a servicios del extranjero)**: por defecto solo las webs y servicios bloqueados pasan por la VPN; las webs chinas y las extranjeras que ya cargan bien desde China (webs de empresas extranjeras, descargas de Apple y Microsoft, plataformas de juegos y similares) conectan directamente, sin rodeos, tan rápido como sin el router.

## Tres modos

| Modo | Por dónde va el tráfico | Cuándo usarlo |
|---|---|---|
| Global | Todo pasa por la VPN | Temporalmente, al diagnosticar problemas |
| Split routing (dividido) | Los dominios de la lista pasan por la VPN y el resto conecta directamente | En el día a día |
| Direct (directo) | Nada pasa por la VPN | Cuando no la necesitas durante un tiempo |

## Acceso a servicios del extranjero desde China: solo las webs bloqueadas

Desde el 14 de octubre de 2026, en el sentido de acceso a servicios del extranjero desde China, el enrutamiento dividido solo envía por la VPN, por defecto, las webs y servicios bloqueados. Se basa en una lista de sitios bloqueados que se actualiza sola cada día, más servicios como Telegram que se conectan a direcciones fijas sin consultar el nombre de un sitio. Las webs que ya cargan bien desde China, chinas o extranjeras, conectan directamente.

El interruptor está en la página de administración del router, en «VPN settings» (ajustes de VPN), en la sección de enrutamiento dividido inteligente: la casilla «Blocked sites only» (solo las webs bloqueadas van por la VPN), marcada por defecto. Desmárcala para volver al comportamiento anterior: webs chinas directas y todo lo demás por la VPN.

El firmware instalado antes de octubre de 2026 todavía no muestra esta casilla; el nuevo comportamiento predeterminado ya se aplica a esos routers mediante las actualizaciones automáticas. Para cambiarlo, contacta con atención al cliente, que puede hacerlo a distancia.

El sentido de acceso a China desde el extranjero no cambia.

## Trampas habituales

- **Una web no abre con el enrutamiento dividido**: comprueba primero si está en la lista. Las webs que no están en la lista conectan directamente, y si esa web ya no abría de por sí, el enrutamiento dividido no ayudará. Cambia temporalmente a «Global» para comprobarlo.
- **En China, una web extranjera no abre**: desmarca «Blocked sites only» en la sección de enrutamiento dividido inteligente (o cambia temporalmente a «Global») y vuelve a probar. Si entonces abre, la web está bloqueada pero aún no está en la lista; envía la dirección a atención al cliente.
- **Las webs bloqueadas no abren, pero todo lo demás funciona**: lo más probable es que el dispositivo tenga activado un ajuste de DNS cifrado («DNS privado» en Android, «DNS seguro» en el navegador), así que el router no puede ver qué sitio está consultando. Desactiva ese ajuste.
- **La impresora o el NAS no son accesibles tras conectar**: eso significa que las direcciones de la red local también se están enviando fuera. Comprueba si las reglas de enrutamiento dividido excluyen los rangos privados, como 192.168.x.x.
- **El rendimiento del router** marca el techo. El procesador de un router antiguo se satura con el tráfico cifrado, y se nota en que toda la casa va más lenta. En ese caso, el problema no es la línea de la VPN.

## Una cuenta, un router

La mayoría de los servicios vinculan el router a la cuenta (por dirección MAC). Cada cuenta se vincula a un router, y al cambiar de router primero se desvincula. Así la cuenta queda solo para ti.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-03) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-03) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
