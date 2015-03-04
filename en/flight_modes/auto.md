###Auto Mode

In AUTO mode the follow a mission (a set of GPS waypoints and other commands) set by your ground station configuration. When entering AUTO mode ArduPlane will continue from whatever mission item it was last doing, unless you have reset the mission.

When in AUTO ArduPlane will by default allow the pilot to influence the flight of the plane by using “stick mixing”, which allows for aileron, elevator and rudder input to steer the plane in a way that can override the autopilot control. Whether this is enabled is determined by the [STICK_MIXING](http://plane.ardupilot.com/wiki/arduplane-parameters/#Stick_Mixing_ArduPlaneSTICK_MIXING) option. By default stick mixing behaves the same as FBWA mode.

+ Warning: “Home” position is always supposed to be your Planes actual GPS takeoff location:
+ It is very important to acquire GPS lock before arming in order for RTL, Loiter, Auto or any GPS dependent mode to work properly.
	* For APM:Plane the home position is the postion of the Plane when you first get GPS lock whether it was armed or not.
	* This means if you execute an RTL in APM:Plane, it will return to the location where it was when it first acquired GPS lock.
	* For APM:Plane: Plug in the battery and let it acquire GPS lock where you want it to return to: (Not the Pits).