#Revolotear

El modo revoloteo automáticamente tiende a mantener la posición actual, la altitud y la dirección. El piloto debe volar el cóptero en el modo `Loiter` como si estuviera en el manual. Mientras se sueltan los sticks, continuará manteniendo la posición.

Buena posición del GPS, **una interferencia electromagnética baja** en el compás y **vibraciones leves** todas ellas son importantes a la hora de conseguir un buen rendimiento en el revoloteo.

El modo revoloteo incorpora un controlador de altitud desde el modo AltHold. Los detalles sobre la sintonización de AltHold están en [ésta página](altitude_hold.md).

##Controles
El piloto puede controlar la posición del cóptero con las palancas de control del mando. En AC3.1 (y por encima) debes armar el modo Loiter, pero sólo cuando el GPS haya entrado en el bloqueo 3D y que **HDOP haya bajado a 2.0 o niveles menores**.

La velocidad máxima horizontal del cóptero durante el modo `Loiter` se puede ajustar con el parámetro de `Loiter Speed` (**WPNAV_LOIT_SPEED**). El valor se expresa en cm/s, por lo cual 500 = 5m/s. La aceleración máxima durante el modo `Loiter` siempre es 1/2 de la velocidad del modo revoloteo.

El valor del PID de `Loiter` se utiliza para convertir el error de la posición horizontal (ej. diferencia entre la posición deseada y la posición actual). **No es necesario reajustar éste parámetro**.

Los valores del PID de `Loiter` se utilizan para convertir la velocidad deseada hacia el objetivo, con una aceleración deseada. El resultado de la velocidad deseada, se convierte en un ángulo de inclinación que luego pasará por el mismo controlador angular usado por [Stabilize mode](stabilization.md). **Normalmente no se suelen ajustar éstos parámetros**.


## Problemas comunes

Como se ha mencionado anteriormente, el modo revoloteo incorpora un controlador de altitud desde [AltHold mode](altitude_hold.md)

1. El vehículo despega en la dirección equivocada cuando el modo `Loiter` está en ejecución. La causa es la misma que en #1, excepto que el error del compás sea mayor a 90 grados. Por favor, mira las sugerencias de arriba para resolver éste problema. 

2. El vehículo está revoloteando con normalidad, y de repente, cambia a una dirección incorrecta. Normalmente ésto se ocasiona por un fallo en el GPS. No hay ninguna protección segura que funcione al 100% contra ésto, lo que significa que el piloto debe estar preparado para un control manual. Mas allá de asegurar un buen GPS HDOP antes de despegar, siempre será bueno y puede ayudar a reducir los parámetros GPSGLITCH_RADIUS y/o GPSGLITCH_ACCEL para acercarlos hacia la dirección del fallo.