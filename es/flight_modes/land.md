# Tierra
La función del modo `LAND` es de llevar al cóptero hacia abajo.

+ **Desciende a 10 metros** (o hasta que el sonar note algo debajo del cóptero) usando un controlador regular `Altitude Hold`, en el que descenderá a la velocidad retenida en el parámetro `WPNAV_SPEED_DN`, que puede ser modificado.
+ **Debajo de 10 metros** el cóptero debería descender al valor especificado en `LAND_SPEED`, que por defecto es 50cm/s.
+ Al alcanzar el suelo, el cóptero apagará automáticamente los motores y desarmará el cópero si el `throttle` del piloto está al minimo.

En el siguiente gráfico, verás el comportamiento del modo aterrizaje. Cuando el fondo esté de color rojo, el cóptero está colando en el modo `altitude hold` y si el fondo es de color azul, significa que el cópero está aterrizando. La línea azul representa la altitud deseada. Cuando el modo aterrizaje comienza, la altitud deseada empieza a descender.

![land](../erleimg/LAND/land.png)


**NOTAS**:
+ Si el vehículo no tiene el bloqueo de GPS, el control horizontal estará como en el modo stabilize, así que el piloto podrá controlar la inclinación del `roll y el pitch` del cóptero.
+ Si el vehículo tiene el bloqueo de GPS, el controlador de vuelo intentará controlar su posición horizontal, pero el piloto podrá ajustar el objetivo de la posición horizontal sólamente con el modo `Loiter`.

**Precaución**

En cualquier modo basado en `AltHold`. Si las operaciones de tu cóptero son erróneas cuando estás cerca del suelo o aterrizando, probablemente tengas el controlador de vuelo situado como su barómetro (altímetro) está siendo afectado por **la presión creada por las corrientes de aire del motor, que son generadas contra el suelo**.
+ Esto se puede observar fácilmente en el Altímetro, leyendo los registros y mirando si se clava u oscila cuando está cerca del suelo.
+ Si es un problema, mueve el controlador de vuelo fuera de las corrientes generadas por las hélices de los motores, o protégelo con un recinto ventilado.
El éxito de vuelo se verificará mediante los registros de vuelo.