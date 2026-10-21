# 10 · ¿Se verán afectados el NAS, la impresora y las cámaras que hay detrás del router?

Cuando entra en casa un router VPN, la primera preocupación suele ser el resto de aparatos: ¿seguirán funcionando el NAS, la impresora y las cámaras? ¿Mandará el NAS todo su tráfico por la VPN?

## La respuesta corta

No. El enrutamiento dividido viene activado por defecto: **el tráfico entre los dispositivos de casa y el tráfico hacia servicios en China nunca entra en el túnel. Solo pasan por él los sitios que necesitan la VPN.**

## Tres tipos de tráfico, tres caminos

| Tráfico | Camino | Ejemplos |
|---|---|---|
| Entre dispositivos de casa | Se queda en la red local, nunca toca el túnel | Copiar archivos al NAS, enviar contenido a la tele, imprimir |
| Hacia servicios en China | Directo, por tu propia conexión de banda ancha | El NAS sincronizando con una nube china, las cámaras subiendo vídeo a una nube china, descargas desde China |
| Hacia sitios bloqueados | Por el túnel | YouTube, buscadores, herramientas de IA |

Así que copiar archivos al NAS en casa va a toda la velocidad de la red local, y sus copias de seguridad en nubes chinas aprovechan toda tu banda ancha sin tocar la VPN.

Si estás en el extranjero y usas una ruta hacia China, el sentido se invierte: los sitios chinos de la lista van por el túnel y todo lo demás va directo. Consulta [03 · Qué es el enrutamiento dividido](03-router-split-routing.md).

## Tres situaciones habituales

**Acceder al NAS desde fuera (archivos en remoto, copia de fotos del móvil)**
Dos maneras:
- Usa la red privada (Tailscale): inicia sesión en el NAS y en el móvil con la misma cuenta y llega al NAS por su nombre de dispositivo desde cualquier lugar. Sin IP pública ni redirección de puertos. Consulta [Red privada frente a VPN](../network/03-private-network-vs-vpn.md).
- Sigue haciendo lo de antes (el acceso remoto del fabricante, la redirección de puertos). El router no lo bloquea.

**Descargas en el NAS**
Las descargas desde fuentes chinas van directas y no se ven afectadas. Las de webs extranjeras que ya cargan bien desde China (las descargas de Apple y Microsoft, por ejemplo) también van directas por defecto; solo las de sitios bloqueados pasan por el túnel y van a la velocidad del túnel. Si no quieres que las descargas usen el túnel, conecta el NAS al router de arriba o al módem y se saltará este router por completo.

**Un portátil del trabajo que necesita la VPN de la empresa**
Conéctalo al wifi del router de arriba o del módem, no a este router. Dos VPN apiladas una sobre otra suelen romper el acceso a la red de la empresa.

## Cuando un dispositivo no se comporta como debe

- El dispositivo tiene activado «DNS privado» o «DNS seguro». En ese caso resuelve los nombres por su cuenta, saltándose el router, y el enrutamiento dividido no lo ve. Desactiva ese ajuste.
- Comprueba a qué wifi está conectado. Si está en el wifi del módem, nunca ha pasado por este router.

## Preguntas frecuentes

**¿El NAS ocupa una plaza de dispositivo en mi cuenta?** No. El router ocupa una plaza, y lo que hay detrás no cuenta por separado.

**Con toda la familia conectada, ¿me quedaré sin datos?** Las cuentas tienen datos ilimitados, y el tráfico dentro de China ni siquiera entra en el túnel.

**¿Puedo dejar un dispositivo siempre fuera de la VPN?** Sí, conéctalo al router de arriba o al módem. En la página de administración también puedes pasar todo el router al modo «Direct» (directo), pero eso afecta a todos a la vez.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-10) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-10) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
