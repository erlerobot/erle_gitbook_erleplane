# Vuelta a lugar de depegue (RTL)

En el modo vuelta a lugar de despegue, el cóptero vuela desde su actual posición, merodeando cerca de su posición inicial. El comportamiento del modo RTL puede ser controlado por diferentes parámetros ajustables. Esta página describe como usar y customizar el modo RTL.

Cuando el modo RTL está seleccionado, el cóptero voverá a la zona de lanzamiento. Primero, el cóptero comenzará a elevarse a RTL_ALT, antes de volver a su posición inicial o mantenener la altitud actual si la posición en ése momento es mayor que RTL_ALT. El valor predeterminado para RTL_ALT es 15m.

RTL es un GPS de movimiento dependiente, por lo cual, es esencial que el bloqueo del GPS esté activado antes de entrar en éste modo. Antes de armarlo, ten seguro que los LEDs azules del APM están encendidos y no parpadean. Para un GPS sin compás, el LED estará azul cuando el bloqueo del GPS se haya activado. Para el módulo Compás+GPS, el LED azul parpadeará cuando el GPS esté bloqueado.

RTL mandará al cóptero volver a la posición inicial, es decir, volverá a la posición donde fué armado. **Por lo tanto, la posición de despegue siempre será la localización actual del GPS del cóptero, sin obstrucción y lejano de la gente**. Para APM: Cóptero si tienes el bloqueo de GPS y después ARM tu cóptero, la posición de inicio es la localización en la que el cóptero estaba cuando estaba armado. Esto significa que si ejecutas un RTL en APM: Cóptero, volverá a la posición donde fue armado.

**Precaución**: En el modo RTL, el controlador de vuelo usa un barómetro donde mide la presión del aire, como importancia primaria para determinar la altitud ("Presión de Altitud") y si la presión del aire está cambiando en tu área de vuelo, el cóptero seguirá el cambio de presión del aire antes que la altitud actual (a no ser que estés a 6 metros del suelo y tengas un SONAR operativo)

## Opciones

- *RTL_ALT*: La altitud mínima a la que el cóptero se moverá antes de volver a la zona de lanzamiento.
 - Establece a cero para volver a la altitud actual.
 - La altitud de retorno puede ser de 1 a 8000 centímetros. 
 - La altitud predeterminada de retorno son 15 metros (1500).
- *RTL_ALT_FINAL*: La altitud del cóptero cambiará a la posición final de "Volviendo a la zona de despegue" o despues de completar la misión.
 - Establece a cero para que el cóptero aterrize automáticamente.
 - El retorno de altitud final debe ser ajustado de 0 a 1000 centímetros.
- *RTL_LOIT_TIME*: Tiempo en milisegundos para sobrevolar la posición de `despegue` antes de que comienze el descenso final.
 - El tiempo de *sobrevuelo* se puede ajustar de 0 a 60000 milisegundos.
- *WP_YAW_BEHAVIOR*: Establece cómo el autopiloto controla el `yaw` durante `Misiones` y RTL.
 - 0 = Nunca cambia el yaw
 - 1 = Enfrenta el siguente punto del recorrido incluyendo apuntar al punto de despegue durante RTL
 - 2 = Enfrenta el siguiente punto del recorrido excepto para RTL (durante el RTL, el vehículo continuará apuntando como en la última dirección)
- *LAND_SPEED*: El decrecimiento de velocidad para la última fase del aterrizaje en centímetros por segundo.
 - La velocidad del aterrizaje es ajustable de 20 a 200 centímetros por segundo.

 ## Notas

- Otros ajustes de navegación también tienen influencia sobre el modo RTL:
 - WPNAV_ACCEL
 - WPNAV_LOITER_SPEED
 - WPNAV_SPEED_DN
 - WPNAV_SPEED_UP
- Para usar los RTL, el bloqueo del GPS debe estar activado (El LED azul del GPS y el LED azul del APM deben estar fijas, no parpadeantes) antes de el armado y el despegue para establecer la posición de la zona de lanzamiento.
- Ten en cuenta que el LED del módulo del GPS UBLOX, está apagado mientras se obtiene la localización de los satélites, y que está parpadeando cuando los satélites han sido adquiridos.
- El aterrizar y rearmar el cóptero, reseteará el lugar predeterminado de despegue, lo que es una buena característica para pilotajes en terrenos de vuelo.
- Si se desactiva por primera vez durante el vuelo, el lugar de despegue se establecerá en el lugar donde se desactivó.
- Si estableces ALT_HOLD_RTL a un número que no sea 0, irá y mantendrá esa altitud durante su regreso.
- RTL usa waypoint_speed (velocidad en el punto de ruta) para determinan la velocidad.
- Una vez que el cóptero ha llegado al lugar de despegue, el cóptero entrará en el modo `Loiter`, se acaba el tiempo (AUTO_LAND), después aterriza.
- Para prevenir el auto aterrizaje, simplemente cambia los modos con la palanca de control a `limpiar el temporizador de aterrizaje`, y continúa con tu vuelo.
- La palanca de `throttle` controla la altitud mientras vuelve a la base o sobrevuela la zona sobre el lugar de despliegue, y no los motores directamente.
