We knew that we wanted users to be able to remotely control the robot. At the time we were both working as web developers and we figured the simplest way is to set up a website that allows users to use a interface which would send strokes to the server which would send commands to the robot. This process wouldn't require users having to download an app or force us into writing multiple copies for different operating platforms. We chose Google Web Toolkit (GWT) for our client side development and Java for the server side development. We chose GWT because it handles the majority of cross browser compatibility issues that we care about. It also allows you to write testable, well documented, reusable, sanely structured code for the client. Javascript is absolutely miserable to develop complex applications in, when compared to Google Web Toolkit. On the server, we needed the functionality of a full programming language. Since we were already using GWT it made sense to stick with Java.



Initially we prototyped a system that used the HTML5 canvas to allow users to "draw" and then sent the captured points back to the server. The strokes would remain on the users screen until the robot had painted them. The first problem we encountered was that there is only one robot and potentially many users. We developed a system that would allow a single user to paint and then we had a queueing system where other users could wait to paint. We set a time limit where a user couldn't paint for more than five minutes without going back into the queue. There was a lot of effort put into working out the queueing mechanism, client-server communication, and queue related corner cases. There were ideas of even allowing people to reserve painting times.

Then we showed it to people.

The initial reaction was positive, so positive that no one wanted to wait to paint. We ended up scrapping the user queue and trying to figure out how we could have multiple users paint at the same time. 

Another thing we noticed was that users wanted to paint on different views.  Some users wanted to trace the source image, while others wanted to work free styledirectly on the canvas.  To address this, we added a button to switch between multiple views.  Three of the views can be seen below.

![Three Views](project_images/threeviews.jpg?raw=true "Three Views")

Views from Left to Right: Trace, Mix, Painting

Anyone with a browser or web connection can use the client we created to take over the robot and paint.  You simply select a color from the palette and make your stroke.  The buttons down the left side help navigate and select views.  

Though still in beta testing, you are able to see and use its interface at [Crowd Painter Beta Prototype](http://www.crowdpainter.com "Crowd Beta Painter Prototype").
