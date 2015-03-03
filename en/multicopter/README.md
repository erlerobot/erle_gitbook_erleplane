# MultiCopter
###What is a MultiCopter and How Does it Work

A multicopter is a mechanically simple aerial vehicle whose motion is controlled by speeding or slowing multiple downward thrusting motor/propeller units.

**MultiCopters are aerodynamically unstable** and absolutely **require an on-board computer** (aka flight controller) for stable flight.  As a result, they are “Fly by Wire” systems and if the computer isn’t working, you aren’t flying.  The flight controller combines data from small on-board MEMs gyroscopes, accelerometers (the same as those found in smart phones) to maintain an accurate estimate of it’s orientation and position.

The quadcopter is the simplest type of multicopter, with each motor/propeller spinning in the opposite direction from the two motors on either side of it (i.e. motors on opposite corners of the frame spin in the same direction).

A quad copter can control it’s roll and pitch rotation by speeding up two motors on one side and slowing down the other two.  So for example if the quad copter wanted to roll left it would speed up motors on the right side of the frame and slow down the two on the left.  Similarly if it wants to rotate forward it speeds up the back two motors and slows down the front two.

The copter turns (aka “yaw”) left or right by speeding up two motors that are diagonally across from each other, and slowing down the other two.

Horizontal motion is accomplished by temporarily speeding up/slowing down some motors so that the vehicle is leaning in the direction of desired travel and increasing the overall thrust of all motors so the vehicle shoots forward.  Generally the more the vehicle leans, the faster it travels.

Altitude is controlled by speeding up or slowing down all motors at the same time.

###What is the difference between a MultiCopter and a UAV/Drone?

**A multicopter becomes a UAV or Drone when it is capable of autonomous flight**. Normally this means taking the accelerometer and gyro information and combining it with barometer and GPS data so the flight controller understands not only it’s orientation but also it’s position.

