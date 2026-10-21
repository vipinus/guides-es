# 03 · Conectado, pero la web de vídeo sigue mostrando el aviso de derechos: IPv6 y DNS son los que se escapan

> Versión web (más extensa): https://www.leotun.com/es/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

Ya pasaste el paso 1 de [02 · Conectado para acceder a China pero sigo sin poder ver nada](02-still-blocked-after-connecting.md) —la IP de salida aparece como de China continental—, pero la web sigue diciendo «no se puede reproducir por restricciones de derechos de autor». Nueve de cada diez veces todavía queda en el dispositivo un camino que no pasa por la VPN: **IPv6** o **DNS**. Una web de vídeo decide de dónde eres según la dirección que ve, y mientras se escape un solo camino, lo que ve sigue siendo extranjero.

## Por qué hay fugas

- Los dispositivos actuales tienen dirección IPv4 e IPv6, y los navegadores prefieren IPv6. Si la VPN solo se encarga de IPv4, las peticiones IPv6 salen directamente por la banda ancha de casa.
- El «DNS seguro» integrado en el navegador, el «DNS privado» de Android u otra herramienta de red mallada que tengas en marcha (Tailscale y similares) se adelantan a la VPN y se quedan con la resolución de nombres.

«Conectado» solo significa que el túnel está establecido. No significa que todo el tráfico pase por él.

## Comprobación en cinco pasos

1. **Comprueba IPv6.** Tras conectar, busca «test ipv6» y abre una página de prueba. Si el campo IPv6 muestra una dirección del país donde estás → el problema está aquí, ve al paso 2. Si ambos campos muestran China continental, o IPv6 no está disponible → ve al paso 3.
2. **Desactiva IPv6 o cambia a un cliente que bloquee IPv6.** Windows: en las propiedades del adaptador de red, desmarca «Protocolo de Internet versión 6 (TCP/IPv6)». macOS: Ajustes de red → TCP/IP → pon «Configurar IPv6» en «Solo enlace local». Móvil: desactiva el wifi y prueba una vez con datos móviles; la banda ancha de casa suele tener IPv6, mientras que los datos móviles del operador a menudo no.
3. **Comprueba el DNS.** Configuración de Chrome → Privacidad y seguridad → desactiva «Usar DNS seguro»; en Android desactiva «DNS privado»; cierra otras VPN, herramientas de red mallada y extensiones de proxy.
4. **Cierra la app del todo y vuelve a abrirla; en la versión web, borra los datos del sitio.** Las plataformas guardan en caché la comprobación de región anterior.
5. **Cambia a otro punto de entrada y vuelve a probar.** Puede que la plataforma acabe de marcar la dirección de una salida concreta.

## Cómo lo resuelve LeoTun

Desde septiembre de 2026, los tres métodos de conexión de LeoTun (Hiddify, Cisco AnyConnect, OpenVPN) rechazan IPv6 directamente dentro del túnel y envían una configuración de DNS que obliga a resolver dentro del túnel, sin que tengas que cambiar nada en tu dispositivo. **Las configuraciones de Hiddify importadas antes de septiembre no tienen esta regla. Bórralas y escanea el código QR para importarlas de nuevo.**

Con la opción del router no hay fugas desde el principio: toda la red local sale por el router, así que el IPv6 y el DNS de los dispositivos nunca llegan al exterior.

## Casos en los que sigue saliendo el aviso

| Caso | Síntoma | Solución |
|---|---|---|
| La salida no es de China continental | La consulta de IP muestra Hong Kong / Taiwán / Japón | Cambia a un punto de entrada de China; para Tencent e iQIYI, las direcciones de Hong Kong y Taiwán también cuentan como extranjeras |
| Reglas de enrutamiento personalizadas mandan los dominios de vídeo a «direct» (directo) | Las páginas cargan, pero los vídeos no se reproducen | Haz que los dominios chinos pasen por el nodo; si estás fuera de China no actives «direct for China» (directo para China) |
| Estás usando el proxy web | Funciona en el navegador, no en las apps | Para ver vídeo hace falta un túnel para todo el dispositivo; el proxy web solo cubre el navegador |

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-03) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-03) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
