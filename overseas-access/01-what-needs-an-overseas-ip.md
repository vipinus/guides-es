# 01 · Qué servicios necesitan una IP extranjera y cómo funciona la línea

La prueba es la inversa del acceso a China desde fuera: cuando el servicio ve que tu IP de origen está en China continental, o directamente no puedes llegar a sus servidores, no carga, funciona recortado o va lentísimo. La tabla está organizada por uso.

| Categoría | Ejemplos | Qué pasa sin la línea | Qué necesitas además de la IP |
|---|---|---|---|
| Trabajo | Google Workspace, Slack, Zoom, Teams, Notion | No carga o se corta continuamente | Una cuenta de la empresa |
| Desarrollo | GitHub, npm, Docker Hub, fuentes de PyPI que no sean réplicas, Stack Overflow | Tan lento que da tiempo de espera agotado | Nada |
| IA | ChatGPT, Claude, Gemini | No carga | El país de registro de la cuenta, un número de teléfono |
| Investigación | Google Scholar, bases de datos de artículos, correo de la universidad | No carga o va lentísimo | Una cuenta universitaria |
| Juegos | Regiones extranjeras de Steam, PSN, Switch eShop, servidores extranjeros | La tienda no carga, mucha latencia | Una cuenta de la región de esos servidores |
| Vídeo y música | YouTube, Netflix, Disney+, Spotify | No carga | Una cuenta de pago, y la región de la cuenta tiene que coincidir con la IP |
| Redes sociales | X, Instagram, Telegram, Discord, WhatsApp | No carga | Un número de teléfono |

## Una distinción importante

**«Necesitar una IP extranjera» y «necesitar una cuenta extranjera» son cosas distintas.** Para GitHub y YouTube basta con cambiar la IP; Netflix exige una cuenta de pago con la región correspondiente; para registrarte en ChatGPT necesitas un número de teléfono extranjero que pueda recibir códigos de verificación. La línea resuelve «si se puede abrir»; la cuenta corre de tu parte.

## Cómo funciona la línea

Tu tráfico se cifra primero y se envía a un servidor en el extranjero, que luego accede al destino. Lo que ve el destino es la IP de ese servidor. Hay tres formas de hacerlo: un cliente, el proxy web o un router. Para elegir, consulta [Qué método de conexión conviene en cada situación](../network/02-choose-your-connection-method.md).

## Tres ideas equivocadas habituales

- **Cambiar el DNS no sirve.** No poder conectar es un problema de ruta, no de resolución de nombres.
- **La velocidad depende de la línea entre los dos extremos.** Saliendo desde China, el cuello de botella es el enlace transfronterizo y la salida de tu operador, así que la región que elijas importa más que las especificaciones del servidor; consulta la [03](03-which-region-is-fastest.md).
- **Mientras usas apps chinas, no hace falta que todo pase por la línea.** Activa el enrutamiento dividido: por defecto solo los sitios bloqueados van por la línea, mientras que las webs chinas y las extranjeras que ya cargan bien desde China conectan directamente, así ninguna da rodeos; consulta [Enrutamiento dividido en el router](../router/03-router-split-routing.md).

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=overseas-access-01) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=overseas-access-01) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
