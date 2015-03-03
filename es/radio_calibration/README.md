# Calibración del radiocontrol

http://copter.ardupilot.com/wiki/initial-setup/configuring-hardware/#Calibrate_radio_control

Enciende el radiocontrol. Verifica que el transmisor está conectado con el multicóptero y los *joysticks* estén en su sitio.

![radiocontroler](../img/calibration/radio_setup1.png)

#### Modos
- **Modo 1**: El *stick* izquierdo controlará el *pitch* y *yaw*. El *stick* derecho controlará el *throttle* y el *roll*
- **Modo 2**: El *stick* izquierdo puede controlar el *throttle* y *yaw*. El *stick* derecho controlará el *pitch* y el *roll*.

Para cualquier tipo de transmisor, el interruptor de 3 posiciones  debe estar conectado al canal 5 para controlar los distintos modos de vuelo.

Opcionalmente el canal 6 del transmisor puede ser configurado para realizar ajustes durante el vuelo. El canal 7 y 8 se pueden utilizar para el control de funciones auxiliares. Por ejemplo, para controlar el gimbal.

Mueve las palancas de control y los interruptores de su transmisor a los límites de recorrido. Su transmisor debe realizar los siguiente cambios:
- **Canal 1**: low = izquierda roll , high = derecha roll.
- **Canal 2**: low = pitch arriba, high=pitch abajo back.
- **Canal 3**: low = throttle abajo (off), high = throttle arriba.
- **Canal 4**: low = izquierda yaw, high = derecha yaw.
