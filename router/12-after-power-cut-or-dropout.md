# 12 · ¿El router se recupera solo tras un corte de luz o de conexión?

Quien haya montado alguna vez un router con VPN por su cuenta seguramente lo ha vivido: un corte de luz, o una caída breve de la banda ancha, y tras el reinicio todo parece normal, pero el túnel no vuelve hasta que entras en la página de administración y lo configuras otra vez.

## La respuesta corta

Sí, se recupera solo. Tras un corte de luz y el reinicio, una caída de la banda ancha o un corte del túnel en plena sesión, el firmware vuelve a conectar por sí mismo. Sin entrar en la página de administración y sin volver a iniciar sesión.

## Cómo lo hace

El firmware tiene un comprobador funcionando todo el tiempo que revisa el túnel más o menos cada medio minuto. Cuando ve que el túnel ha caído, vuelve a conectar y restablece el enrutamiento dividido.

Durante el breve intervalo hasta que el túnel vuelve, las webs chinas siguen funcionando. La casa no se queda sin internet solo porque el túnel aún no esté arriba.

Tu configuración también se recuerda: la región, el modo de enrutamiento dividido y el interruptor «Seleccionar automáticamente la línea más rápida» se conservan tras un reinicio o una reconexión. Si desactivaste el enrutamiento dividido, sigue desactivado.

## Qué pasa en cada caso

| Lo que ocurrió | Después |
|---|---|
| Vuelve la luz tras un corte | El router arranca y el túnel se reconecta solo |
| La banda ancha cae y vuelve | El túnel se reconecta en cuanto vuelve la línea |
| El túnel se corta en plena sesión | El comprobador lo detecta y vuelve a conectar |
| La cuenta caduca | El tráfico deja de pasar por el túnel y la red de casa sigue funcionando. Tras renovar se reanuda solo, sin volver a iniciar sesión |
| Cambiamos la dirección de un servidor | El router la sigue por sí mismo. No hay nada que reconfigurar |

## ¿Sigue sin volver al cabo de unos minutos? Revisa esto

1. **¿Funciona la propia banda ancha?** Abre una web china. Si falla, el problema está en la línea o en el módem, no en el túnel.
2. **¿Ha caducado la cuenta?** El túnel no conecta tras el vencimiento. Inicia sesión en la web y compruébalo.
3. **Prueba otra región.** Cambia de región en la página de administración. A veces una región tiene un problema temporal.
4. **Reinicia el router.** Desenchúfalo, espera diez segundos y vuelve a enchufarlo.
5. Si nada de eso funciona, envía al soporte una captura del estado que muestra la página de administración.

## El primer arranque tras instalar el firmware

El primer arranque es más lento de lo normal: el firmware busca actualizaciones de componentes y detecta el país para ajustar la potencia inalámbrica. **Conecta un cable de red para ese primer arranque.** Que el wifi vaya flojo antes de que haya estado en línea una vez es normal.

## Preguntas frecuentes

**¿Sirve donde hay cortes de luz frecuentes?** Sí. Vuelve a conectar cada vez que regresa la luz.

**¿Tengo que reiniciar el router periódicamente?** No.

**¿Las actualizaciones de componentes cortarán mi conexión?** No. Las actualizaciones se comprueban y descargan al arrancar y se aplican en el siguiente arranque. El router no se reiniciará mientras lo estás usando.

---
Elaborado por el equipo de [LeoTun](https://www.leotun.com/es?utm_source=github&utm_content=router-12) · ¿Dudas? Mira la [página de contacto](https://www.leotun.com/es/contact?utm_source=github&utm_content=router-12) (allí están los grupos, el correo y el soporte) · Regístrate y pruébalo gratis 24 horas; invita a un amigo que pague y cada uno recibirá 20 días del plan Individual, una promoción sin fecha de fin
