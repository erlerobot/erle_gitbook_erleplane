# Flight mode

There are 14 flight modes available in APM:Plane, 10 of which are regularly used.  You can set these up by doing the following:

+ Turn on your RC transmitter
+ Connect your board to Mission Planner or QGoundControl
+ Go to Flight Modes screen
+ Note as you move your transmitter’s flight mode switch (channel 5) the green highlight bar will move to a different position.
+ Use the drop-down on each line to select the flight mode for that switch position ensuring that at least one switch position is left assigned to Stabilize
+ When finished press the “Save Modes” button.

*Note: You can find more info about this in [Erle-Brain's book](http://erlerobotics.gitbooks.io/erle-robotics-erle-brain-a-linux-brain-for-drones/), in the section belonging to [GCS](http://erlerobotics.gitbooks.io/erle-robotics-erle-brain-a-linux-brain-for-drones/content/en/GCS/README.html) and [RCs](http://erlerobotics.gitbooks.io/erle-robotics-erle-brain-a-linux-brain-for-drones/content/en/RC/README.html).* 

#Modes

###Manual

Regular RC control, no stabilization. All RC inputs are passed through to the outputs. The only ways in which the RC output may be different from inputs are as follows:

* if a configured failsafe or geofence triggers, and ArduPlane takes control
* if the `VTAIL_OUTPUT` option is enabled, then a software VTAIL mixer is applied on the output
* if the `ELEVON_OUTPUT` option is enabled, then a software Elevon mixer is applied on the output

###Fly by Wire A (FBWA)

This is the most popular mode for assisted flying in ArduPlane, and is the best mode for inexperienced flyers. In this mode ArduPlane will hold the roll and pitch specified by the control sticks. So if you hold the aileron stick hard right then the plane will hold it’s pitch level and will bank right by the angle specified in the `LIM_ROLL_CD` option (in centidegrees). It is not possible to roll the plane past the roll limit specified in `LIM_ROLL_CD`, and it is not possible to pitch the plane beyond the `LIM_PITCH_MAX/LIM_PITCH_MIN` settings.

Note that holding level pitch does not mean the plane will hold altitude. How much altitude a plane gains or loses at a particular pitch depends on its airspeed, which is primarily controlled by throttle. So to gain altitude you should raise the throttle, and to lose altitude you should lower the throttle. If you want ArduPlane to take care of holding altitude then you should look at the FlyByWireB mode.

In FBWA mode throttle is manually controlled, but is constrained by the `THR_MIN` and `THR_MAX` settings.

In FBWA mode the rudder is under both manual control, plus whatever rudder mixing for roll you have configured. Thus you can use the rudder for ground steering, and still have it used for automatically coordinating turns.

###Fly by Wire B (FBWB)

The FBWB mode is similar to FBWA, but ArduPlane will try to hold altitude as well. Roll control is the same as FBWA, and altitude is controlled using the elevator. The target airspeed is controlled using the throttle.

To control your altitude in FBWB mode you use the elevator to ask for a change in altitude. If you leave the elevator centred then ArduPlane will try to hold the current altitude. As you move the elevator ArduPlane will try to gain or lose altitude in proportion to how far you move the elevator. How much altitude it tries to gain for full elevator deflection depends on the `FBWB_CLIMB_RATE` parameter, which defaults to 2 meters/second. Note that 2 m/s is quite a slow change, so many users will want to raise `FBWB_CLIMB_RATE` to a higher value to make the altitude change more responsive.

Whether you need to pull back on the elevator stick or push forward to climb depends on the setting of the `FBWB_ELEV_REV` parameter. The default is for pulling back on the elevator to cause the plane to climb. This corresponds to the normal response direction for a RC model. If you are more comfortable with the reverse you can set `FBWB_ELEV_REV` to 1 and the elevator will be reversed in FBWB mode.

Note that the elevator stick does not control pitch, it controls target altitude. The amount of pitch that will be used to achieve the requested climb or descent rate depends on your TECS tuning settings, but in general the autopilot will try to hold the plane fairly level in pitch, and will primarily climb or descend by raising or lowering the throttle. This can be disconcerting for people used to flying in FBWA mode, where you have much more direct control over pitch.

If you have an airspeed sensor then the throttle will control the target airspeed in the range `ARSPD_FBW_MIN` to `ARSPD_FBW_MAX`. If throttle is minimum then the plane will try to fly at `ARSPD_FBW_MIN`. If it is maximum it will try to fly at `ARSPD_FBW_MAX`.

If you don’t have an airspeed sensor then the throttle will set the target throttle of the plane, and ArduPlane will adjust the throttle around that setting to achieve the desired altitude hold. The throttle stick can be used to push the target throttle up beyond what it calculates is needed, to fly faster.

As with FBWA, the rudder is under a combination of manual control and auto control for turn coordination.

You should also have a look at CRUISE mode, as it is generally better than FBWB, especially if there is significant wind. In CRUISE mode the aircraft will hold a ground track as opposed to just levelling the wings when you don’t input any roll with the aileron stick.

###Auto Mode

The AUTOTUNE mode flies in the same way as FBWA, but it does automatic tuning of roll and pitch control gains. Please read the [full documentation on AUTOTUNE](http://plane.ardupilot.com/wiki/flying/tuning/automatic-tuning-with-autotune/) for more details.

###Training

This mode is like training wheels on a bicycle and is ideal for teaching students manual R/C control. If the roll is less the the `LIM_ROLL_CD` parameter than the pilot has manual roll control. If the plane tries to roll past that limit then the roll will be held at that limit. The plane will not automatically roll back to level flight, but it will prevent the pilot from rolling past the limit. The same applies to pitch – the pilot has manual pitch control until the `LIM_PITCH_MIN` or `LIM_PITCH_MAX` limits are reached, at which point the plane won’t allow the pitch to go past those limits.

In training mode the rudder and throttle are both completely under manual control.

###Acro

ACRO (for acrobatic) is a mode for advanced users that provides rate based stabilization with attitude lock. It is a good choice for people who want to push their plane harder than you can in FBWA or STABILIZE mode without flying in MANUAL. This is the mode to use for rolls, loops and other basic aerobatic maneuvers, or if you just want an “on rails” manual flying mode.

To setup this mode you need to set `ACRO_ROLL_RATE` and `ACRO_PITCH_RATE`. These default to 180 degrees/second, and control how responsive your plane will be about each axis.

When flying in ACRO the aircraft will try to hold it’s existing attitude if you have no stick input. So if you roll the plane to a 30 degree bank angle with 10 degrees pitch and then let go of the sticks, the plane should hold that attitude. This applies upside down as well, so if you roll the plane upside down and let go of the sticks the plane will try to hold the inverted attitude until you move the sticks again.

When you apply aileron or elevator stick the plane will rotate about that axis (in body frame) at a rate proportional to the amount of stick movement. So if you apply half deflection on the aileron stick then the plane will start rolling at half of `ACRO_ROLL_RATE`.

So to perform a simple horizontal roll, just start in level flight then hold the aileron stick hard over while leaving the elevator stick alone. The plane will apply elevator correction to try to hold your pitch while rolling, including applying inverse elevator while inverted.

In the current implementation the controller won’t use rudder while the plane is on it’s side to hold pitch, which means horizontal rolls won’t be as smooth as a good manual pilot, but that should be fixed in a future release. This also means that it won’t hold knife-edge flight.

Performing a loop is just as simple – just start with wings level then pull back on the elevator stick while leaving the aileron alone. The controller will try to hold your roll attitude through the loop. You can stop the loop upside down if you like as part of maneuvers such as Immelman turns or cuban eights.

Note that if you are using ACRO mode to try and teach yourself aerobatic flying then it is highly recommended that you setup a geo-fence in case you get disoriented.

**Warning**: It is very easy to stall your plane in ACRO mode, and if you stall you should change to MANUAL mode to recover

* make sure you know the limitations of your airframe, and what the correct stall recovery procedure is. This varies a lot between airframes. Search for stall recovery tutorials for R/C aircraft and read them
* don’t overload your airframe, only fly ACRO mode with a lightly loaded plane
* make sure you have enough airspeed for whatever maneuver you are attempting. Throttle and speed control is completely under manual pilot control in ACRO mode
*practice stall recovery before trying anything too fancy. Make sure you practice when you have plenty of altitude to give you time to try different recovery strategies

It can be a lot of fun flying ACRO mode, but you can also easily stall and crash hard. Automatic stall detection and recovery in autopilots is an area of research, and is not yet implemented in APM:Plane, so if you do stall then recovery is up to you. The best mode for recovery is MANUAL.

###Cruise

Cruise mode is a bit like FBWB, but it has “heading lock”. It is the ideal mode for longer distance FPV flight, as you can point the plane at a distant object and it will accurately track to that object, automatically controlling altitude, airspeed and heading.

The way it works is this:

* If you have any aileron or rudder input then it flies just like FBWB. So it holds altitude until you use the elevator to change the target altitude (at the `FBWB_CLIMB_RATE` rate) and it adjusts airspeed based on throttle
* when you let go of the aileron and rudder sticks for more than 0.5 seconds it sets an internal waypoint at your current location, and projects a target waypoint one kilometre ahead (note that heading lock will only activate if you have GPS lock, and have a ground speed of at least 3 m/s)
* as it flies along it heads for the target waypoint, and constantly updates that target to always be one kilometre ahead, leaving the previous waypoint as the position that you centred the aileron and rudder sticks
* as long as you don’t touch the aileron or rudder, it will run the same navigation system it uses for waypoints, including crabbing, cross-track etc, so it will very accurately hold that ground course even in the face of changing wind conditions

One of the nicer aspects of CRUISE mode is how it handles rudder. If you give it some rudder then the roll controller will keep the wings level, but the plane will yaw with the rudder. So you get a “wings level” turn, allowing you to rotate your flight to point at whatever geographic feature you want to head towards. Then when you let go of the rudder it will head straight for that point.


**Warning**: Make sure you only fly FPV if it is allowed by your countries flight and airspace control rules. Many countries do not allow non line of sight flight without a special operating license.

###Auto

In AUTO mode the follow a mission (a set of GPS waypoints and other commands) set by your ground station configuration. When entering AUTO mode ArduPlane will continue from whatever mission item it was last doing, unless you have reset the mission.

When in AUTO ArduPlane will by default allow the pilot to influence the flight of the plane by using “stick mixing”, which allows for aileron, elevator and rudder input to steer the plane in a way that can override the autopilot control. Whether this is enabled is determined by the `STICK_MIXING` option. By default stick mixing behaves the same as FBWA mode.

+ Warning: “Home” position is always supposed to be your Planes actual GPS takeoff location:
+ It is very important to acquire GPS lock before arming in order for RTL, Loiter, Auto or any GPS dependent mode to work properly.
	* For APM:Plane the home position is the postion of the Plane when you first get GPS lock whether it was armed or not.
	* This means if you execute an RTL in APM:Plane, it will return to the location where it was when it first acquired GPS lock.
	* For APM:Plane: Plug in the battery and let it acquire GPS lock where you want it to return to: (Not the Pits).

###Loiter

In LOITER mode the plane will circle around the point where you started the loiter, holding altitude at the altitude that you entered loiter in. The radius of the circle is controlled by the `WP_LOITER_RAD` parameter, but is also limited by your `NAV_ROLL_CD` limit, and your `NAVL1_PERIOD` navigation tuning.

As with RTL and AUTO mode you can “nudge” the plane while in LOITER using stick mixing, if enabled.

**Warning**: “Home” position is always supposed to be your Planes actual GPS takeoff location:
It is very important to acquire GPS lock before arming in order for RTL, Loiter, Auto or any GPS dependent mode to work properly.
For APM:Plane the home position is the postion of the Plane when you first get GPS lock whether it was armed or not.
This means if you execute an RTL in APM:Plane, it will return to the location where it was when it first acquired GPS lock.
For APM:Plane: Plug in the battery and let it acquire GPS lock where you want it to return to: (Not the Pits).

###Circle

Circle mode is similar to loiter, but doesn’t attempt to hold position. This is primarily meant as a failsafe mode and is the mode that the aircraft will enter by default for 20 seconds when a failsafe event occurs, before switching to RTL.

Circle mode is deliberately a very conservative mode, and doesn’t rely on GPS positioning as it is used when GPS fails. It will do a large circle, The bank angle is set to the `LIM_ROLL_CD` divided by 3, to try to ensure the plane remains stable even without GPS velocity data for accelerometer correction. That is why the circle radius is so large.

Circle mode uses throttle and pitch control to maintain altitude at the altitude where it started circling.

###GUIDED

The GUIDED mode is used when you want the aircraft to fly to a specific point on the map without setting up a mission. Most ground control stations support a “click to fly to” feature where you can click a point on the map and the aircraft will fly to that location when loiter.

The other major use for GUIDED mode is in geo-fencing. When the geo-fence is breached the aircraft will enter GUIDED mode, and head to the predefined geo-fence return point, where it will loiter until the operator takes over.

###Mission Specific Modes

When flying an AUTO mission ArduPlane has some sub-modes that are set using mission items. The two main sub-modes are TAKEOFF and LAND.

+ **TAKEOFF**: Auto takeoff is set by the mission control scripting only. The takeoff mission specifies a takeoff pitch and a target altitude. During takeoff ArduPlane will use the maximum throttle set by the THR_MAX parameter. The takeoff mission item is considered complete when the plane has reached the target altitude specified in the mission.

Before takeoff it is important that the plane be pointing into the wind, and be aligned with the runway (if a wheeled takeoff is used). The plane will try to hold its heading during takeoff, with the initial heading set by the direction the plane is facing when the takeoff starts. It is highly recommended that a compass be enabled and properly configured for auto takeoff, as takeoff with a GPS heading can lead to poor heading control.

If you are using a wheeled aircraft then you should look at the WHEELSTEER_* PID settings for controlling ground steering. If you are hand launching or using a catapult you should look at the TKOFF_THR_MINACC and TKOFF_THR_MINSPD parameters.

+ **LAND**: Auto Land is set by the mission control scripting only. Throttle and altitude is controlled by the autopilot. After getting closer `LAND_FLARE_ALT` meters from the target altitude or `LAND_FLARE_SEC` seconds from the target landing point the plane will “flare” to the `LAND_PITCH_CD` pitch (in centidegrees) and will hold heading for the final approach.

Setting up ArduPlane for reliable auto-takeoff and landing is very airframe dependent, and it is recommended that you first get some experience flying your aircraft in FBWA mode, and be ready to take over control in manual or FBWA mode the first few times you use an automatic takeoff or landing.

You should also look through the complete list of parameters, as there are a lot of parameters that help control takeoff and landing for different situations.


*Note: [Here](http://erlerobotics.gitbooks.io/erle-robotics-erle-brain-a-linux-brain-for-drones/content/en/RC/README.html) you can find how to setup this flight modes in your RC.*
