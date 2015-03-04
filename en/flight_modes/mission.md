#Mission Specific Modes

When flying an AUTO mission ArduPlane has some sub-modes that are set using mission items. The two main sub-modes are TAKEOFF and LAND.

###TAKEOFF

Auto takeoff is set by the mission control scripting only. The takeoff mission specifies a takeoff pitch and a target altitude. During takeoff ArduPlane will use the maximum throttle set by the THR_MAX parameter. The takeoff mission item is considered complete when the plane has reached the target altitude specified in the mission.

Before takeoff it is important that the plane be pointing into the wind, and be aligned with the runway (if a wheeled takeoff is used). The plane will try to hold its heading during takeoff, with the initial heading set by the direction the plane is facing when the takeoff starts. It is highly recommended that a compass be enabled and properly configured for auto takeoff, as takeoff with a GPS heading can lead to poor heading control.

If you are using a wheeled aircraft then you should look at the WHEELSTEER_* PID settings for controlling ground steering. If you are hand launching or using a catapult you should look at the TKOFF_THR_MINACC and TKOFF_THR_MINSPD parameters.

###LAND

Auto Land is set by the mission control scripting only. Throttle and altitude is controlled by the autopilot. After getting closer `LAND_FLARE_ALT` meters from the target altitude or `LAND_FLARE_SEC` seconds from the target landing point the plane will “flare” to the `LAND_PITCH_CD` pitch (in centidegrees) and will hold heading for the final approach.

Setting up ArduPlane for reliable auto-takeoff and landing is very airframe dependent, and it is recommended that you first get some experience flying your aircraft in FBWA mode, and be ready to take over control in manual or FBWA mode the first few times you use an automatic takeoff or landing.

You should also look through the complete list of parameters, as there are a lot of parameters that help control takeoff and landing for different situations.