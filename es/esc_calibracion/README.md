# Calibración ESC 

http://copter.ardupilot.com/wiki/initial-setup/esc-motor/

Los controladores electrónicos de velocidad son los responsable de regular los motores a la velocidad deseada por el autopiloto. La mayoría de los ESCs necesitan calibrarse para conocer los valores máximos y minimos de *PWM* que el controlador de vuelo enviará. Esta página proporciona información sobre como calibrar los ESCs.

#### Calibrando todos a la vez

######Chequeo de seguridad!

Antes de calibrar los ESCs, por favor, asegúrate de que tu multicóptero no tiene puestas las hélices, que APM no esté conectado a tu ordenador vía USB y que la batería LIPO está desconectada.

![no-props](../img/calibration/no-props.png)
![no-usb](../img/calibration/noUSB.png)

- Enciende el transmisor y pon el *stick* del *throttle* en el valor máximo.

- Conecta la batería (LiPo). Los LEDs rojo, azul y amarillo del autopiloto, se iluminarán en un patrón cíclico. Esto significa que está listo para entrar en el modo calibración de los ESC la próxima vez que te conectes.

![battery](../img/calibration/Connect-Battery.jpg)

- Con el *stick* del *throttle* todavía en el valor máximo, desconecta y vuelve a conectar la bateria.

![dis-battery](../img/calibration/Disconnect-Battery.jpg)
![battery](../img/calibration/Connect-Battery.jpg)

- Ahora el autopiloto está en el modo calibración de ESC. (Los LEDs rojo y azul de APM tiene que estar parpadenado de forma alterna, como un coche de policía).

- Espera a que los ESCs emitan un tono musical, el número de pitidos que indican el número de celdas que posee la batería (es decir, 3 para 3S, 4 para 4S) y adicionalmente dos pitidos para indicar que el valor máximo del *throtlle* ha sido capturado.

- Pon el *stick* del *throtlle* a su posición mínima.

- Los ESCs deben emitir un tono largo indicando que el valor mínimo del *throtlle* ha sido capturado y la calibración ha sido completada.

- Si se escucha un tono largo indicando que la calibración ha sido completada, ahora los ESC están *en funcionamiento*, y si mueves el *throtlle* los motores deben girar. Testea que los motores giran, moviendo levemente el *throtlle* y devolviéndolo a la posición mínima.

- Leva el *throtlle* a su valor mínimo y desconecta la bateria para salir del modo calibración de ESC.
