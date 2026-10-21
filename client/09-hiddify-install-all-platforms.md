# 09 · Instalar Hiddify en todas las plataformas: Windows, macOS, Linux, Android, iOS

El cliente que usa la sección Hiddify de este sitio es Hiddify, de código abierto, que lleva integrado el núcleo sing-box, así que una vez instalado no hay que configurar nada más. Las cinco plataformas usan la misma app, pero los obstáculos del primer arranque cambian: en Windows el antivirus puede bloquearlo o borrarlo; en un Mac puede decirte que «está dañada» y además tienes que autorizar una extensión de red; en Linux tienes que ejecutar un comando de autorización para que funcione el modo VPN, y en el iPhone no aparece en la tienda de China. Este artículo explica, para cada plataforma, dónde descargarlo, cómo instalarlo y qué hacer en el primer arranque, y termina con los pasos más cortos para importar una suscripción y conectarte.

## Dónde descargarlo

| Plataforma | Instalador | Dónde conseguirlo |
|---|---|---|
| Windows | Instalador (.exe), solo x64 | Zona de descargas de la página de Hiddify |
| macOS | .dmg, un solo paquete para Apple silicon e Intel | Zona de descargas de la página de Hiddify |
| Linux | .deb (familia Debian / Ubuntu), solo x64 | Zona de descargas de la página de Hiddify |
| Android | .apk, en dos versiones: ARM64 y x86-64 | Zona de descargas de la página de Hiddify, o Google Play |
| iPhone / iPad | Hiddify Proxy & VPN en el App Store | App Store; requiere un Apple ID de fuera de la región de China |

La zona de descargas de la página de Hiddify te recomienda automáticamente el paquete para tu sistema actual, y debajo aparecen los de los demás sistemas. Junto a cada fila hay además un icono de «sitio oficial» que lleva a la página oficial de versiones de Hiddify, para que puedas comparar versiones. Los tres sistemas de escritorio (Windows, macOS, Linux) tienen también videotutoriales.

Los instaladores de escritorio son copias sin modificar de los paquetes oficiales de Hiddify, ni alterados ni reempaquetados. Antes de darle permiso puedes comprobarlo tú mismo: sube el instalador a VirusTotal y échale un vistazo; cómo hacerlo, en [Solución de problemas 06](../troubleshooting/06-antivirus-false-positive.md).

## Windows

1. Descarga el instalador desde la zona de descargas de la página de Hiddify y haz doble clic para instalarlo. (En nuestras pruebas actuales, Seguridad de Windows no lo marca; si lo marca el antivirus que tengas instalado, consulta las preguntas frecuentes al final de [Solución de problemas 06](../troubleshooting/06-antivirus-false-positive.md).)

## macOS

1. Descarga el .dmg desde la zona de descargas de la página de Hiddify, ábrelo y arrastra Hiddify a «Aplicaciones».
2. En «Finder» → «Aplicaciones», mantén pulsada la tecla Control y haz clic en el icono de Hiddify, elige «Abrir» y vuelve a hacer clic en «Abrir» en el cuadro de diálogo.
3. Si sigue sin abrirse: «Ajustes del Sistema» → «Privacidad y seguridad», haz clic en «Abrir igualmente» en la sección «Seguridad» e introduce tu contraseña para confirmar.
4. Si te dice que «está dañada y no se puede abrir»: el archivo no está dañado; lo está bloqueando Gatekeeper, del sistema. Abre «Terminal», ejecuta el comando de abajo, pulsa Retorno, introduce tu contraseña de inicio de sesión y vuelve a abrir Hiddify:

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Este comando solo quita la marca de cuarentena que indica que el archivo se descargó de internet, y solo afecta a esta app. **No** uses `sudo spctl --master-disable` para desactivar Gatekeeper en todo el equipo.

La primera vez que pulses conectar tras la instalación, el sistema también te pedirá que autorices una «extensión de red». Si te saltas este paso, el icono se queda girando y nunca conecta:

- **macOS 15 Sequoia y posteriores**: «Ajustes del Sistema» → «General» → «Ítems de inicio y extensiones», baja hasta «Extensiones» al final, cambia la vista a «Por categoría», haz clic en la ⓘ junto a «Extensiones de red», activa el interruptor de Hiddify e introduce tu contraseña o usa la huella cuando te lo pida.
- **macOS 13 Ventura / 14 Sonoma**: abre primero Hiddify y pulsa conectar una vez, y aparecerá «Extensión del sistema bloqueada»; luego ve a «Ajustes del Sistema» → «Privacidad y seguridad», baja hasta «Se ha bloqueado la carga del software del sistema del desarrollador…», haz clic en «Permitir» e introduce tu contraseña.

En un Mac de empresa, si estos botones aparecen en gris, es que una política de gestión de dispositivos los ha bloqueado; pregunta a TI o usa en su lugar los clientes de Cisco, OpenVPN o la red privada.

## Linux

1. Descarga el .deb desde la zona de descargas de la página de Hiddify y haz doble clic para instalarlo con el centro de software, o abre una terminal en la carpeta de descarga y ejecuta (Debian, Ubuntu y derivadas):

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Si conectas nada más instalar, verás «operation not permitted» (operación no permitida) y el modo VPN no arrancará, porque el deb oficial no tiene ese permiso al instalarse. Abre una terminal, ejecuta el comando de abajo para autorizar Hiddify y vuelve a abrir Hiddify:

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Vuelve a ejecutarlo después de cada actualización de Hiddify**: la autorización va ligada al archivo del programa, y una actualización sustituye el archivo, así que la autorización se pierde.

El paquete deb es x64; en dispositivos Linux ARM usa OpenVPN, y la misma cuenta sirve.

## Android

1. Descarga el .apk desde la zona de descargas de la página de Hiddify. La página te recomienda automáticamente la arquitectura de tu móvil; la inmensa mayoría son ARM64. Si puedes usar Google Play, también puedes instalarlo directamente desde la tienda.
2. Si durante la instalación aparece un aviso sobre «orígenes desconocidos» o una advertencia del software de seguridad, permítelo.
3. La primera vez que pulses conectar, el sistema te pedirá permiso de VPN; toca permitir.

## iPhone / iPad

1. Busca «Hiddify» en el App Store e instálala; es gratuita.
2. Si no la encuentras, o te aparece «Esta app no está disponible actualmente en tu país o región»: en iOS, instala desde el App Store con un Apple ID de una región distinta de China (Hiddify está en las tiendas de Estados Unidos, Hong Kong, Taiwán, Japón y Singapur). Te recomendamos crear uno nuevo: en el App Store, toca «Obtener» en cualquier app gratuita → «Crear Apple ID nuevo», elige una región como Hong Kong o Estados Unidos y como método de pago «Ninguno». Solo cambias de cuenta en el App Store, e iCloud no se ve afectado. Para los pasos completos, consulta [06 · Qué hacer cuando iOS no te deja instalar una app](06-ios-app-store.md).
3. La primera vez que pulses conectar, el sistema te pedirá permiso de VPN; toca permitir.

**No** uses un Apple ID que te preste otra persona: puede bloquear tu dispositivo a distancia.

## Después de instalar: importa una suscripción y conéctate

1. Inicia sesión en la web y abre la página de Hiddify.
2. Haz clic en la bandera de la región que quieras y aparecerá un código QR; o haz clic en «Importar todas las regiones · selección automática», arriba en la página, para importar de una vez todas las regiones fuera de China y dejar que el cliente elija automáticamente. **La región de China se importa aparte**: para ver vídeo o usar la banca en línea de China desde el extranjero, haz clic en la bandera de China para importarla.
3. Debajo del QR hay tres botones, agrupados por tipo de suscripción. Hiddify usa el primero (muestra Hiddify / sing-box / GUI.for.SingBox / Karing, con el subtítulo «Suscripción sing-box»), y es el mismo botón en el móvil y en el ordenador. Móvil: tócalo, pásate a Hiddify y añádela según te indique, o escanea el código con Hiddify desde otro dispositivo. Ordenador: haz clic para copiar una dirección https:// y luego, en Hiddify, haz clic en «+» → «Add from clipboard» (añadir desde el portapapeles).
4. Haz clic en conectar.

Para la diferencia entre los tres botones, cómo importar en Clash y otros clientes y si una suscripción caduca, consulta [02 · Cómo importar un enlace de suscripción (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md). Si ya la importaste pero no conecta, consulta [Solución de problemas 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Preguntas frecuentes

**¿Han modificado los instaladores?** No. Los instaladores de escritorio son copias sin modificar de los paquetes oficiales de Hiddify. Cada fila de la página de Hiddify tiene un enlace a la página oficial de versiones, para que compares versiones tú mismo, y también puedes subir el archivo a VirusTotal para asegurarte.


**Ya ejecuté el comando xattr en mi Mac y sigue sin conectar.** Lo más probable es que no se haya autorizado la «extensión de red»; sigue la sección de macOS de arriba y activa el interruptor de Hiddify en Ajustes del Sistema.

**Tras actualizar Hiddify en Linux, el modo VPN ha vuelto a dejar de funcionar.** Es lo esperado; ejecuta otra vez el comando de autorización después de actualizar.

**¿Se puede usar en ordenadores Windows o Linux con ARM?** Sí, con otro método de acceso como OpenVPN, y la misma cuenta sirve; los paquetes de escritorio de Hiddify son, de momento, x64.

**¿No quieres complicarte con los pasos de dar permiso?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect) y la red privada (Tailscale) se abren con un doble clic; el antivirus no los marca, un Mac no dice que estén «dañados», y la cuenta es la misma.

## Para seguir leyendo

- [Página de Hiddify: descargas del cliente y códigos QR de cada región](https://www.leotun.com/es/singbox?utm_source=github&utm_content=client-09)
- [Cómo importar un enlace de suscripción (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/es/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [El antivirus marca el cliente / el Mac dice que está dañado: primero verifica, luego permite](https://www.leotun.com/es/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [Qué es la autorización de «extensión de red» de macOS y cómo permitirla](https://www.leotun.com/es/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [Qué hacer cuando iOS no te deja instalar una app](https://www.leotun.com/es/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-09) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-09) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
