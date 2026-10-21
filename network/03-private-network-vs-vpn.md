# 03 · En qué se diferencia la red Privada (Tailscale) de una VPN y cuándo usarla

> Versión web (más extensa): https://www.leotun.com/es/guides/tailscale-mesh?utm_source=github&utm_content=network-03

La sección de la red Privada usa Tailscale, una herramienta de red basada en WireGuard. LeoTun gestiona su propio servidor de control, y tú inicias sesión con tu cuenta de este sitio. No es lo mismo que las VPN «de conexión», como AnyConnect y OpenVPN.

## Tres diferencias

| | VPN de conexión (AnyConnect / OpenVPN / Hiddify) | Red Privada (Tailscale) |
|---|---|---|
| Conexión | Tocas «conectar» cada vez, y vuelves a conectar tras un corte | Inicias sesión una vez y se queda en línea; se recupera sola al cambiar de red |
| Salida | Una vez conectado, todo el tráfico pasa por la salida | La salida es opcional: sin ninguna seleccionada, el tráfico de internet sale por la red local y solo se cifra el tráfico entre los dispositivos de la red privada; solo cuando eliges la salida de una región equivale a una VPN |
| Acceso entre dispositivos | No hay | Los móviles, ordenadores y NAS de la misma cuenta se comunican directamente, sin redirección de puertos ni IP pública |

## Cuándo te conviene

- Tienes varios dispositivos y quieres configurarlos una vez y que se queden en línea para siempre.
- Tienes en casa un NAS, un ordenador o una cámara a los que quieres acceder desde fuera: inicia sesión en la red Privada en los dos extremos y conecta directamente por el nombre del dispositivo, como si estuvieras en la misma red local.
- Dispositivos que deben estar conectados mucho tiempo: no hay caducidad de sesión.

## Cuándo te conviene más otro método

- Solo quieres usarlo una vez, de forma puntual: importar Hiddify con el código QR o instalar AnyConnect es más rápido.
- El dispositivo ya ejecuta una VPN de empresa u otro software de red: se pelearán por el DNS y las rutas, y los síntomas son avisos de derechos de autor al ver vídeo chino y una intranet de empresa que no carga. Usa un método que solo afecte al navegador, como el Proxy Web.
- Redes de campus o de empresa que restringen UDP: WireGuard va sobre UDP y solo puede apoyarse en servidores de retransmisión, que son lentos; cambia a AnyConnect.

## Vencimiento y número de dispositivos

La validez del inicio de sesión de un dispositivo sigue la fecha de vencimiento de la cuenta; se desconecta a los pocos minutos de caducar, y basta con volver a iniciar sesión después de renovar. El número de dispositivos en línea a la vez depende del plan (Individual 2, Familiar 4, Empresa 8), y el cupo se comparte con los demás métodos de conexión; cuando los dispositivos en línea a la vez superan el límite del plan, puedes subir temporalmente de tipo de cuenta (el tiempo restante se convierte a valor equivalente según el precio) y volver cuando termines.

Para los pasos de instalación e inicio de sesión, consulta [Guía de clientes 05](../client/05-tailscale-private-network.md).

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=network-03) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=network-03) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
