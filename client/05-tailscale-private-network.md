# 05 · Red privada (Tailscale): instalar, iniciar sesión en el servidor de control de este sitio y elegir una salida

> Versión web (más extensa): https://www.leotun.com/es/guides/tailscale-mesh?utm_source=github&utm_content=client-05

La sección de red Privada usa Tailscale (una herramienta de red basada en WireGuard). LeoTun tiene su propio servidor de control, y se inicia sesión con **tu cuenta de este sitio**, que no tiene nada que ver con una cuenta oficial de Tailscale. Inicias sesión una vez y te quedas en línea; la región de salida se puede cambiar desde el menú cuando quieras. Para ver en qué se diferencia de una VPN y a quién le conviene, consulta la [guía de red 03](../network/03-private-network-vs-vpn.md).

## Instalación

| Plataforma | Dónde conseguirlo |
|---|---|
| Windows / macOS / Linux / Android | La zona de descargas de [la página de la red Privada de la web](https://www.leotun.com/es/mesh?utm_source=github&utm_content=client-05) (la sirve directamente este sitio, no hace falta ir a la web oficial) |
| iPhone / iPad | App Store; exige un Apple ID de fuera de la región de China (consulta [Clientes 06](06-ios-app-store.md)) |

## Iniciar sesión

1. **Cierra antes la sesión de la cuenta oficial** (si alguna vez la iniciaste): en el móvil, toca tu avatar → Log Out (cerrar sesión); en el ordenador, ejecuta `tailscale logout`. Si no cierras la sesión del todo, la opción del paso siguiente no aparece.
2. **Apunta el inicio de sesión a este sitio**:
   - Móvil: en la pantalla sin sesión, toca «⋯» arriba a la derecha → Use custom server (usar servidor personalizado; en algunas versiones se llama Use an alternate server), introduce la dirección que aparece en la página de la red Privada de la web y toca Log in (iniciar sesión).
   - Windows / Linux: copia el comando `tailscale up --login-server=…` de la página de la web y ejecútalo en PowerShell o en un terminal.
   - macOS: **no hagas clic en Log in**. En la ventana de Tailscale, haz clic en la flecha de la fila de la cuenta → Account Settings… → Accounts → la flechita junto a «Add Account…» → Add Account Using Alternate Server (añadir cuenta con un servidor alternativo), pega la dirección y haz clic en Add Account….
3. El navegador abre automáticamente la página de inicio de sesión de este sitio; confirma con tu cuenta de este sitio. Al volver al cliente, ya está en línea.

## Elegir una salida

- Móvil: menú → Exit Node (nodo de salida), elige una región; se aplica al momento.
- Ordenador: icono de la bandeja / de la barra de menús → submenú Exit Node; o `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` muestra las disponibles).
- Para no usar salida, elige None (ninguna; en la línea de comandos, deja vacío el valor tras el signo igual). Solo se puede usar una salida a la vez.

## Vencimiento y número de dispositivos

- La validez del inicio de sesión de un dispositivo sigue la fecha de vencimiento de la cuenta, y se desconecta a los pocos minutos de vencer; tras renovar, basta con iniciar sesión una vez más. No hace falta reinstalar.
- El número de dispositivos en línea a la vez depende de tu plan (Individual 2, Familiar 4, Empresa 8), y el cupo se comparte con los demás métodos de acceso; si superas el límite de tu plan, puedes subir temporalmente de tipo de cuenta (el tiempo restante se convierte a valor equivalente según el precio) y volver cuando termines.

## Dos casos en los que encaja mejor otro método

- Con otra VPN funcionando en el mismo dispositivo (el AnyConnect de la empresa, otro software de red mallada): se pelean por el DNS y las rutas. Esa es la causa de los avisos de derechos al ver vídeo chino y de que no abra la intranet de la empresa.
- En una red de campus o de empresa que restringe UDP: WireGuard funciona sobre UDP, así que solo puede pasar por los relés de Tailscale, que son muy lentos; cambia a AnyConnect.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=client-05) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=client-05) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
