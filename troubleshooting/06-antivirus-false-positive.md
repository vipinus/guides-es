# 06 · Qué hacer cuando tu Mac dice que la app «está dañada»

> Versión web (más extensa): https://www.leotun.com/es/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

Primero, la conclusión: el archivo no está roto y nadie lo ha manipulado. Cuando al hacer doble clic en Hiddify en un Mac aparece «está dañado y no se puede abrir» o «no se puede verificar el desarrollador», es Gatekeeper, del propio sistema, el que lo bloquea; sigue los pasos de abajo para permitirlo.

En nuestras pruebas actuales, instalar Hiddify en Windows ya no provoca ninguna alerta de virus. Si aun así el antivirus que tienes instalado lo marca, sigue el mismo orden que aquí: primero verificar, luego permitir.

## Por qué se bloquea

**Los archivos descargados de una página web llevan una marca de cuarentena.** Cuando Gatekeeper de macOS ve esa marca, bloquea la app. El mensaje a veces dice «está dañado» y otras «no se puede verificar el desarrollador»; la causa es la misma.

Lo que hacemos nosotros: el cliente de escritorio es un **espejo sin modificar** del paquete publicado por el proyecto de código abierto original. No lo alteramos, no lo reempaquetamos ni le inyectamos nada; solo lo alojamos en nuestro propio sitio de descargas para que sea más fácil descargarlo.

## Verifícalo tú primero; no lo permitas a ciegas

Permitir una app significa que el sistema deja de comprobarla, así que el orden es: primero verificar, luego permitir.

**Súbelo a VirusTotal para una segunda comprobación.** Arrastra el instalador a [virustotal.com](https://virustotal.com/gui/home/upload). Que unos pocos motores heurísticos lo marquen mientras todos los fabricantes principales lo dan por bueno es el patrón típico de un falso positivo. Si lo marcan la mayoría de los motores principales, **no lo instales**: acude directamente a nosotros.

Continúa solo si pasa la comprobación. Si tienes dudas, contacta primero con soporte y revisaremos el sitio de descargas.

## Tres formas de permitirlo, de la más limitada a la más amplia

Tras hacer doble clic puede que veas «"Nombre del cliente" está dañado y no se puede abrir. Deberías moverlo a la Papelera», o «no se puede abrir porque no se puede verificar el desarrollador». Los tres pasos de abajo van de lo más limitado a lo más amplio; **si el primero funciona, no uses el tercero**.

1. Búscala en «Aplicaciones» en el Finder, haz Control-clic en el icono (o clic derecho), elige «Abrir» y vuelve a hacer clic en «Abrir» en el cuadro que aparece. Es un permiso puntual solo para esta app.
2. Si el menú del clic derecho no tiene un «Abrir» que funcione, ve a «Ajustes del Sistema» → «Privacidad y seguridad» y baja hasta la sección Seguridad. Verás «Se ha bloqueado el uso de "Nombre del cliente" porque no procede de un desarrollador identificado». Haz clic en «Abrir igualmente» a la derecha e introduce tu contraseña para confirmar.
3. Si el mensaje es «está dañado», los dos primeros pasos no suelen funcionar. Abre «Terminal» y ejecuta `sudo xattr -dr com.apple.quarantine` seguido de la ruta de la app (normalmente una `.app` dentro de `/Applications/`), pulsa Intro, escribe tu contraseña de inicio de sesión y vuelve a abrir la app. Lo que hace este comando es quitar la marca de cuarentena que indica el origen de la descarga.

En el primer arranque, el sistema también te pedirá la contraseña para autorizar la instalación de una extensión de red. La app solo puede encargarse del tráfico después de que aceptes.

Algunos recordatorios:

- Usa el comando `xattr` **solo con archivos cuyo origen ya hayas verificado**; en la sección anterior tienes cómo verificarlo.
- **No** uses `sudo spctl --master-disable` para desactivar Gatekeeper de forma global. Eso apaga la protección de todo el equipo, mientras que «Abrir» con clic derecho solo afecta a una app.
- Desde macOS 15, Apple ha endurecido la vía de «Abrir» con clic derecho, y en la mayoría de los casos hay que pasar por el paso de «Ajustes del Sistema». Es un cambio en el comportamiento del sistema, no un problema de nuestro paquete.
- Los Mac que entrega la empresa suelen estar gestionados con un perfil MDM, y puede que los tres pasos anteriores estén desactivados. No lo fuerces; usa una de las tres opciones de abajo.

## ¿No quieres permitirlo? Usa una de estas tres

Sus clientes **funcionan en macOS con un doble clic** y no muestran ninguno de los mensajes anteriores. La cuenta es la misma, sin pagar nada más:

- **Red privada (cliente oficial de Tailscale)**: funciona nada más instalarlo, ideal para dejarlo activado siempre
- **OpenVPN Connect**: el instalador propio de OpenVPN; solo hay que importar la configuración
- **Cisco Secure Client**: un cliente de nivel empresarial que ya está instalado en muchos ordenadores de empresa

## Preguntas frecuentes

**¿El programa de ustedes lleva realmente un virus?**
No. Es un espejo sin modificar del paquete oficial publicado por el proyecto de código abierto original. Pero no tienes por qué fiarte solo de nuestra palabra; arriba tienes cómo comprobarlo tú mismo: súbelo a VirusTotal y mira cómo se reparten los veredictos de los motores.

**¿Lo seguirá marcando Windows?**
Por ahora, en nuestras pruebas, el centro de seguridad integrado en Windows ya no marca la instalación de Hiddify. Si aun así lo marca el antivirus que tienes instalado, súbelo antes a VirusTotal para una segunda comprobación y, si la pasa, marca la carpeta de instalación de Hiddify como de confianza en el antivirus. No desactives la protección en tiempo real para instalarlo.

**Tras instalarlo en el Mac no abre. ¿Se descargó mal?**
No. No abre porque Gatekeeper lo está bloqueando. Resuélvelo con las tres formas de permitirlo de arriba.

**¿Debería instalar un antivirus en el Mac para acompañarlo?**
No. Lo que te bloquea en macOS es Gatekeeper, integrado en el sistema, no un antivirus. Instalar un antivirus de terceros no hará desaparecer este mensaje y puede añadir bloqueos nuevos.

**¿Pasa esto en el móvil?**
En iOS, instalando desde el App Store, el problema no existe. Android avisa de vez en cuando sobre orígenes desconocidos; basta con permitirlo.

---

Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=troubleshooting-06) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=troubleshooting-06) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
