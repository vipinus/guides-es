# 08 · Configura muchos dispositivos de una vez y cambia de móvil sin empezar de cero

Para quien tiene muchos dispositivos, lo más pesado es configurarlos uno a uno, repetirlo todo al cambiar de móvil y tocar «conectar» en cada aparato cuando sales de casa. La red privada elimina todo eso: cada dispositivo inicia sesión una vez con tu cuenta de este sitio y a partir de ahí se queda en línea, sin hacer nada tras un reinicio o un cambio de wifi; cada dispositivo elige su propia región de salida, así que el portátil puede usar Japón y el móvil la región de China sin afectarse entre sí; los dispositivos de la misma cuenta se ven entre ellos, así que un portátil fuera de casa puede abrir directamente las carpetas compartidas del NAS de casa. Un móvil nuevo solo tiene que iniciar sesión. Este artículo explica cómo meter todos los dispositivos de la casa, cómo se cuenta el cupo y qué hacer con el vencimiento y los cambios de dispositivo.

## Lo que haces una sola vez por dispositivo

1. Instala el cliente de Tailscale (Android, Windows, macOS y Linux desde la zona de descargas de la página de la red Privada de este sitio; iPhone / iPad desde el App Store, que exige un Apple ID de fuera de la región de China).
2. Si has iniciado sesión con una cuenta oficial de Tailscale, cierra sesión primero y luego apunta el inicio de sesión al servidor de control de este sitio (móvil: «⋯» en la pantalla sin sesión → Use custom server (usar servidor personalizado); ordenador: copia el comando de la página; macOS: Account Settings → Accounts → la flecha junto a «Add Account…» → Add Account Using Alternate Server (añadir cuenta con un servidor alternativo)).
3. Confirma en el navegador con tu cuenta de este sitio. A partir de ahí el dispositivo está en la red privada y no necesita más atención.
4. Elige una salida: cada dispositivo la elige en su propio menú, de forma independiente. Si no quieres salida, elige None (ninguna); así solo conservas el acceso entre dispositivos.

## Cómo se cuentan los dispositivos simultáneos

Una cuenta se puede instalar en todos los dispositivos que quieras; el único límite es cuántos están en línea a la vez: Individual 2, Familiar 4, Empresa 8, y ese cupo se comparte con Cisco, Hiddify y los demás métodos. Si superas el límite de tu plan, puedes subir temporalmente de tipo de cuenta (el tiempo restante se convierte a valor equivalente según el precio) y volver cuando termines.

Un router cuenta como un dispositivo, y los que hay detrás no cuentan. Un router o NAS en casa más el móvil y el portátil que llevas encima suele ser suficiente.

## Los dispositivos se ven entre sí

- Cada dispositivo de la misma cuenta tiene una dirección en la red privada y también se le puede llamar por su nombre, sin necesidad de IP pública ni redirección de puertos.
- Abrir una carpeta compartida del NAS de casa desde un portátil fuera de casa, ver la grabadora de vídeo de casa desde el móvil o usar el escritorio remoto con el ordenador de casa: todo conecta directamente con las direcciones de la red privada.
- Un router doméstico con el firmware de este sitio puede compartir toda la red local con la red privada, así que los dispositivos que no pueden ejecutar un cliente, como impresoras y televisores, también son accesibles desde fuera.
- Los dispositivos de otros clientes no aparecen en absoluto en tu red privada; no es que simplemente no los veas.

## Vencimiento, cambio de dispositivo, desinstalación

- Vencimiento de la cuenta: todos los dispositivos se desconectan en pocos minutos; tras renovar, inicia sesión una vez más en cada uno, y la configuración de salida se conserva.
- Cambio de móvil: inicia sesión en el móvil nuevo siguiendo los pasos de arriba; si te dice que has alcanzado el límite, cierra sesión en el móvil antiguo o sube temporalmente de tipo de cuenta y vuelve cuando termines.
- Si no quieres que un dispositivo siga en la red privada: cierra sesión en el cliente; para desconectar un dispositivo a la fuerza, contacta con soporte.
- No ejecutes otra VPN en el mismo dispositivo a la vez (el cliente Cisco de la empresa, otro software de red mallada): se pelearán por el DNS y las rutas.

## Preguntas frecuentes

**¿Cada dispositivo puede elegir una región de salida distinta?** Sí, cada uno elige su propia salida. El portátil puede usar Japón para ver vídeo mientras el móvil usa la región de China para la banca en línea, sin afectarse entre sí.

**¿Dejar la red privada siempre activada gasta batería?** Sin salida seleccionada casi no hay tráfico; solo se usa al comunicarse con dispositivos de la red privada. El gasto de batería es comparable al de la VPN del sistema.

**¿Cómo la instalo en un NAS de casa?** Synology y QNAP tienen un paquete de Tailscale, y en los sistemas Linux se usa el script de instalación oficial; al iniciar sesión, apúntalo al servidor de control de este sitio de la misma manera. Un router con el firmware de este sitio no necesita instalarlo: inicia sesión con tu cuenta y ya está en la red privada.

**¿Por qué no configurar Cisco en todos los dispositivos?** Se puede, pero con Cisco tienes que tocar «conectar» cada vez, volver a conectar tras un corte y cambiar la dirección para cambiar de salida; con muchos dispositivos, la red privada da muchísimo menos trabajo. La excepción es un dispositivo en una red de campus que restringe UDP; en ese, usa Cisco.

## Para seguir leyendo

- [Página de la red Privada: descarga y pasos para iniciar sesión](https://www.leotun.com/es/mesh?utm_source=github&utm_content=client-08)
- [Qué es la red privada (Tailscale)](https://www.leotun.com/es/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Ver desde el extranjero tus cámaras y tu NAS en China](https://www.leotun.com/es/guides/home-camera?utm_source=github&utm_content=client-08)
- [Qué puede hacer el firmware del router](https://www.leotun.com/es/guides/router-firmware?utm_source=github&utm_content=client-08)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/multi-device?utm_source=github&utm_content=client-08

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-08) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-08) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
