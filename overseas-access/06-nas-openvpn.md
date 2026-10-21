# 06 · Cómo hacer que un NAS Synology o QNAP pase por la línea

El NAS es el dispositivo de casa que más necesita la línea y al que menos atención se presta: el gestor de descargas tiene que llegar a recursos extranjeros, Docker tiene que descargar imágenes, Cloud Sync tiene que sincronizar nubes extranjeras y Plex tiene que obtener metadatos. Un NAS no puede ejecutar Hiddify, pero tanto Synology como QNAP traen un cliente OpenVPN integrado: descargas un .ovpn desde la página de OpenVPN de este sitio, lo importas y conecta, y se vuelve a conectar solo al arrancar. Este artículo explica dónde está la importación en Synology y en QNAP, la opción clave «usar la puerta de enlace predeterminada», qué hacer tras cambiar la contraseña y por qué «acceder al NAS desde fuera» es otra cuestión que pide la red Privada.

## Primero, distingue dos cosas

Que el propio NAS salga por la línea (descargas, imágenes de Docker, sincronizar nubes extranjeras): usa OpenVPN, que es lo que explica este artículo.

Acceder al NAS desde fuera (abrir carpetas compartidas en un viaje, ver las cámaras): usa la red Privada (Tailscale), que mete el NAS y tu móvil en la misma red privada; consulta «Ver desde el extranjero tus cámaras y tu NAS en China». Deja ese trabajo a la red Privada: OpenVPN conecta el NAS a nuestra línea, y la red Privada te conecta a ti con tu casa.

## Synology

1. Inicia sesión en este sitio y, en la página de OpenVPN, haz clic en la bandera de una región para descargar el archivo .ovpn de esa región.
2. Panel de control → Red → Interfaz de red → Crear → Crear perfil de VPN → OpenVPN (mediante la importación de un archivo .ovpn), e introduce el correo y la contraseña de tu cuenta de este sitio.
3. «Usar la puerta de enlace predeterminada» (Use default gateway): marcada, todo el tráfico saliente del NAS pasa por la línea (descargas, Docker y Cloud Sync se benefician); desmarcada, solo establece el túnel y el tráfico saliente sigue saliendo por la red local. En la inmensa mayoría de los casos hay que marcarla.
4. Marca «Volver a conectar cuando se pierda la conexión VPN» (Reconnect when the VPN connection is lost) para que se recupere solo tras reiniciar el NAS o si la línea fluctúa. Conecta y prueba una descarga desde algún paquete.

## QNAP

1. Descarga el .ovpn de la misma manera.
2. QVPN Service → VPN Client (cliente VPN) → Add (añadir) → OpenVPN, importa el archivo e introduce la cuenta y la contraseña.
3. En los ajustes de la conexión, marca «Use VPN as the default gateway of the NAS» (usar la VPN como puerta de enlace predeterminada del NAS) y la reconexión automática, y conecta.

## Qué tráfico pasa por la línea y cuál no

- Pasa: las tareas BT y HTTP de Download Station / Download Station, las descargas de imágenes de Docker, la sincronización de Google Drive / Dropbox / OneDrive con Cloud Sync, la obtención de metadatos de Plex y Emby, y las actualizaciones del Centro de paquetes.
- No pasa: el tráfico con el que tú accedes al NAS dentro de la red local; ya está dentro de la red local y no se ve afectado.
- Estás en China y quieres que las webs chinas conecten directamente: el NAS no tiene un script de enrutamiento dividido, y una vez conectado OpenVPN todo el tráfico saliente del NAS pasa por la línea. Si las fuentes de descarga chinas van lentas, usa direcciones de réplicas chinas en las tareas de descarga, o conéctate a la línea solo cuando la necesites.

## Lo que conviene saber

- El archivo de configuración lleva tu cuenta, y el campo de contraseña del NAS deja de funcionar cuando cambias la contraseña: vuelve a descargar el .ovpn y sustitúyelo, o cambia solo la contraseña en el perfil de VPN.
- Cuando la cuenta caduca, el NAS se desconecta; tras renovar se vuelve a conectar solo, sin cambiar la configuración.
- El NAS cuenta como un dispositivo y comparte el cupo de conexiones simultáneas con tus otros dispositivos (Individual 2, Familiar 4, Empresa 8).
- La línea va sobre UDP; un NAS con banda ancha doméstica casi nunca se encontrará con restricciones de UDP.

## Preguntas frecuentes

**Con «Usar la puerta de enlace predeterminada» marcada, ¿se sigue pudiendo acceder al NAS en la red local?** Sí. El tráfico de la red local no pasa por la puerta de enlace; las carpetas compartidas, la reproducción en Plex y la página de administración funcionan igual.

**¿La reproducción remota de Plex va más lenta desde que el NAS pasa por la línea?** La reproducción remota de Plex usa el tráfico saliente del NAS, así que con la puerta de enlace predeterminada marcada da un rodeo por la línea. Para reproducir a distancia es más directo acceder al NAS por la red Privada; o conecta OpenVPN solo cuando necesites descargar.

**¿Se puede hacer que solo Download Station pase por la línea?** Synology y QNAP no tienen enrutamiento dividido por aplicación. Para un control fino, ejecuta en Docker un contenedor de descargas con OpenVPN (como qbittorrent + gluetun) y haz que solo ese pase por la línea.

**¿Y un NAS con un sistema Linux (TrueNAS, Unraid)?** Hazlo al estilo Linux: el paquete openvpn más un archivo de configuración en /etc/openvpn/client/; consulta «Cómo hacer que un servidor Linux y las herramientas de línea de comandos pasen por la línea».

## Para seguir leyendo

- [Página de OpenVPN: descarga de clientes y archivos de configuración](https://www.leotun.com/es/openvpn?utm_source=github&utm_content=overseas-access-06)
- [Cómo usar OpenVPN y cuándo elegirlo](https://www.leotun.com/es/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Ver desde el extranjero tus cámaras y tu NAS en China](https://www.leotun.com/es/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Cómo hacer que un servidor Linux y las herramientas de línea de comandos pasen por la línea](https://www.leotun.com/es/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=overseas-access-06) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=overseas-access-06) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
