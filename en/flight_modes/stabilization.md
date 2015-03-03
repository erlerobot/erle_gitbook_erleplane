# Stabilize mode

Stabilize mode allows you to fly your vehicle manually, but self-levels the roll and pitch axis.

If you’re learning to fly, try **Alt Hold** or **Loiter** instead of **Stabilize**. You’ll have fewer crashes if you don’t need to concentrate on too many controls at once. Always switch into a `manual mode` such as stabilize if the autopilot fails to control the vehicle. **Maintaining control of your copter is your responsibility**.

+ Pilot’s roll and pitch input control the lean angle of the copter.  When the pilot releases the roll and pitch sticks the vehicle automatically levels itself.
+ Pilot will need to regularly input roll and pitch commands to keep the vehicle in place as it is pushed around by the wind.
+ Pilot’s yaw input controls the rate of change of the heading.  When the pilot releases the yaw stick the vehicle will maintain it’s current heading.
+ Pilot’s throttle input controls the average motor speed meaning that constant adjustment of the throttle is required to maintain altitude.  If the pilot puts the throttle completely down the motors will go to their minimum rate (MOT_SPIN_ARMED) and if the vehicle is flying it will lose attitude control and tumble.
+ The throttle sent to the motors is automatically adjusted based on the tilt angle of the vehicle (i.e. increased as the vehicle tilts over more) to reduce the compensation the pilot must do as the vehicle’s attitude changes.

#Common problems
+ New copter flips immediately upon take-off.  This is usually caused by the motor order being incorrect or spinning in the wrong direction or using an incorrect propeller (clockwise vs counter-clockwise).
+ Copter always tends to fly in one direction even in a windless environment.  Try SaveTrim or AutoTrim to level the copter.
+ Sudden flips during flight.  This is nearly always caused by mechanical failures of the motor or ESCs.

