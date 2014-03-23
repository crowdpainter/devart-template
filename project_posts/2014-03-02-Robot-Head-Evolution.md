Similar to how the XY Tables have evolved over time to the current state, the robotic head that holds the paint brush has gone through many changes and improvements over the last eight years. The following is a brief history.

First (2005-2006): Electromagnet and Wood
Second (2006-2007): Solenoid and Wood
Third (2007-2008): Solenoid and Aluminum
Fourth (2008-2009): Machined Aluminum
Fifth (2009-2013): Visual Feedback
Sixth (2014-Present): Current Robotic Head

![First Five Robotic Heads](../project_images/robothead1.jpg?raw=true "First Five Robotic Heads")

The first robotic head (1), was a proof of concept.  It performed horribly.  As you can see, or guess, it is a home made electromagnet. The problem was that the electromagnet was so weak the fulcrum needed to be loose to avoid any friction.  And with such a loose connection, the brush would sway all over the place.  This robotic head was inexact and very unreliable.

To address these issues I made the second robotic head (2) with the help of a friend, Leon Derr.  He gave me a solenoid from a washing machine that I mounted on wood.  It was here that I also came up with the idea of using a magnetic refrigerator clamp to hold brushes. This low-tech solution survives to this day being used in even the most recent robotic head.  This head worked great. The only problem was that the solenoid was prone to overheating which reduced the strength of the electromagnet as it was being used. As such, it could only paint for a couple hours at a time.

To solve the solenoid heat problem, I bought a new set of solenoids and mounted them on a pure aluminum frame (3). Only problem with this head was that it would jam once in a while. The jam was probably caused by the fact that I used a threaded bolt for the fulcrum.

At this point money from sales justified machining a new robotic head.  For a reasonable professional fee, I had two robotic heads (4) made by Jacobus McKenzie, a friend from work. Mechanically, this design and fabrication is nearly perfect.  It has logged thousands of hours and millions of strokes without a single jam or malfunction. The robotic head was now a very stable, durable, and reliable mechanical part.

This brings us to the fifth robotic head (5), enhanced with the assistance of Gary Carr.  This head has a camera in a protective case.  The camera tracks all changes and used the images it captured to provide visual feedback to the robots AI.  In theory this was a great idea, in practice it was a disaster.  Painting with a brush is a messy business and paint would often get on the protective case.  When this happened the feedback algorithms became confused as it could not tell the difference between paint on the canvas and paint on the protective camera lens.  Chaos ensued.  This camera and the algorithms behind it had to be abandoned, though they would come back in a different form in the current robotic head.

![Current Robotic Head](../project_images/robothead2.jpg?raw=true "Current Robotic Head")

The current robotic head differs from the previous heads in many ways.  The primary difference is that it is designed to work at an upright angle.  The previous heads would glide above a flat horizontal canvas and as such received minimum paint splatter. Since this new upright head is to the side of canvas instead of over it, it gets splattered with a lot more paint.  To deal with this, it is designed to get dirty.  

![Robot Cameras](../project_images/robothead3.jpg?raw=true "Robot Cameras")

Due to the amount of paint splatter another modification was to remove the feedback camera and place it on a tripod approximately 48 inches away.  Multiple cameras can be see in the image above that captures the painting from multiple angles.  The primary feedback camera is run on a Raspberry Pi and was installed for the artists with the help and expertise of Matt Beiriger.
