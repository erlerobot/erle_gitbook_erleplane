#Modo guiado

El modo guiado es una característica de APM:Cóptero para guiar dinámicamente el cóptero al objetivo inalámbricamente usando el módulo de radio telemétrico y la aplicación de la estación de tierra. Esta página te proporcionará la información necesaria para usar el modo guiado.

El modo guiado no es un modo de vuelo tradicional que podría ser asignado a un modo de cambio, como otros modos de vuelo. El modo guidado se activa usando la aplicación de control de tierra (Como el Mission Planner) y el radio de telemetría. Gracias a éste modo, te permitirá mandar órdenes interactivas al cóptero para guiarlo a una localización, haciendo click en el mapa de la estación de control de vuelo en tierra. Una vez que el cóptero haya llegado a su localización deseada, el cóptero revoloteará en dicha posición, esperando al próximo comando de vuelo. El modo **Follow Me** usa el modo Guiado para hacer que el cópero siga al piloto sobre el terreno por el que lo está pilotando.

#### Instrucciones

- Configura tu cóptero en el campo y establece la conexión MAVLink sobre la telemetría inalámbrica entre tu cóptero y tu ordenador.
- Asegurate que tu ordenador portátil funciona, y que tiene el GPS bloqueado.
- Despega en el modo `Stabilize`, y una vez que hayas llegado a una altitud considerble, cambia al mido `Loiter`.
- En el pantalla del mapa de la estación de control de tierra, intenta hacer click derecho en un lugar cercano.
- El vehículo debe volar a la posición deseada, y esperará allí hasta que introduzcas otra localización o a que cambies a otro modo.


**Nota**: No es necesario que configures uno de tus modos de vuelo a `Guided`.