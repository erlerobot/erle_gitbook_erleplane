###Stabilize Mode

RC control with simple stabilization. If you let go of the sticks then ArduPlane will level the plane. This is a bit like flying a plane with a lot of dihedral. You will find that while it is possible to do maneuvers like rolls and loops in stabilize mode, the tendency of the plane to right itself will make these maneuvers difficult. For people wanting the plane to mostly fly itself, with the pilot just telling it where to fly, you are better off using the FlyByWireA mode.

In stabilize mode the throttle is limited by the `THR_MIN` and `THR_MAX` settings.

Note that STABILIZE mode is not a good mode to use for tuning the control loops. You are far better off using FBWA for that.