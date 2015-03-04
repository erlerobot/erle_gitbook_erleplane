###Training Mode

This mode is like training wheels on a bicycle and is ideal for teaching students manual R/C control. If the roll is less the the `LIM_ROLL_CD` parameter than the pilot has manual roll control. If the plane tries to roll past that limit then the roll will be held at that limit. The plane will not automatically roll back to level flight, but it will prevent the pilot from rolling past the limit. The same applies to pitch – the pilot has manual pitch control until the `LIM_PITCH_MIN` or `LIM_PITCH_MAX` limits are reached, at which point the plane won’t allow the pitch to go past those limits.

In training mode the rudder and throttle are both completely under manual control.