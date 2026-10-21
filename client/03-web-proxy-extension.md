# 03 · Proxy web: configura la extensión ZeroOmega en dos pasos

> Versión web (más extensa): https://www.leotun.com/es/guides/web-proxy?utm_source=github&utm_content=client-03

El proxy web solo envía **este navegador** por la línea; los demás programas del sistema no se tocan. No hay cliente que instalar, no hacen falta derechos de administrador y no existe un estado de «conectado», así que, por diseño, no hay conexión que se pueda cortar. Es ideal para el ordenador de la empresa, para un equipo que ya está conectado a la VPN corporativa o para cuando quieres que solo un navegador use la línea. Para saber cuándo usarlo y cuándo hace falta una VPN, consulta la [guía de red 02](../network/02-choose-your-connection-method.md).

## Dos pasos

1. **Instala la extensión**: instala ZeroOmega (la continuación de SwitchyOmega) en Chrome / Edge / Firefox. [La página de Proxy Web de la web](https://www.leotun.com/es/httpproxy?utm_source=github&utm_content=client-03) tiene el enlace de instalación para cada navegador.
2. **Importa**: inicia sesión en la web y, en la página de Proxy Web, haz clic en la bandera de la región que quieras (o en «Copiar el enlace de importación de todas las regiones» para importarlas todas de una vez); así se copia el enlace de configuración. Abre «Import/Export» (importar/exportar) en la extensión, pégalo en «Restore from online» (restaurar desde internet) y haz clic en «Restore» (restaurar). Regiones, direcciones y método de cifrado se importan de una vez, sin escribir nada a mano.

Después, haz clic en el icono de la extensión y elige una región; luego escribe el usuario y la contraseña de tu cuenta de la web en el cuadro de inicio de sesión que muestra el navegador. Para cambiar de región, haz clic en otra en el menú del icono; para volver a la conexión directa local, cambia a «Direct» (directo).

## En estos casos, usa un método para todo el equipo

- Apps y reproductores de vídeo y música: la mayoría no usan el proxy del navegador, así que te pasa que «las páginas abren pero los vídeos no se reproducen».
- Apps del móvil, juegos y programas de escritorio. La configuración de proxy de programas como Dropbox solo acepta HTTP / SOCKS5 sin cifrar, mientras que en la práctica un proxy tiene que ir cifrado, así que el proxy web de este sitio no se puede introducir ahí. Usa Hiddify para encargarse de todo el equipo; consulta el [10](10-app-proxy.md).
- Ver Tencent Video o iQIYI desde el extranjero: las webs de vídeo también comprueban el IPv6 y el DNS, que el proxy web no cubre; usa una VPN para todo el equipo.

## Preguntas frecuentes

| Síntoma | Causa |
|---|---|
| El cuadro de inicio de sesión no deja de aparecer | La cuenta ha caducado o la contraseña es incorrecta |
| Algunas webs no abren y otras sí | Las reglas de «auto switch» (cambio automático) de la extensión las han enviado por conexión directa; prueba una vez con el modo de proxy global |
| En China solo abren las webs HTTPS | El HTTP sin cifrar se modifica por el camino y solo pasan las conexiones cifradas; hoy en día casi todas las webs usan HTTPS |
| Va lento | Cambia de región; el proxy y la VPN usan los mismos servidores |

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-03) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-03) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
