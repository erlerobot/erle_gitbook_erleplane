###Acro Mode

ACRO (for acrobatic) is a mode for advanced users that provides rate based stabilization with attitude lock. It is a good choice for people who want to push their plane harder than you can in FBWA or STABILIZE mode without flying in MANUAL. This is the mode to use for rolls, loops and other basic aerobatic maneuvers, or if you just want an “on rails” manual flying mode.

To setup this mode you need to set [ACRO_ROLL_RATE and ACRO_PITCH_RATE](http://plane.ardupilot.com/wiki/arduplane-parameters/#ACRO_mode_pitch_rate_ArduPlaneACRO_PITCH_RATE). These default to 180 degrees/second, and control how responsive your plane will be about each axis.

When flying in ACRO the aircraft will try to hold it’s existing attitude if you have no stick input. So if you roll the plane to a 30 degree bank angle with 10 degrees pitch and then let go of the sticks, the plane should hold that attitude. This applies upside down as well, so if you roll the plane upside down and let go of the sticks the plane will try to hold the inverted attitude until you move the sticks again.

When you apply aileron or elevator stick the plane will rotate about that axis (in body frame) at a rate proportional to the amount of stick movement. So if you apply half deflection on the aileron stick then the plane will start rolling at half of `ACRO_ROLL_RATE`.

So to perform a simple horizontal roll, just start in level flight then hold the aileron stick hard over while leaving the elevator stick alone. The plane will apply elevator correction to try to hold your pitch while rolling, including applying inverse elevator while inverted.

In the current implementation the controller won’t use rudder while the plane is on it’s side to hold pitch, which means horizontal rolls won’t be as smooth as a good manual pilot, but that should be fixed in a future release. This also means that it won’t hold knife-edge flight.

Performing a loop is just as simple – just start with wings level then pull back on the elevator stick while leaving the aileron alone. The controller will try to hold your roll attitude through the loop. You can stop the loop upside down if you like as part of maneuvers such as Immelman turns or cuban eights.

Note that if you are using ACRO mode to try and teach yourself aerobatic flying then it is highly recommended that you setup a [geo-fence](http://plane.ardupilot.com/wiki/flying/flight-modes/geofencing-3/) in case you get disoriented.

**Warning**: It is very easy to stall your plane in ACRO mode, and if you stall you should change to `MANUAL` mode to recover

* Make sure you know the limitations of your airframe, and what the correct stall recovery procedure is. This varies a lot between airframes. Search for stall recovery tutorials for R/C aircraft and read them
* Don’t overload your airframe, only fly ACRO mode with a lightly loaded plane
* Make sure you have enough airspeed for whatever maneuver you are attempting. Throttle and speed control is completely under manual pilot control in ACRO mode
* Practice stall recovery before trying anything too fancy. Make sure you practice when you have plenty of altitude to give you time to try different recovery strategies

It can be a lot of fun flying ACRO mode, but you can also easily stall and crash hard. Automatic stall detection and recovery in autopilots is an area of research, and is not yet implemented in APM:Plane, so if you do stall then recovery is up to you. The best mode for recovery is MANUAL.