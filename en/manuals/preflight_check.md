#Preflight Checks

When using [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) some test is recommended in order to see that all is working fine. This tests allowed us:

+ Checking the RC channels are properly set.
+ Checking ailerons/rudder/elevator/throttle are the good ones.
+ Checking the flight modes switch is OK

###Manual mode check

Turn on [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) and put it is `manual mode`. Now move the RC sticks to see that the servos moves in the proper direction, make sure this happens:

	* When moving left stick to right/left, check that the rudder turns to the rigth/left as the same as the stick movement.
	* When moving the right stick right/left, check that the ailerons move in the opposite direction. When you move the stick to the left, check that the left aileron goes up and the right aileron down. Ypu should see vice versa movement when the sticj is moved to the right.
	* When moving the right stick down, you should see the elevator moving down. And when moving the right sitck up, the elevator should move up.
	* Finally, trigger the throttle slightly to see that is responsing.

###Stabilize mode check

Now check that using assisted flight modes, the servo movements are according to what they should.

