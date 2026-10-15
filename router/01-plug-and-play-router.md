# 01 · Primeros pasos con un router ya preparado

## Tres pasos al sacarlo de la caja

1. **Conecta la corriente y el cable de red**: conecta el puerto WAN del router a tu módem o al router que ya tienes y espera a que la luz indicadora se estabilice, alrededor de un minuto.
2. **Conéctate al wifi**: el nombre y la contraseña del wifi predeterminados están impresos en la tarjeta de instrucciones (de fábrica, los dos son el dominio de la web). Una vez conectado, abre un navegador y ve a la dirección de administración `http://192.168.11.1`.
3. **Inicia sesión con tu cuenta**: en la página de administración, introduce el correo y la contraseña de tu cuenta y guarda (las cuentas Individual, Familiar y Empresa pueden usar router). A partir de ahí, todos los dispositivos conectados a este wifi pasan por la VPN automáticamente.

## Cambia las contraseñas predeterminadas

La contraseña de administración y la del wifi de fábrica son públicas, así que cámbialas nada más iniciar sesión: página de administración → System (sistema) → Administration (administración); Wireless (inalámbrico) → Interfaces → Wireless Security (seguridad inalámbrica).

## Modo de enrutamiento dividido

El modo predeterminado es el enrutamiento dividido: los dominios chinos de la lista pasan por la VPN y todo lo demás conecta directamente. Es el modo que mejor encaja si estás en el extranjero viendo vídeo chino o si los mayores de la familia usan la tele. Cuando estás en China y eliges una región extranjera, el sentido se invierte automáticamente: por defecto solo las webs y servicios bloqueados pasan por la VPN, y las webs chinas y las extranjeras que ya cargan bien desde China conectan directamente; consulta [03 · Qué es el enrutamiento dividido en el router](03-router-split-routing.md). Cuando necesites temporalmente que todo pase por la VPN, cambia a «Global» y vuelve cuando termines.

## Preguntas frecuentes

- **La luz indicadora está normal pero los dispositivos conectados no tienen internet**: revisa el estado de la cuenta en la página de administración; tanto una cuenta caducada como una contraseña incorrecta aparecen ahí.
- **Quieres cambiar a otro router**: desvincula primero el antiguo en la web; consulta [Vinculación MAC y sustitución del router](05-mac-binding-and-replacing.md).

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-01) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-01) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
