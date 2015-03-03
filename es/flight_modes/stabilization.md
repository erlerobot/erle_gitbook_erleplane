# Modo estable

El modo estable te permite volar tu vehículo manualmente, pero los ejes de `roll` y `pitch` se autonivelan.

Si estás aprendiendo a volar, prueba **AltHold** o **Loiter** en lugar de **Stabilize**. Tendrás menos accidentes si no tienes que concentrarte en varios controles a la vez. Siempre cambia al modo manual como `Stabilize` si el autopiloto falla al controlar el vehículo. **Mantener el control de tu cóptero es tu responsabilidad**.

+ El control de entrada del `roll` y el `pitch` inclina el ángulo del cóptero. Cuando el piloto suelte las palancas de `roll` y `pitch`, el vehículo se levelará automáticamente.
+ El piloto necesitará comandos de `pitch` y `roll` para hacer que el vehículo se mantenga en su sitio aunque sea empujado por el viento.
+ La entrada del `yaw` del piloto controla la diferencia en el cambio de ángulo en el cabezal del cóptero. Cuando el piloto suelte la palanca de `yaw`, el vehículo mantendrá el ángulo de la cabecera.
+ La entrada del `throttle` controla la media de la velocidad del motor, ésto quiere decir que el ajustamiento constante del acelerador es necesario para mantener la altitud. Si el piloto mueve la palanca del `throttle` al mínimo, los motores irán a la velocidad mínima (MOT_SPIN_ARMED) y si el vehículo está volando, perderá la posición y caerá.
+ La aceleración enviada a los motores es automáticamente ajustada basándose en la inclinación del vehículo (ej. se incrementa cuanto más se incline el vehículo) para reducir la compensación que el piloto debe hacer en cada cambio de la actitud del vehículo.

#Problemas comúnes
+ El nuevo cóptero se voltea inmediatamente después del despegue. Esto suele pasar cuando el orden del motor es incorrecto o las cuchillas giran en la dirección equivocada o usan hélices inapropiadas (sentido horario ó antihorario).
+ El cóptero siempre tiende a volar en una dirección incluso si hay un entorno sin corrientes de aire. Prueba `SaveTrim` o `AutoTrim` para nivelar el cóptero.
+ Flips repentinos durante el vuelo. Esto es normalmente ocasionado por fallos mecánicos en el motor o los ESC.