# 04 · Hiddify importado pero no conecta

> Versión web (más extensa): https://www.leotun.com/es/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Busca tu error en la tabla. Para saber cómo importar desde el principio, consulta [Cómo importar un enlace de suscripción (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md).

| Síntoma | Causa | Qué hacer |
|---|---|---|
| «Unable to fetch subscription» (no se pudo obtener la suscripción), 401 | La cuenta ha caducado o se cambió la contraseña (cambiar la contraseña invalida al instante las configuraciones antiguas; es así a propósito) | Inicia sesión en la web y comprueba la fecha de validez; tras renovar o cambiar la contraseña, vuelve a escanear el código QR |
| Se importa bien, pero la conexión agota el tiempo de espera | Acaban de cambiar la dirección de esa región, o el operador está interfiriendo con ese punto de entrada | Toca «Update subscription» (actualizar suscripción) en el cliente para descargar la configuración más reciente; cambia a otra región: cada región es una configuración aparte y no se afectan entre sí |
| Conectado pero sin internet | Las reglas de enrutamiento propias del cliente mandan el tráfico a «direct» (directo) | Cambia la salida por defecto a ese nodo o borra las reglas que añadiste tú |
| Al escanear sale «Invalid QR code» (QR no válido) | Al abrir la ventana, el QR que aparece primero es el de Hiddify / sing-box, y otros clientes que lo escanean directamente dan este error; o lo escaneaste de una captura de otra persona | Haz clic primero en el botón de tu cliente, que cambia el QR al tipo correspondiente, y luego escanea o pega: los clientes de la familia Clash pulsan «Suscripción Clash»; Shadowrocket / NekoBox / v2rayN, etc., pulsan «Enlace para compartir». El QR contiene tus propias credenciales, y el de otra persona no te servirá |
| Velocidad lenta | La región elegida tiene mucha carga, o tu banda ancha local no casa bien con esa región | Mira las luces roja, amarilla y verde en la lista de regiones de la web y cambia a una región en verde; si sigue lento, cambia de región según tu operador |
| Un cliente de la familia Clash no consigue importar el enlace para compartir | Clash Meta, Clash Verge, FlClash, Stash y similares no pueden importar una sola línea hysteria2:// como perfil | Pulsa el botón «Suscripción Clash» y pega la URL en la lista de suscripciones del cliente; el Clash original y Clash for Windows no tienen hysteria2 en su núcleo, así que usa un cliente con núcleo mihomo |
| El enlace para compartir no se importa o no conecta | El enlace usa un formato ampliado que unos pocos clientes no saben interpretar | Cambia a Hiddify |

## ¿Tengo que volver a importar tras renovar, cambiar de plan o cambiar la contraseña?

- **Renovar o cambiar de plan (Individual / Familiar / Empresa)**: No. La configuración que tienes sigue funcionando.
- **Cambiar la contraseña**: La configuración antigua deja de funcionar al instante; vuelve a escanear el QR. Si pierdes el móvil o se filtra el enlace, usa esto para revocar el acceso.
- **Cuenta caducada**: La configuración devuelve 401. Tras renovar no necesitas una configuración nueva; basta con volver a conectar.
- **Importada antes de septiembre de 2026**: Le falta la regla que rechaza IPv6, así que al ver vídeo chino desde el extranjero te saldrá un aviso de restricción por derechos de autor. Bórrala y vuelve a importarla; consulta la [03](03-ipv6-and-dns-leak.md).

## Cuándo contactar con soporte

Dile a soporte tres cosas: el nombre y la versión del cliente, la región y el texto exacto del error o una captura de pantalla.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-04) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-04) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
