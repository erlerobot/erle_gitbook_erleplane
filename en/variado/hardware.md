# Hardware

![](https://erlerobotics.com/blog/wp-content/uploads/2014/10/IMG_6399.jpg)

The following sections will describe the different hardware components involved in [Erle-copter](http://erlerobotics.com/blog/erle-copter), an educational drone.

###What is a multicopter and how does it work

A multicopter is a mechanically simple aerial vehicle whose motion is controlled by speeding or slowing multiple downward thrusting motor/propeller units.

MultiCopters are **aerodynamically unstable** and absolutely **require an on-board computer** (aka flight controller) for stable flight.  As a result, they are _fly by wire_ systems and if the computer isn’t working, you aren’t flying.  The flight controller combines data from small onboard gyroscopes, accelerometers and magnetometers (pretty much the same technology as those found in smart phones) to maintain an accurate estimate of it’s orientation and position.

The **quadcopter** is the simplest type of multicopter, with each motor/propeller spinning in the opposite direction from the two motors on either side of it (i.e. motors on opposite corners of the frame spin in the same direction).

A quadcopter can control it’s roll and pitch rotation by speeding up two motors on one side and slowing down the other two.  So for example if the quad copter wanted to roll left it would speed up motors on the right side of the frame and slow down the two on the left.  Similarly if it wants to rotate forward it speeds up the back two motors and slows down the front two.

The copter turns (aka “yaw”) left or right by speeding up two motors that are diagonally across from each other, and slowing down the other two.

Horizontal motion is accomplished by temporarily speeding up/slowing down some motors so that the vehicle is leaning in the direction of desired travel and increasing the overall thrust of all motors so the vehicle shoots forward.  Generally the more the vehicle leans, the faster it travels.

Altitude is controlled by speeding up or slowing down all motors at the same time.

###Multicopter or a drone UAV/Drone?

**A multicopter becomes a UAV (or _drone_) when it is capable of autonomous flight**. Normally this means taking the accelerometer and gyro information and combining it with barometer and GPS data so the flight controller understands not only it’s orientation but also it’s position.

Erle-copter is a multicopter that thanks to its flight computer and onboard sensors has the ability make autonomous flights there, a drone.
