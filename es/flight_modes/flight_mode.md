#Modo de vuelo

Existen 14 modos de vuelo diferentes en APM: Cóptero, 10 de ellos son normalmente usados. Puedes establecerlo haciendo lo siguiente:

+ Enciende el transmisor RC
+ Conecta tu placa a Mission Planner o a QGroundControl
+ Ve a la pantalla Modos de Vuelo
+ Cambiando el modo de vuelo de tu transmisor (canal 5) la barra de luz verde se moverá una posición diferente.
+ Usa el desplegable en cada línea para seleccionar el modo de vuelo, para que cada posición del interruptor del mando esté al menos en una posición asignada a Stabilize.
+ Cuando acabe, pulsa el botón "Save Modes"

###Modos
+ **Stabilize**: El modo 'Estabilizador' te permite volar el vehículo manualmente, pero autonivela los niveles de 'roll' y 'pitch'.
+ **Altitude hold mode**: El modo de mantenimiento de altitud, el cóptero mantiene una altitud constante, permitiendo al piloto maniobrar el 'roll', 'pitch' y 'yaw'.
+ **Loiter**: El modo 'Merodear' automaticamente intenta mantener la misma posición, los grados y la altitud. El piloto debe volar en el modo 'Loiter' como si fuera 'manual'.
+ **RTL Mode**: En el modo 'Vuelta al lugar de lanzamiento (RTL)' el cóptero navega desde su actual posición, para volar alrededor de su zona de lanzamiento. El comportamiento del modo RTL se puede ajustar por varios parámetros reajustables.
+ **Auto Mode**: En el modo automático, el cóptero seguirá una misión de vuelo programada, almacenada en el autopiloto, que está hecha de comandos de navegación (ej. caminos) y 'hace' comandos (ej. comandos que no afectan la localización del cóptero, incluyendo el disparador de fotos de la cámara).
+ **Acro**: El modo acro (Modo de nivel) usa los sticks de RC para controlar la velocidad angular del cóptero. Suelta los sticks y el vehiculo mantendrá la altitud actual, y no volverá al nivel. El modo acro es útil para las acrobacias como los flips o rolls, o FPV cuando los controles rápidos y llanos son deseados.
+ **Sport**: El modo deportivo también es conocido como 'Velocidad controlada a estabilizar' más el bloqueo de altitud. Esto fue diseñado para que fuera útil para volar FPV y para grabar en lugares complicados, porque puedes establecer el vehículo an un determinado angulo y mantendrá ese ángulo.
+ **Drift**: El modo 'flotar' permite al usuario volar el multicóptero como si fuera un avión, en tiempos automáticos coordinados.
+ **Guided Mode**: El modo guiado es una prestación de APM: El cóptero es guiado inalámbricamente a una localización, usando un módulo radio de telemetría y una aplicación de estación de tierra.
+ **Circle Mode**: El drone orbitará en circulos sobre el punto de interés, con la cara del vehículo apuntando al centro.
+ **Position Mode**: El modo de posición es el mismo que el modo 'Loiter', pero con el control manual del 'throttle'. Esto significa que en el modo posición, el cóptero mantiene una localización y un grado consistente, mientras permite al operador controlar el 'throttle' manualmente.
+ **Land Mode**: El cometido del modo aterrizaje es realizar un aterrizaje en tierra.
+ **Follow me mode**: Es posible hacer que el cóptero siga tus movimientos, usando un radio de telemetría y una estación de tierra. El planeador de misiones para laptops Windows, Planeador APM para laptops OS X, y DroidPlanner para dispositivos Android que normalmente soportan Follow Me; sin embargo, es más facil usar un teĺéfono móvil o una tablet en tu estación de tierra Follow Me.
+ **Simple and Super Simple Modes**: Los modos 'Simple' y 'Super Simple' se usan en combinación con los modos Stabilize, Sport, Drift y Land Flight. Estos permiten al piloto controlar el movimiento del cóptero desde el punto de visión del piloto, independientemente de donde se sitúe el piloto.

###Dependencia GPS

Requiere que el GPS se bloquee antes del despegue:

+ [Loiter (& OF_loiter)](loiter.md)
+ [RTL (Return-to-Launch)](RTL.md)
+ [Auto](auto.md)
+ [Guided](guided.md)
+ [Drift]()
+ [Position](position.md)
+ [Follow Me](followme.md)
+ [Circle]()

No requiere que el GPS se bloquee:

+ [Stabilize](Stabilization.md)
+ [Alt Hold](altitude_hold.md)
+ [Acro]()
+ [Sport]()
+ [Land](land.md)
+ [Autotune](autotune.md)