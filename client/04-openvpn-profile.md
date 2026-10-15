# 04 · OpenVPN: descarga el perfil .ovpn, impórtalo y conéctate; funciona en routers, NAS y Linux

> Versión web (más extensa): https://www.leotun.com/es/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN es un protocolo de código abierto veterano, y casi todos los sistemas operativos, firmwares de router y NAS traen un cliente para él. Los archivos de perfil de LeoTun ya incluyen tu cuenta, tu contraseña y el material de cifrado, así que puedes conectarte nada más importar uno. Para el día a día en el móvil y el ordenador, AnyConnect o Hiddify dan menos trabajo; el valor de OpenVPN está en **los sitios que solo aceptan OpenVPN**: routers OpenWrt, NAS Synology / QNAP, servidores Linux y dispositivos antiguos.

## Tres pasos

1. Desde la tabla de [la página de OpenVPN en la web](https://www.leotun.com/es/openvpn?utm_source=github&utm_content=client-04), instala el cliente para tu sistema (todas las plataformas tienen el oficial OpenVPN Connect; en Windows también puedes usar OpenVPN GUI, y en macOS, Tunnelblick).
2. Tras iniciar sesión, **haz clic en la bandera de una región** para descargar el .ovpn de esa región. Un archivo por región.
3. Abre el archivo en el cliente y conéctate.

| Plataforma | Notas |
|---|---|
| Windows / macOS / Android / iOS | El perfil lleva la cuenta y la contraseña incorporadas; importa y conecta |
| Linux | Ajustes de VPN del sistema → importar desde archivo, e introduce el correo y la contraseña de la web en la primera conexión; por línea de comandos `openvpn --config file`; para que arranque al iniciar, colócalo en `/etc/openvpn/client/` |
| Router OpenWrt | Instala luci-app-openvpn, sube el .ovpn y actívalo; no hace falta si ya tiene el firmware de este sitio |
| NAS Synology | Panel de control → Red → Interfaz de red → Crear → VPN → OpenVPN (importa el .ovpn); para que el tráfico saliente del NAS pase por la línea, marca «Usar la puerta de enlace predeterminada en la red remota» |
| NAS QNAP | QVPN → VPN Client → Añadir → OpenVPN, importar |

## Si estás en China: conexión directa a las webs chinas

Una vez conectado, el tráfico hacia webs chinas da un rodeo. La web ofrece una herramienta «China directo»: ejecútala con doble clic y las IP chinas conectarán directamente mientras todo lo demás va por la línea. Sirve tanto para Cisco como para OpenVPN. Si estás fuera de China, no la uses.

## Si no conecta, revisa en este orden

| Palabra clave en el registro / síntoma | Causa | Qué hacer |
|---|---|---|
| AUTH_FAILED | Cuenta o contraseña incorrectas, o caducada | Inicia sesión en la web y comprueba la fecha de vencimiento; si cambiaste la contraseña, vuelve a descargar el perfil |
| UDP agota el tiempo de espera y luego conecta por TCP | La red actual restringe UDP y ha pasado a TCP automáticamente | Se puede usar, pero va más lento; si va demasiado lento, cambia de red o usa AnyConnect |
| Tanto UDP como TCP dan TLS handshake failed / key negotiation failed | El camino de red hasta el servidor está cortado | Cambia de región o de red |
| Error al importar | El cliente es demasiado antiguo (anterior a OpenVPN 2.5) | Actualiza el cliente |
| Se corta de repente estando conectado | La cuenta caducó y el servidor te desconectó | Renueva y vuelve a conectar; no hace falta cambiar el perfil |

## ¿UDP o TCP?

Están los dos y no tienes que elegir. UDP va primero en el perfil, así que el cliente prueba UDP antes; si UDP está restringido o no conecta, a los pocos segundos pasa a TCP automáticamente. UDP tiene menos latencia y es más rápido; TCP es solo un respaldo y se nota más lento en conexiones transfronterizas. En redes que restringen UDP de forma permanente (algunas redes de campus y de empresa), recomendamos usar directamente AnyConnect.

> Los perfiles descargados antes del 15 de septiembre de 2026 solo contienen UDP; vuelve a descargarlo si quieres el cambio automático.

## Seguridad

El archivo de perfil contiene tu cuenta y tu contraseña, así que equivale a la propia cuenta: no lo pases a nadie. Si se filtra, cambia la contraseña en la web y el archivo antiguo dejará de funcionar al instante. El propio intercambio inicial también va cifrado: sin la clave del perfil ni siquiera se puede iniciar, y el servidor es invisible para los escáneres.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-04) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-04) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
