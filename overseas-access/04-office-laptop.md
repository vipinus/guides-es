# 04 · Con el ordenador de la empresa: sin derechos de administrador y ya conectado a la VPN corporativa

Un ordenador de empresa tiene tres restricciones: no puedes instalar software no autorizado, no tienes derechos de administrador y a menudo ya está conectado a la VPN corporativa. Una VPN para todo el dispositivo, en estas condiciones, o no se puede instalar o se pelea con la VPN de la empresa. La herramienta adecuada es el Proxy Web: una extensión del navegador que solo envía por la línea las peticiones de ese navegador, mientras la intranet de la empresa, el cliente de correo y la VPN corporativa siguen exactamente igual, y sin necesidad de derechos de administrador. Este artículo explica cómo configurarlo, qué puede hacer, qué no debes hacer y cómo llevarte bien con la política de TI de la empresa.

## Por qué el Proxy Web

- Sin cliente que instalar: es solo una extensión del navegador, y la mayoría de las empresas permiten extensiones pero no programas.
- Sin derechos de administrador: la extensión funciona en el espacio del usuario y no cambia la configuración de red del sistema.
- Convive con la VPN corporativa: la VPN de la empresa se hace cargo de las rutas del sistema, mientras que el Proxy Web solo actúa en el navegador, así que no se estorban; las páginas de la intranet siguen pasando por la VPN de la empresa.
- Por diseño, no hay conexión que se pueda caer: el proxy trabaja petición a petición, sin una conexión permanente, así que tampoco notas los altibajos de la red de la empresa.

## Configúralo en dos pasos

1. Instala en el navegador la extensión ZeroOmega (la continuación de SwitchyOmega); la página de Proxy de este sitio tiene el enlace de instalación para cada navegador.
2. Inicia sesión en este sitio y, en la página de Proxy, haz clic en «Copiar enlace de restauración de la extensión»; luego pégalo en la extensión, en «Import/Export» (importar/exportar) → «Restore from online» (restaurar desde internet). Las regiones y las direcciones se importan de una vez; a partir de ahí, haz clic en el icono de la extensión, elige una región e introduce la cuenta y la contraseña de este sitio en la ventana de inicio de sesión que muestra el navegador.
3. Te recomendamos un perfil de navegador aparte (o un navegador distinto) dedicado al proxy, y dejar el navegador de trabajo en local, para no mezclar las dos cosas.

## Para qué sirve y cuándo hace falta otro método

- Sirve: buscar información, abrir Google, GitHub, Stack Overflow, webs de documentación extranjeras, la versión web de ChatGPT y el correo web.
- Otro método: las apps de vídeo, los programas de escritorio y las herramientas de línea de comandos no usan por defecto la configuración de proxy del navegador (para la línea de comandos puedes poner la dirección del proxy en la variable de entorno http_proxy; consulta el artículo de Linux).
- Otro método: ver webs de vídeo chinas (para quien está fuera de China); las webs de vídeo también comprueban el IPv6 y el DNS, que el Proxy Web no cubre, así que ese caso necesita una VPN para todo el dispositivo.

## Llevarse bien con la política de TI

Todo lo que hay en un ordenador de empresa puede ser auditado por la empresa, y las extensiones no son una excepción. Lee primero la política de uso aceptable de la empresa: lo que prohíben la mayoría de las empresas es el software no autorizado y saltarse la política de seguridad, y una extensión del navegador que accede a webs externas suele estar en zona gris; si no lo tienes claro, pregunta a TI.

No instales una VPN para todo el dispositivo (Cisco, red Privada, Hiddify) en un ordenador de empresa para saltarte la política de la empresa: cambian las rutas del sistema, lo que dispara alertas en el software de gestión de equipos y además saca fuera el tráfico de la intranet. El Proxy Web solo afecta a un navegador y es lo que menos riesgo tiene.

Separa las cuentas de trabajo de las personales: no inicies sesión en cuentas de la empresa en el navegador que usa el proxy, ni en cuentas personales en el navegador de la empresa.

## Preguntas frecuentes

**¿Y si la empresa prohíbe instalar extensiones?** Entonces usa tu propio móvil o tu ordenador personal. No uses software portátil de origen desconocido para saltarte los controles.

**¿La extensión verá el tráfico de la intranet de la empresa?** No. Con las reglas de enrutamiento dividido, los dominios de la intranet conectan directamente y no pasan por el proxy; en modo global solo se envían al servidor proxy y vuelven, y lo que ve el proxy es el nombre de dominio, no el contenido. Para ir sobre seguro, dale al proxy su propio perfil de navegador.

**¿El proxy sigue funcionando con la VPN de la empresa activada?** Sí, no hay conflicto. Unas pocas VPN corporativas obligan a que todo el tráfico salga por la salida de la empresa y desactivan la configuración de proxy; en ese caso la extensión dice que no puede conectar, y la única opción es desactivar la VPN de la empresa.

**¿Es igual en un Mac de empresa?** Igual; las extensiones de Chrome, Edge y Firefox tienen versión para Mac. Safari no tiene esta extensión, así que usa otro navegador.

## Para seguir leyendo

- [Página de configuración del Proxy: instalación de la extensión y enlace de restauración](https://www.leotun.com/es/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Qué es el Proxy Web y cuándo usarlo](https://www.leotun.com/es/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Cómo hacer que un servidor Linux y las herramientas de línea de comandos pasen por la línea](https://www.leotun.com/es/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Qué método de conexión conviene en cada situación](https://www.leotun.com/es/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Versión web de este artículo (también disponible en otros idiomas): https://www.leotun.com/es/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=overseas-access-04) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=overseas-access-04) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
