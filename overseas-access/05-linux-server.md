# 05 · Cómo hacer que un servidor Linux y las herramientas de línea de comandos pasen por la línea

En Linux hay dos caminos hacia la línea; elige según lo que necesites. Para que pase todo el equipo (descargar imágenes de Docker, ejecutar servicios que necesitan red extranjera, funcionamiento desatendido), usa OpenVPN: un archivo de configuración en /etc/openvpn/client/ que arranca con el sistema. Para que pasen solo unos pocos comandos (git, pip, npm, curl), usa el proxy web: pon la dirección del proxy en la variable de entorno http_proxy y el resto del tráfico no se toca. En Linux de escritorio también puedes importarlo en NetworkManager. Este artículo cubre las tres opciones, con cómo escribir el archivo de contraseña y los comandos para comprobarlo.

## Camino uno: todo el equipo por la línea (OpenVPN)

1. Instala el cliente: Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Inicia sesión en este sitio y, en la página de OpenVPN, haz clic en la bandera de una región para descargar el .ovpn. La configuración que recibe Linux no lleva la cuenta y la contraseña incorporadas (NetworkManager no acepta archivos con credenciales incorporadas), así que crea un archivo de contraseña aparte: dos líneas, la primera tu correo de este sitio y la segunda tu contraseña, con chmod 600.
3. Copia el .ovpn a /etc/openvpn/client/<region>.conf y añade la ruta del archivo de contraseña después de auth-user-pass dentro del archivo.
4. sudo systemctl enable --now openvpn-client@<region>. Comprueba el estado con systemctl status openvpn-client@<region> y verifica que curl -s https://ipinfo.io/country muestra la región que elegiste.
5. Para cambiar de región, descarga otra configuración y activa otra unidad; ejecuta solo una a la vez.

## Camino dos: solo las herramientas de línea de comandos por la línea (proxy web)

La dirección del proxy que aparece en la página de Proxy de este sitio, junto con tu cuenta y tu contraseña, se puede poner directamente en variables de entorno: export https_proxy=https://username:password@proxy-address export http_proxy=$https_proxy. Los caracteres especiales de la contraseña hay que codificarlos para URL. A partir de ahí, curl, wget, git, pip y npm pasan por la línea en esa terminal, y los demás programas no se ven afectados.

El demonio de Docker no lee las variables de entorno de la shell; escríbelo en Environment= dentro de /etc/systemd/system/docker.service.d/proxy.conf y reinicia docker. Para apt, escribe Acquire::https::Proxy en /etc/apt/apt.conf.d/proxy.conf.

En este camino, por diseño, no hay ninguna conexión que se pueda caer; no necesita root ni cambia las rutas. Va bien para servidores de empresa y para cuando solo quieres acelerar las descargas; solo afecta a los programas que respetan las variables de proxy, y el resto del tráfico no se toca.

## Camino tres: NetworkManager en Linux de escritorio

1. Instala network-manager-openvpn-gnome (desde la página de OpenVPN de este sitio, un clic puede abrir el centro de software).
2. Configuración → Red → VPN → «+» → Importar desde archivo, elige el .ovpn, introduce tu correo y tu contraseña de este sitio y guarda.
3. Activa y desactiva la VPN desde la barra superior o la bandeja. Para que se conecte sola al arrancar, marca «Conectar automáticamente a la VPN» en los ajustes de la conexión cableada o inalámbrica.

## Comprobación y solución de problemas

- Comprueba la salida: el país que muestra curl -s https://ipinfo.io es la región que elegiste.
- Comprueba el DNS: en resolvectl status, el DNS de la interfaz VPN debería ser el que envía la línea; si hay fugas, añade dhcp-option DNS a la configuración o usa el script update-systemd-resolved.
- AUTH_FAILED: el archivo de contraseña está mal o la cuenta ha caducado; si cambiaste la contraseña, actualiza el archivo de contraseña.
- Tiempo de espera agotado en el intercambio TLS: el UDP hacia el servidor no pasa; cambia de región o de red. En un servidor en la nube, el grupo de seguridad tiene que permitir UDP saliente.
- El servidor está en China y las fuentes chinas deberían conectar directamente: con OpenVPN conectado, todo el tráfico saliente pasa por la línea. Cambia las fuentes de apt / pip / npm a réplicas chinas, o usa el camino dos para que solo pasen comandos concretos.

## Lo que conviene saber

- Una máquina Linux cuenta como un dispositivo y comparte el cupo de dispositivos simultáneos con los demás (Individual 2 dispositivos, Familiar 4 dispositivos, Empresa 8 dispositivos); el proxy web del camino dos se cuenta por conexión y también entra en el cupo.
- El archivo de configuración y el de contraseña equivalen a tu cuenta; no los subas a un repositorio git ni los metas en una imagen.
- Al cambiar la contraseña, la configuración antigua deja de funcionar al instante; es el mecanismo de revocación previsto. Basta con actualizar el archivo de contraseña.
- Si usas la línea en un servidor en la nube, respeta las condiciones de uso del proveedor; la línea solo registra la duración de la conexión y el tráfico total.

## Preguntas frecuentes

**¿Por qué la configuración para Linux no lleva la cuenta y la contraseña incorporadas?** Al importar una configuración, NetworkManager no acepta un archivo con credenciales incorporadas y da error de importación, así que la copia para Linux te pide rellenarlas tú; con el método de systemd, escríbelas en el archivo de contraseña.

**¿Puedo hacer que solo Docker pase por la línea?** Sí: configura las variables de proxy solo para el demonio de Docker (camino dos), o ejecuta un contenedor con OpenVPN dentro (gluetun) para que pasen por la línea contenedores concretos.

**¿Y la red Privada (Tailscale) en Linux?** El script oficial la instala en una línea, y tailscale up --login-server=<servidor de control de este sitio> inicia sesión. Va bien cuando necesitas acceder a esta máquina desde fuera o quieres configurarla una vez y tenerla siempre en línea; para solo acelerar descargas, OpenVPN o el proxy son más sencillos.

**¿Es igual con OpenWrt en un router?** En OpenWrt, instala luci-app-openvpn y sube el .ovpn, y toda la red local pasará por la línea; un router con el firmware de este sitio no lo necesita: basta con iniciar sesión con tu cuenta.

## Para seguir leyendo

- [Página de OpenVPN: descargas de clientes y archivos de configuración](https://www.leotun.com/es/openvpn?utm_source=github&utm_content=overseas-access-05)
- [Cómo usar OpenVPN y cuándo elegirlo](https://www.leotun.com/es/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Cómo hacer que un NAS Synology o QNAP pase por la línea](https://www.leotun.com/es/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Qué es el proxy web y cuándo usarlo](https://www.leotun.com/es/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=overseas-access-05) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=overseas-access-05) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
