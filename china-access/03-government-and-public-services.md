# 03 · Usar webs oficiales y de servicios públicos chinos

## Lo que ves

La Plataforma Nacional de Servicios Gubernamentales, las webs de trámites de provincias y ciudades, la oficina tributaria electrónica, las consultas de la seguridad social y del fondo de vivienda (housing provident fund), CHSI (la plataforma oficial de títulos universitarios) y 12306 (venta de billetes de tren): desde el extranjero, o no abren, o abren pero el código de verificación nunca llega o el reconocimiento facial falla.

## Primero averigua en qué capa está el problema

| Síntoma | Causa | Solución |
|---|---|---|
| La página no abre en absoluto o se agota el tiempo de espera | La web solo acepta IP de China continental, o se pierden paquetes en la línea internacional | Cambia a una IP china |
| Abre, pero el código de verificación por SMS nunca llega | El SMS tiene que enviarse a un número de teléfono chino | Conserva una SIM china y activa la itinerancia internacional para recibir SMS |
| El código llega, pero el reconocimiento facial falla | Usas la versión de una tienda de apps extranjera, o es el permiso de la cámara | Instala la edición china de la app y permite el acceso a la cámara |
| Te dice «el entorno de red actual es anómalo» | El control de riesgos ha detectado rasgos de proxy | Vuelve a probar con otra región de entrada, o usa la opción del router (se parece más a una banda ancha doméstica) |

## 12306, caso aparte

12306 es extremadamente sensible a la IP, y desde una IP extranjera puede que ni siquiera abra la página de inicio. Una vez con IP china: para registrarte necesitas un número de teléfono chino, para comprar un billete necesitas un documento de identidad con nombre real y para pagar hace falta una tarjeta bancaria china o Alipay. Necesitas las tres cosas para poder comprar. En los picos de venta (por ejemplo, en vacaciones chinas) además limita la frecuencia de peticiones por IP, así que no abras varias ventanas ni recargues sin parar.

## CHSI y la verificación de títulos

CHSI en sí no es especialmente estricto con las IP extranjeras; el problema principal es la lentitud. Pero sus SMS de verificación también se envían solo a números chinos. Antes de verificar un título, quien estudia en el extranjero debe comprobar primero que su número chino sigue recibiendo SMS.

## Un consejo

Los trámites oficiales suelen surgir solo una o dos veces al año, y buscar una línea a última hora cada vez es un engorro. Dejar configurada la línea hacia China como un punto de entrada fijo y volver a tu configuración habitual al terminar da mucho menos trabajo que configurarlo de nuevo cada vez.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=china-access-03) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=china-access-03) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 4 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
