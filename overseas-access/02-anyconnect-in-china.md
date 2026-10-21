# 02 · ¿Funciona Cisco AnyConnect en China?

> Versión web (más extensa): https://www.leotun.com/es/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Sí. AnyConnect es el protocolo VPN empresarial de Cisco. Empresas de todo el mundo dependen de él para el teletrabajo, y las filiales en China de las empresas extranjeras lo usan a diario, así que prohibirlo por completo saldría demasiado caro. **Lo que se bloquea en realidad es una dirección de servidor concreta, no el protocolo.** Por eso, que «funcione» depende de que el proveedor tenga suficientes direcciones y las sustituya lo bastante rápido.

## Por qué resiste los bloqueos mejor que las apps VPN propietarias

| | AnyConnect | App VPN propietaria |
|---|---|---|
| Huella del tráfico | TLS estándar, igual que visitar una web HTTPS | Protocolo propio, con una huella fija |
| Cuando lo identifican | Solo deja de conectar esa dirección | Deja de funcionar toda la app |
| Cliente | Lo publica Cisco; la alternativa de código abierto OpenConnect existe en todas las plataformas | Desaparece en cuanto lo retiran de la tienda de apps |

LeoTun tiene máquinas propias en 24 regiones. Cuando una dirección queda marcada se sustituye por otra nueva, el nombre de dominio se redirige automáticamente y no hace falta cambiar la dirección guardada en tu cliente.

## Cómo instalarlo

1. Descarga el instalador para tu sistema desde la página de Cisco de la web. Están cubiertos Windows 10 y posteriores, macOS, iOS, Android y Linux; Windows 7/8 solo puede usar la versión 4.9, la última compatible con ellos.
2. Abre el cliente e introduce la dirección del servidor en el campo de dirección; en la web, haz clic en la bandera de una región para copiarla.
3. Introduce tu cuenta y tu contraseña y conecta. No hace falta ningún archivo de certificado ni importar ninguna configuración.
4. Cuando veas «Connected» (conectado), comprueba tu IP de salida.

## Si no conecta, sigue este orden

1. **Cambia a otra región.** Si otra región conecta, es que solo ese servidor está temporalmente inaccesible.
2. **Cambia de red.** Si falla la banda ancha, pasa a los datos móviles, y al revés; las interferencias de los distintos operadores no van sincronizadas.
3. **Lee el error.** `Login failed` se refiere a la cuenta o la contraseña, o al vencimiento; `Untrusted server certificate` casi siempre es la hora del sistema mal puesta o que la red actual intercepta el TLS, así que cambia de red; solo `Connection attempt has failed` significa que la dirección es inaccesible.
4. **Actualiza el cliente.** Sobre todo después de una actualización importante del sistema.
5. **Cambia de método de conexión.** La misma cuenta puede usar OpenVPN o Hiddify para conectar a los mismos servidores, y los bloqueos de los tres protocolos son independientes entre sí; consulta [02 · Qué método de conexión conviene en cada situación](../network/02-choose-your-connection-method.md).

## Actualizar Cisco AnyConnect

Cisco lo ha rebautizado como Cisco Secure Client; se usa igual. No hace falta desinstalar primero: instala la versión nueva encima de la antigua y las direcciones guardadas se conservan. En el móvil, actualízalo en el App Store / Google Play; si la búsqueda de la tienda no lo encuentra, usa el cliente de código abierto OpenConnect, que usa el mismo protocolo y la misma cuenta (para cambiar la región de la tienda de iOS, consulta [Clientes 06](../client/06-ios-app-store.md)).

## Preguntas frecuentes

**¿Que vaya lento es señal de que me están limitando?** Primero cambia de región: mira los semáforos rojo, amarillo y verde de la lista de regiones de la web y elige uno verde. Si sigue lento, la causa habitual es la banda ancha local: banda ancha compartida de urbanización, o un operador y una región que no casan (China Unicom en el norte: Japón o Corea; China Telecom en el sur: Sudeste Asiático o Australia; otros proveedores: los puntos de entrada en China).

**¿Por qué la misma dirección a veces va bien y a veces mal?** La dirección es un nombre de dominio, y las máquinas que hay detrás se sustituyen automáticamente según los bloqueos y la carga. Si esperas un minuto o dos y vuelves a probar, lo normal es que la hubieras pillado en pleno cambio.

**¿Se desconecta solo después de mucho tiempo conectado?** No por el tiempo. Cuando la cuenta caduca, el servidor te desconecta; renueva y vuelve a conectar.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=overseas-access-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=overseas-access-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
