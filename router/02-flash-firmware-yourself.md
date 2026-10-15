# 02 · Instalar el firmware tú mismo: del sistema original al nuestro, paso a paso (con vídeo)

> Videotutorial (unos dos minutos y medio, narrado en inglés o en chino): https://www.leotun.com/es/video/router-flash?utm_source=github&utm_content=router-02
>
> Versión web: https://www.leotun.com/es/guides/router-flash?utm_source=github&utm_content=router-02

Esta guía es para quien ya tiene un router cuyo modelo está en la lista de compatibles. Partes de un router que todavía lleva su sistema original, y vamos desde abrir la web hasta tener toda la casa conectada: qué pulsar en cada paso, qué vas a ver y dónde suele tropezar la gente. La demostración usa un GL.iNet GL-MT3000. Los demás modelos siguen los mismos pasos; solo cambia el aspecto del panel de administración original. Si prefieres no hacerlo tú, un router ya preparado da menos trabajo: consulta la [01](01-plug-and-play-router.md). Para elegir modelo, consulta la [07](07-which-router-to-buy.md).

## Antes de empezar

- **Comprueba que tu modelo es compatible.** Inicia sesión, abre la sección **Router** y busca tu modelo por marca. La revisión de hardware que va tras el nombre del modelo (v1, v2, etc.) también tiene que coincidir.
- **Tu cuenta tiene que estar activa.** Los planes Individual, Familiar y Empresa pueden usar router.
- **Ten a mano un cable de red.** El puerto WAN del router va a tu módem o al router de arriba. Durante la instalación es mejor conectar también el ordenador al router por cable; es más estable que el wifi.
- **Guarda una copia del firmware original.** Descarga el firmware original de tu modelo desde la web del fabricante, por si algún día quieres volver atrás.

## Paso 1: genera el firmware en la web

1. Inicia sesión y haz clic en **Router** en la barra de navegación.
2. Busca tu modelo y haz clic en **Firmware**, o baja hasta «Construir Firmware» y elige el modelo en la lista de marcas.
3. Haz clic en **Iniciar construcción**.

Algunas cosas que conviene saber antes:

- **La generación tarda de 3 a 5 minutos.** El firmware se crea en el momento para tu cuenta; no es un archivo ya hecho. En horas punta puede quedarse en cola. La página te avisa cuando pasa: solo espera, no hace falta volver a pulsar.
- **Recibirás un correo cuando esté listo.** La entrada de «Construcciones recientes» cambia a «Completado» y te llega un aviso al correo.
- **El idioma de la interfaz del firmware sigue el idioma de la web.** Si usas la web en español, las páginas de administración del router estarán en español. Si quieres otro idioma, cambia primero el idioma de la web y luego genera el firmware.
- **El enlace de descarga es válido un día.** Si caduca, simplemente vuelve a generarlo.

## Paso 2: descarga y descomprime

1. En «Construcciones recientes», haz clic en **Descargar**. Obtendrás un archivo zip.
2. Abre la carpeta de Descargas y **descomprímelo**.
3. La carpeta descomprimida contiene el archivo del firmware.

Qué archivo usar:

| Tu router lleva ahora | Usa el archivo |
|---|---|
| El sistema original de GL.iNet (el caso del vídeo) | que termina en `sysupgrade.bin` |
| El sistema original de otra marca | con `factory` en el nombre |
| Ya nuestro firmware, y vas a actualizar | con `sysupgrade` en el nombre |

Si el zip solo contiene un archivo, es ese.

> ⚠️ **Este firmware es solo para ti.** Lleva los datos de tu cuenta para que el router pueda iniciar sesión solo después de la instalación. No envíes el archivo a nadie ni lo compartas públicamente.

## Paso 3: instálalo desde el panel de administración original

Con GL.iNet como ejemplo:

1. Conecta el ordenador al router, abre el panel de administración original en el navegador (`http://192.168.8.1` en GL.iNet) e inicia sesión con la contraseña de administrador.
2. En el menú de la izquierda, abre **System** (sistema) → **Upgrade** (actualizar).
3. Cambia a la pestaña **Firmware Local Upgrade** (actualización local de firmware).
4. Haz clic en la zona de subida y elige el archivo de firmware que descomprimiste.
5. Espera a que la verificación muestre **Pass** (correcto).
6. **Desactiva «Keep Settings» (conservar ajustes).** Es el paso que más se olvida. Los dos sistemas no comparten formato de configuración, y conservar los ajustes antiguos provoca todo tipo de problemas raros.
7. Haz clic en **Install** (instalar).

La página cambia a «Upgrading and rebooting…» (actualizando y reiniciando) con un círculo de progreso. **Tarda de dos a tres minutos. No desenchufes el router ni cierres la página mientras tanto.** Es normal que la página deje de cargar al acabar el progreso: el router ya funciona con otro sistema, y han cambiado tanto su dirección como su wifi. Mira el paso siguiente.

Otras marcas: busca en el panel original «Firmware Upgrade», «System Upgrade» o «Local Upgrade» (o su equivalente en tu idioma), sube el archivo y, igualmente, no conserves los ajustes.

## Paso 4: conéctate al nuevo wifi

Tras la instalación, el nombre del wifi antiguo desaparece y aparece uno nuevo:

- **Nombre del wifi: `www.anyfq.com`**
- **Contraseña del wifi: `www.anyfq.com`** (la misma que el nombre)

Los ordenadores y móviles tienen que **cambiarse a este wifi** para poder conectarse a internet o abrir la página de administración del router. Un ordenador conectado al router por cable no necesita cambiar nada.

La nueva dirección de administración es `http://192.168.11.1` (escribe tú el `http://` del principio).

## Paso 5: espera a que se conecte solo

Sin iniciar sesión y sin elegir región. **Mientras tu cuenta esté activa, el router se conecta solo en menos de 10 minutos.** Una vez conectado, todos los dispositivos de ese wifi pasan por el servicio automáticamente, incluidas teles, decodificadores y consolas.

Para confirmar que está conectado, abre desde un dispositivo conectado al router una web a la que normalmente no puedes acceder, o mira el estado en la página de administración.

## Dos cosas que conviene hacer después

1. **Cambia las contraseñas predeterminadas.** La contraseña del wifi y la de administración vienen de fábrica con valores públicos. Cambia las dos en la página de administración.
2. **Que la señal wifi sea débil justo después de instalar es normal.** El router tiene que conectarse a internet una vez y averiguar en qué región está antes de subir la potencia inalámbrica al nivel permitido allí. Enchufa el cable de red y deja que se conecte primero.

## Sustituir un router antiguo por uno nuevo

Una cuenta está vinculada a un solo router a la vez. Si tu cuenta ya se usó antes en otro router:

1. Inicia sesión, abre la sección **Router** y, bajo el título «Construir Firmware», verás el modelo **Vinculado**, con **Desvincular** al lado.
2. Haz clic en Desvincular. Puedes hacerlo aunque el router antiguo esté roto o no lo tengas a mano.
3. En el router nuevo no hay que hacer nada: **se conecta automáticamente** y queda vinculado a tu cuenta.

Si instalas el router nuevo antes de desvincular, tampoco pasa nada. El router nuevo se queda esperando y se conecta solo en cuanto desvinculas.

Más sobre las reglas en [05 · Vinculación por MAC y sustitución del router](05-mac-binding-and-replacing.md).

## ¿Y si caduca mi cuenta?

Tras el vencimiento, el router deja de pasar el tráfico por el servicio, mientras que la red de casa sigue funcionando con normalidad. **En cuanto renuevas, el router se recupera solo: no hace falta volver a iniciar sesión ni volver a instalar el firmware.**

## No se ha conectado solo: cómo revisarlo

Si pasados unos diez minutos sigue sin funcionar, revisa esto por orden:

1. **¿Funciona la propia conexión de banda ancha?** Desde un dispositivo conectado al router, abre cualquier web normal. Si falla, el problema es el cable o el módem: comprueba que el cable del puerto WAN está bien encajado.
2. **¿Ha caducado la cuenta?** Inicia sesión en la web y comprueba la fecha de vencimiento. Tras renovar, espera unos minutos.
3. **¿Sigue la cuenta vinculada al router antiguo?** En la sección Router, mira el modelo vinculado. Si no es este router, haz clic en Desvincular.
4. **Reinicia el router una vez.** Desenchúfalo, espera diez segundos, vuelve a enchufarlo y dale de dos a tres minutos.
5. **Inicia sesión a mano.** Abre `http://192.168.11.1` y entra en el router con el usuario `root` y la contraseña `www.anyfq.com`. Luego ve a **Services** (servicios) → **VPN**, introduce el correo y la contraseña de tu cuenta y guarda.

¿Sigues atascado? Pregunta en el grupo y dinos el modelo del router y hasta qué punto de la lista llegaste.

## Cuándo no conviene instalarlo tú

El modelo no está en la lista, la revisión de hardware no coincide o es un router antiguo sin modo de recuperación. En estos tres casos, un router ya preparado da menos trabajo.

## Si la instalación sale mal

La mayoría de los routers tienen un modo de recuperación: desenchufa la corriente, mantén pulsado el botón de reset mientras vuelves a enchufarlo, sigue pulsándolo unos segundos, conecta un ordenador por cable y sube el firmware original siguiendo las instrucciones del fabricante. Para GL.iNet, busca «uboot» en su documentación. Para esto sirve el firmware original que guardaste antes.

## Preguntas frecuentes

**¿Instalar otro firmware anula la garantía?** Depende del fabricante. Los routers GL.iNet están basados de por sí en un sistema de código abierto y se puede volver a instalar el original.

**¿Puedo volver al firmware original?** Sí. Usa el modo de recuperación descrito en «Si la instalación sale mal» para subir el firmware original.

**¿Un mismo archivo de firmware sirve para dos routers?** No. El firmware se genera por cuenta, y una cuenta está vinculada a un solo router a la vez.

**¿Necesito generar uno nuevo si cambio de cuenta?** No. Cierra sesión en la página de administración e inicia sesión con la cuenta nueva.

**¿Las futuras actualizaciones exigen volver a instalar?** Las actualizaciones habituales las recoge el router solo; no tienes que hacer nada. Solo una versión mayor requiere generar un firmware nuevo e instalar una vez el archivo sysupgrade, y la web lo anunciará cuando ocurra.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
