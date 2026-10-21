# 02 · Ver vídeo chino desde el extranjero

> Versión web (más extensa): https://www.leotun.com/es/guides/overseas-video?utm_source=github&utm_content=china-access-02

## Por qué no puedes verlo

Las plataformas compran los derechos solo para China continental, y las IP extranjeras quedan bloqueadas sin excepción. No es un fallo técnico, y la única solución es cambiar de IP.

## Diferencias entre plataformas

| Plataforma | Versión web | App | Notas |
|---|---|---|---|
| iQIYI | Basta con cambiar la IP | Basta con cambiar la IP | La edición internacional, iQIYI, es otra app con menos contenido; no instales la equivocada |
| Tencent Video | Basta con cambiar la IP | Basta con cambiar la IP | Lo mismo pasa con la edición internacional, WeTV |
| Youku | Basta con cambiar la IP | Basta con cambiar la IP | |
| Mango TV | Basta con cambiar la IP | Basta con cambiar la IP | |
| Bilibili | La mayor parte del contenido se ve igualmente | Igual | Solo algunas series de anime y documentales tienen restricción regional |
| Yangshipin / CCTV | Basta con cambiar la IP | Igual | Los canales en directo son los más sensibles a la IP |

**La trampa de la app internacional**: si buscas iQIYI en una tienda de fuera de China, lo normal es que te salga la edición internacional, cuyo catálogo es completamente distinto. Para ver el catálogo chino tienes que instalar la edición china de la app; en iPhone hace falta un Apple ID de la región de China, y en Android se puede instalar el APK directamente.

## Conectado, pero sigue saliendo la restricción por derechos de autor

Si la IP de salida ya es de China continental y la web sigue mostrando la restricción por derechos de autor, nueve de cada diez veces es que el **IPv6 o el DNS local** del dispositivo se están saltando la línea. Desde septiembre de 2026, los tres métodos de conexión de LeoTun para todo el dispositivo bloquean el IPv6 del lado de la línea; las configuraciones de Hiddify importadas antes de septiembre hay que borrarlas y volver a importarlas escaneando el código QR. Para los pasos de diagnóstico, consulta [IPv6 y DNS son los que se escapan](../troubleshooting/03-ipv6-and-dns-leak.md).

## Verlo en la tele

En las teles y los decodificadores no se puede instalar un cliente, así que hay dos caminos:

1. **El router**: configura en el router la línea hacia China y activa el enrutamiento dividido, y la tele podrá verlo en cuanto se conecte a ese wifi. Se beneficia toda la casa; consulta [Para los mayores de la familia y la tele](../router/04-family-tv-and-router.md).
2. **Enviar la pantalla**: activa la línea hacia China en el móvil y envía la imagen a la tele. Es sencillo, pero el móvil tiene que estar encendido todo el rato.

## Calidad de imagen

El 1080p necesita 5 Mbps estables o más. Si la reproducción va a tirones en la hora punta de la noche, elige una región con el semáforo en verde o cambia de método de conexión; si sigue a tirones, la causa habitual es la banda ancha local. Elegir un punto de entrada cercano y con una línea optimizada hacia China continental funciona mejor que cambiar de plataforma.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-02) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-02) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 15 puntos (unos 15 días del plan Individual), una promoción sin fecha de fin
