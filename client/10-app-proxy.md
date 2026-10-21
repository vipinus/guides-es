# 10 · Qué hacer cuando Dropbox u otros programas piden un proxy HTTP / SOCKS

> Versión web (más extensa): https://www.leotun.com/es/guides/app-proxy?utm_source=github&utm_content=client-10

**Primero, cómo están las cosas: un proxy tiene que ir cifrado.** Los proxies sin cifrar (HTTP simple, SOCKS4, SOCKS5) se detectan y se interfieren en las redes de China; al poco tiempo la conexión se vuelve lenta o se corta, y además la cuenta y la contraseña viajan en texto plano. Solo las conexiones cifradas siguen funcionando a largo plazo, por eso el proxy web de este sitio usa siempre conexiones cifradas; **para los programas que solo aceptan HTTP / SOCKS5, deja que Hiddify se encargue de todo el equipo** (lo verás más abajo).

Los programas independientes como Dropbox, Telegram Desktop, Steam, los clientes de almacenamiento en la nube y las herramientas de desarrollo no leen la configuración del navegador, y sus propios ajustes de proxy solo aceptan HTTP / SOCKS5 sin cifrar. Las dos partes no encajan, así que poner un proxy no basta para que conecten. La solución es **no poner ningún proxy**: usa Hiddify para que todo el ordenador pase por la línea y deja el proxy del programa en «Sin proxy».

## Por qué sigue sin conectar después de poner un proxy

| Causa | Explicación |
|---|---|
| El tipo no coincide | El programa solo ofrece HTTP, SOCKS4 y SOCKS5, ninguno cifrado; el proxy de este sitio tiene que ir cifrado y no se puede introducir ahí |
| Un proxy sin cifrar sacado de internet | Conecta durante un tiempo, luego sufre interferencias y funciona a ratos |
| Solo cubre parte del tráfico | En muchos programas solo el inicio de sesión y la sincronización usan el proxy, mientras que las actualizaciones, las llamadas y la sincronización por LAN siguen conectando directamente; un proxy HTTP no reenvía en absoluto el tráfico UDP de juegos y llamadas |
| Hay que mantenerlo en cada programa por separado | Cambiar de región o de contraseña obliga a cambiarlos uno por uno, y el que se te olvide deja de funcionar |

## Lo recomendado: que Hiddify se encargue de todo el equipo

1. Instala Hiddify siguiendo [09 · Instalar Hiddify en todas las plataformas](09-hiddify-install-all-platforms.md) e importa un perfil siguiendo la [02](02-singbox-subscription-links.md).
2. Conéctate en modo «VPN» (el predeterminado). En Windows, la primera conexión necesita permisos de administrador.
3. Devuelve el proxy del programa a «Sin proxy»: en Dropbox, elige «Sin proxy» o «Detectar automáticamente» en «Preferencias → Red → Proxies»; en Telegram Desktop, elige «Desactivar proxy» en «Ajustes → Avanzado → Tipo de conexión». En cualquier otro programa que tenga opción de proxy, desactívala.
4. Comprueba: el icono de Dropbox en la bandeja muestra «Actualizado» y empieza la sincronización; abre en el navegador una web que muestre tu IP y verás que la salida está en la región que elegiste.

Con el «enrutamiento automático» activado, los servicios extranjeros como Dropbox pasan por la línea, mientras que WeChat, la banca en línea y las webs chinas conectan directamente como siempre.

## Programas habituales

| Programa | Cómo configurarlo |
|---|---|
| Dropbox | Proxy en «Sin proxy» o «Detectar automáticamente»; si lo dejas en «Manual» con otra dirección, se queda sin conexión en cuanto apagas Hiddify |
| Telegram Desktop | Tipo de conexión «Desactivar proxy»; el MTProto / SOCKS5 integrado, puesto encima del túnel, solo lo hace más lento |
| OneDrive, Google Drive, iCloud para escritorio | Siguen la red del sistema; no hay nada que configurar |
| Steam, Epic, Battle.net | No necesitan proxy; si las descargas van lentas, cambia a una región más cercana |
| Zoom, Teams, Slack, Discord | La voz y el vídeo van por UDP, y eso solo lo transporta un método que cubra todo el equipo |
| VS Code, JetBrains, Cursor | Siguen la red del sistema; borra cualquier proxy configurado aparte dentro de la herramienta |

## Cuando no puedes instalar un cliente (ordenador de la empresa)

- Usa la versión web de Dropbox y de las nubes: abre dropbox.com en un navegador con el [proxy web](03-web-proxy-extension.md); puedes subir y descargar, pero no hay sincronización automática.
- Las herramientas de línea de comandos (git, pip, npm, curl) aceptan un proxy cifrado: pon la dirección del proxy web en `https_proxy`; consulta [Acceder a servicios del extranjero desde China 05 · Linux y la línea de comandos](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (en chino).
- Los demás programas de escritorio que solo aceptan HTTP / SOCKS5 es mejor usarlos en tu propio ordenador o móvil; no instales una VPN para todo el equipo en un ordenador de la empresa solo por esto, porque saltarán las alertas de seguridad de la empresa.

## Preguntas frecuentes

**¿Me pueden dar una dirección de proxy SOCKS5 o HTTP?** El proxy de este sitio usa siempre conexiones cifradas; uno sin cifrar empieza a funcionar a ratos en poco tiempo. Dejar que Hiddify se encargue de todo el equipo es más estable y cubre todos los programas a la vez.

**Con Hiddify activado, ¿tengo que poner también un proxy en el programa?** No. Ponerlo significa dar dos vueltas: en el mejor caso va más lento; en el peor, no conecta.

**¿Y Dropbox en el móvil?** Las apps del móvil no tienen ajustes de proxy. Instala Hiddify o usa Cisco (AnyConnect); una vez conectado, todas las apps pasan por la línea.

**¿Puedo prescindir de Hiddify?** Sí. Cisco, la red Privada y OpenVPN también cubren todo el equipo, y en el programa se deja igualmente «Sin proxy». La ventaja de Hiddify es el enrutamiento integrado y una mejor velocidad en redes con mucha pérdida de paquetes.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-10) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-10) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
