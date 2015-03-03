# Multicóptero
###Qué es un multicóptero y cómo funciona

Un multicóptero es un vehículo aéreo mecánicamente sencillo, cuyo movimiento es controlado acelerando o frenando múltiples unidades de motor y hélice, generando un empuje desde abajo.

**Los multicóptero son aerodinámicametne inestables** y requieren un equipo de control a bordo (conocido como controlador de vuelo) para un vuelo más estable. Como resultado, existen "Vuelos por cable" y si el ordenador no está funcionado, el sistema no vuela. El controlador de vuelo combina información de la placa, como giróscopos MEM, acelerómetros (los mismo que existen en los teléfonos móviles) para mantener una estimación precisa de su orientación y posición.

El quadricóptero es el tipo de multicóptero más sencillo, donde cada motor gira en dirección contraria a los dos motores que tiene a su lado ( es decir, los motores en esquinas opuestas al bastidor giran en la misma dirección).

Un quadricóptero puede controlar el *roll* y el *pitch* acelerando dos motores de un lado, y reduciendo la velocidad de los otros dos. Por ejemplo, si un quadricóptero quiere modificar el roll hacia la izquierda, deberá acelerar los motores de la derecha y frenar los dos de la derecha. De forma similar si quieres girar hacia delante, acelera los dos motores traseros y ralentiza los delanteros.

El cóptero gira (conocido com *yaw*) hacia la izquierda o hacia la derecha, acelerando los dos motores que están en diagonal y ralentizando los otros dos.

El movimiento horizontal se lleva a cabo mediante la aceleración/desaceleración temporal de alguno de los motores, para que el vehículo se incline en la dirección deseada y aumente la velocidad de todos los motores para que el vehículo se desplace hacia delante. Normalmente, cuanto más se incline el vehículo, viajará mas rapido.

La altitud se controla acelerando o desacelerando todos los motores al mismo tiempo.


###¿Qué es diferente entre un multicóptero y un UAV/Drone?

**Un multicóptero puede ser un UAV o Drone cuando es capaz de realizar vuelos autónomos**. Normalmente esto significa tomar la información de los acelerómetros y giróscopos, y combinarlos con los datos del barómetro y GPS, por lo que el controlador de vuelo entiende no sólo la orientación, sino también su posición.
