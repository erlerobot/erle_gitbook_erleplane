# Armando los motores
Antes de armar los motores, **asegúrate de que todas las personas y objetos están alejados de las hélices**. 

Luego haz lo siguiente:
- Enciende el transmisor.
- Conecta la bateria LiPo. Las luces rojas y azules deben parpadear durante unos segundos mientras los giróscopos se calibran. *No muevas el multicóptero durante el proceso*.
- El pre-arme comprueba que se ejecuta automáticametne y si hay algún problema en APM2.x la luz roja de armado se encenderá dos veces.
- Si estas pensando en usar el autopiloto (es decir los modos Loiter, RTL, Drift, Auto o Guiado) debes esperar 30 segundos hasta que el GPS obtenga el bloqueo 3d. Esto dará tiempo al GPS para obtener la posición.
- Arma los motores sosteniendo el *throtlle* abajo y el *rudder* a la derecha durante 5 segundos. Tomará aproximadamente 5 segundos la primera vez que el multicóptero es armado y que los giróscopos y el barómetro son reiniciados. No mantenga el *rudder* durante mucho tiempo (>15 segundos) o entrarás en el modo *AutoTrim*.
- Una vez armado, el luz roja debe estar solida y las hélices comenzaran a girar lentamente. La velocidad de giro puede ser ajustada con el parámetro **MOT_SPIN_ARMED**.
- Mueve el *throtlle* para despegar.


#Desarmando los motores.
Para desarmar los motores realiza los siguientes pasos:
- Comprueba que el modo de vuelo es: **Stabilize**, **ACRO**, **AltHold** o **Loiter**
- Mantén el *throtlle* al mínimo y el *rudder* a la izquierda durante 2 segundos.
- La luz roja de armado debe parpadear en APM2.
- Desconecta la bateria LiPo.
- Apaga el radiocontrol

**NOTA: Solo puedes armar y desarmar en los modos Stabilize, ACRO, AltHold o Loiter** 

**NOTA: Si dejas el *throtlle al mínimo durante 15 segundos en alguno de los modos anteriores, los motores de desarmarán automáticamente**