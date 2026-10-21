# 01 · Qué servicios necesitan una IP china

Solo hay una prueba: cuando el servicio ve que tu IP de origen no está en China continental, te rechaza o te da un servicio recortado. La tabla está ordenada según lo estricto que es el bloqueo.

| Categoría | Ejemplos | Qué pasa sin IP china | Qué más se comprueba aparte de la IP |
|---|---|---|---|
| Vídeo | iQIYI, Tencent Video, Youku, Mango TV, algunas series de anime en Bilibili | Te avisa de que solo está disponible en China continental, o solo puedes ver lo gratuito | Región de la tienda de apps, dónde se registró la cuenta |
| Música | NetEase Cloud Music, QQ Music, Kugou | Muchísimas canciones salen en gris y no se pueden reproducir | Nada |
| Trámites oficiales | La plataforma nacional de servicios del gobierno, webs de servicios provinciales, impuestos, seguridad social, fondo de vivienda | La página no carga o el código de verificación nunca llega | Número de teléfono, reconocimiento facial |
| Educación | CHSI, la web de verificación de títulos, los sistemas académicos de las universidades | No cargan o van lentísimos | Nada |
| Viajes | 12306, webs de aerolíneas | No cargan, el pago falla | Número de teléfono, pago |
| Finanzas | Banca en línea, banca móvil, Alipay, WeChat Pay | El control de riesgos bloquea el inicio de sesión, las transferencias fallan | Tarjeta SIM, huella del dispositivo, rostro |
| Juegos | Juegos de PC y móvil en servidores chinos | Puedes entrar, pero con mucha latencia y desconexiones | Verificación de identidad real |
| Vida diaria | Meituan, Ele.me, DiDi, algunas funciones de Taobao | Errores de ubicación, los pedidos fallan | Ubicación, número de teléfono |
| Directos | Douyin, Kuaishou, Douyu | No se pueden ver en algunas regiones | Nada |

## Una distinción importante

**«Necesita IP china» y «necesita número de teléfono chino» son cosas distintas.** El vídeo y la música solo miran la IP, y con cambiarla basta. Los trámites oficiales, la banca y la compra de billetes, además de la IP, te piden recibir un código por SMS y pasar el reconocimiento facial. La IP resuelve «si la página se abre»; la verificación posterior depende de tu propio número de teléfono chino y tus documentos de identidad.

## Cómo resolver lo de la IP

El tráfico va primero a un servidor en China continental, que luego visita el destino. Hay tres formas de hacerlo: un cliente, el proxy web o un router. Para elegir, consulta [Qué método de conexión conviene en cada situación](../network/02-choose-your-connection-method.md) en el repositorio hermano.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-01) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-01) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
