# Arming the motors
Before arming the motors, **make sure all people and objects are clear of the propellers**. Then do the following:
- Turn on your transmitter
- Plug in your LiPo battery.  The red and blue lights should flash for a few seconds as the gyros are calibrated. **Do not move the copter**.
- The pre-arm checks will run automatically and if any problems are found an APM2.x will double blink the red arming light.
- If you are planning on using the autopilot (i.e. Loiter, RTL, Drift, Auto or Guided modes) you should wait for 30 seconds after the GPS has gotten 3d lock.  This will give the GPS position time to settle.  On APM2 the GPS lock is indicated by the blue LED going solid.
- Arm the motors by holding the throttle down, and rudder right for 5 seconds.  It takes approximately 5 seconds the first time the copter is armed as it re-initialises the gyros and barometer.  Do not hold the rudder right for too long (>15 seconds) or you will begin the AutoTrim feature.
- Once armed, the red arming light should go solid and the propellers will begin to spin slowly.  The speed they spin can be adjusted with the **MOT_SPIN_ARMED** parameter.
- Raise the throttle to take-off.




# Disarming the motors
To disarm the motors do the following:
- Check that your flight mode switch is set to **Stabilize**, **ACRO**, **AltHold** or **Loiter**
- Hold throttle at minimum and rudder to the left for 2 seconds
- The red arming light should start flashing on the APM2
- Disconnect the Lipo battery
- Turn off your transmiter

**Note: you can only arm or disarm in Stabilize, ACRO, AltHold and Loiter mode.**

**Note: if you leave the throttle at minimum for 15 seconds while in any of the above modes the motors will automatically disarm.**
