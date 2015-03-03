# Modo Sígueme

El modo **follow me** hace posible que el cóptero te siga allí donde te mueves, usando un radio de telemetría y una estación de control en tierra. Será mas fácil usarlo si disponemos de un teléfono o una tablet. El modo sígueme usa el APM: una característica dinámica de control de punto de paso del drone, y comandos de telemetría MAVLink.

#### Lo que vas a necesitar:
 - Un APM: Un cóptero con telemetría
 - Un teléfono u ordenador portátil
 - Una señal de GPS en tu estación de control en tierra.

#### Instrucciones
- Configura tu APM: El cóptero en el suelo y establece una conexión con MAVLink sobre una telemetría inalámbrica.
- Establece uno de tus modos de vuelo a `Loiter`.
- Ten en cuenta que el dispositivo GPS está conectado.
- Despega, y una vez en el aire, cambia a modo `Loiter`. (A la altitud suficiente para tener seguro que mientras te está siguiendo, no te esté atacando, eso será una buena idea).
En la pantalla de datos de la estación de control de tierra, intenta hacer click en un lugar cercano. Si funciona, estás listo para probar el modo `Follow Me`
 - Si has establecido la altitud a 5 pies, puede ser una buena idea para ver si puede funcionar.
 - Como se ha mencionado anteriormente, una altitud suficiente para prevenir cualquier tipo de daño va a ser bueno.
 - Seriamente ésta es una buena capacidad, pero por seguridad es realmente importante cuando se usa el modo `Follow Me`, especialmente cuando se usa un multicóptero de hojas del motor sin ningúna protección.

**Precaución**: Como en todos los otros modos en los que el autopiloto es responsable de mantener la altitud (Loiter, AltHold), el barómetro se utiliza en el cálculo de la altitud, significando que puede moverse durante su vuelo, y que el cóptero seguirá los cambios de presión del aire mejor que la actitud actual por encima del suelo.