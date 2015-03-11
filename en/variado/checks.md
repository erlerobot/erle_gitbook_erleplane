#PreFlight Checks

Before flying [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) for the fist time, you have to be sure all is working as expected. 

---
[This video](https://www.youtube.com/watch?v=gqvfsJAXNZE&feature=youtu.be), explains the proccess

----

In order to do so, follow the next steps:

###Manual Mode Checks

The `Manual Mode Checks` allows you to see that the RC Channels are setup properly, the autopilot does not interfere between the RC and the values that are written to the servos and the motor.

----
*For more info, check [flight modes section](../flight_modes/README.md)*

----

With this verification we could see if the four channel are assigned properly to the `RC sticks` and are not reversed. Follow the next steps:

+ Power up Erle-Plane
+ Connect to [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) and set it into `Manual Mode`.
+ Trigger the throttle from the `RC`, as in the image below:

![Plane Throttle](../img/checks/th9x_throttle.jpeg)

-----

+ Check the `Rudder` is working fine

Turn the left stick to the right, you should see that the `rudder` flap turns also to the right

![Right rudder](../img/checks/th9x_rudder_right.jpeg)
<div style="text-align:center"><img src ="../img/checks/rudder_right.jpg" /></div>

And now turn the left stick to the left and check if `rudder` also moves to the left:

![RC rudder](../img/checks/th9x _rudder_left.jpeg)
<div style="text-align:center"><img src ="../img/checks/rudder_left.jpg" /></div>

-----

+ Check that the `ailerons` are working fine

Move the right stick of the RC to the right
![Right ailerons](../img/checks/th9x_ailerons_right.jpeg)
<div style="text-align:center"><img src ="../img/checks/ailerons_right.jpg" /></div>
You should see how the `left aileron` moves down and the `right aileron` up.

Move the right stick of the RC to the left
![left ailerons](../img/checks/th9x_ailerons_left.jpeg)
<div style="text-align:center"><img src ="../img/checks/ailerons_left.jpg" /></div>
You should see how the `left aileron` moves up and the `right aileron` down.

----

+ Check the `Elevator` is working fine

Turn the right stick to the up, you should see that the `elevator` flap turns down

![up elevator](../img/checks/th9x_elevator_down.jpeg)
<div style="text-align:center"><img src ="../img/checks/elevator_down.jpg" /></div>

And now turn the right stick down and check if `elevator` moves up:

![up elevator](../img/checks/th9x_elevator_up.jpeg)
<div style="text-align:center"><img src ="../img/checks/elevator_up.jpg" /></div>

----

###Troubleshooting

You might find that your [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) is not behaving as described above. So, what to do??

+ RC Sticks are not set in the same order as explained above

That means that `autopilot` have assigned the received channels as in a different order. To fix this behaviour change `RC Map` parameters: change the channel number (1-4) where autopilot is receiving the rudder,yaw,pitch and roll. Save the changes.


+ The movements are reversed

This means that the RC is sending the values wrongly. To fix this behaviour: in the RC, enter in `settings` -> `Reverse`. Reverse the channel you want.

------

###Stabilize Mode Checks

Once we are sure that [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) and the RC are properly configured, let's see if the autopilot corrects the state of the plane correctly.

+ Set [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) to `stabilize mode`.
+ Roll [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) to the right.

You should see that the `left aileron`moves up and the `right aileron`down. You also should see that the `rudder` moves to the left.

![auto roll right](../img/checks/auto_roll_right.png)

---

+ Roll [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) to the left

You should see that the `left aileron`moves down and the `right aileron`up. You also should see that the `rudder` moves to the right.

![auto roll left](../img/checks/auto_roll_left.png)
![auto rudder right](../img/checks/auto_rudder_right.png)

---

+ Put the nose of [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) looking to the floor.

You should see that the `elevator`moves up.

![auto relevator up](../img/checks/auto_elevator_up.png)

----

+ Put the nose of [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) looking to the roof.

You should see that the `elevator`moves down.

![auto elevator down](../img/checks/auto_elevator_down.png)

###Troubleshooting

You might find that your [Erle-Plane](http://erlerobotics.com/blog/erle-plane/) is not behaving us described above. So what to do if the movements are reversed??

Open the parameters list, the easiest way to do it, is to open a GCS. Now, change the reverse/direct parameter of the channel that is moving wrong. If it is set to '1', assign it to '-1', and vice versa.