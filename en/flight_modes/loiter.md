###Loiter Mode

In LOITER mode the plane will circle around the point where you started the loiter, holding altitude at the altitude that you entered loiter in. The radius of the circle is controlled by the `WP_LOITER_RAD` parameter, but is also limited by your `NAV_ROLL_CD` limit, and your `NAVL1_PERIOD` navigation tuning.

As with RTL and AUTO mode you can “nudge” the plane while in LOITER using stick mixing, if enabled.

**Warning: “Home” position is always supposed to be your Planes actual GPS takeoff location:**

	It is very important to acquire GPS lock before arming in order for RTL, Loiter, Auto or any GPS dependent mode to work properly.
	For APM:Plane the home position is the postion of the Plane when you first get GPS lock whether it was armed or not.
	This means if you execute an RTL in APM:Plane, it will return to the location where it was when it first acquired GPS lock.
	For APM:Plane: Plug in the battery and let it acquire GPS lock where you want it to return to: (Not the Pits).
