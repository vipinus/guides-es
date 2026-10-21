# 07 · Ver desde el extranjero tus cámaras de casa en China

> Versión web (más extensa): https://www.leotun.com/es/guides/home-camera?utm_source=github&utm_content=china-access-07

## Tres casos, cada uno con su solución

| Qué tipo de sistema de cámaras tienes en casa | ¿Se puede ver directamente desde el extranjero? | Solución |
|---|---|---|
| App del fabricante con nube (EZVIZ, Xiaomi, TP-Link, Imou, etc.) | Casi siempre sí; en algunas regiones está restringido o va lentísimo | Cambia a una IP china y usa la edición china de la app |
| Una grabadora de vídeo en red (NVR) que solo se puede ver en la red local de casa | No, no tiene punto de entrada público | Mete un dispositivo de casa en una red privada y haz que el dispositivo que tienes en el extranjero entre en la red local de casa a través de ella |
| App del fabricante, pero la de la tienda extranjera es un sistema aparte con sus propios servidores | Las cuentas no coinciden | Instala la edición china de la app y usa la cuenta china |

## Caso uno: la nube del fabricante

La cámara envía la imagen al servidor del fabricante, y la app la recoge del servidor. La conexión desde una red extranjera hasta el servidor de un fabricante chino es mala, y se nota en cargas lentas y cortes de imagen. Al cambiar a una IP china vas por una línea dentro de China, y mejora mucho.

Ten en cuenta que la app del mismo nombre en una tienda extranjera suele conectar con servidores extranjeros, y las cuentas no son intercambiables. Instala la edición china de la app; para problemas con la región de la tienda, consulta la [guía de instalación y solución de problemas](../client/06-ios-app-store.md).

## Caso dos: la grabadora solo está en la red local

Es el caso más habitual y también el más difícil. La NVR no tiene IP pública, y en la banda ancha doméstica china casi nunca se puede hacer redirección de puertos. La forma que funciona es una **red privada**:

1. Deja en casa un dispositivo siempre encendido; vale un ordenador, un NAS, una Raspberry Pi o un router compatible. Instala en él el cliente de la red privada, añádelo a tu red privada y activa «compartir la red local».
2. Añade también a la misma red privada el móvil o el ordenador que tienes en el extranjero.
3. A partir de ahí, el dispositivo en el extranjero llega directamente a la NVR por su dirección de la red local de casa, igual que si estuvieras en casa.

La red «Privada» de LeoTun es justo este tipo de red privada. Con una cuenta no hay límite de dispositivos donde instalarla, y los que pueden estar en línea a la vez dependen del plan: Individual 2, Familiar 4, Empresa 8. Un dispositivo en casa más unos cuantos en el extranjero encajan justo en el plan Familiar.

## Caso tres: las cuentas no coinciden

Un dispositivo comprado en China está vinculado a una cuenta china, y la app de la tienda extranjera no puede iniciar sesión en él. La única solución es instalar la edición china de la app. No vuelvas a vincular el dispositivo, porque eso echará la cuenta de tu familia.

## Un recordatorio sobre la privacidad

La imagen de las cámaras de tu casa solo debería circular entre tus dispositivos y tu casa. La opción de la red privada prefiere una conexión directa entre dispositivos y solo pasa por un servidor intermedio cuando no puede conectar directamente, y la imagen no se guarda en ningún servidor; la opción de la nube del fabricante, en cambio, pasa por el fabricante. En cualquier caso, no uses «herramientas de túnel» de origen desconocido: equivale a entregarle a otro las cámaras de tu casa.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-07) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-07) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
