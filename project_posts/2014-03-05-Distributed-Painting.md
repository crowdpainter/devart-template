There were several technical hurdles that we would have to overcome in order to allow the type of multi-user painting that we wanted.

The first hurdle was paint mixing, or how do we prevent users from dipping the brush in black, then in white, then in black, and so on, creating a very non-black, non-white color on the brush. We solved this using both mechanical and code related means. Pindar created a mechanical brush cleaner so that every time we change colors, we can clean the brush. You don't want to clean the brush after every stroke because it's slow and inefficient. Therefore I created a configurable group queuing mechanism in the code that groups incoming strokes from multiple users by color. The side effect of this is that we are doing some slight altering of stroke order. However, the user is generally unaware of this because they don't know when other user strokes are received in comparison to their strokes. 

Since there is only one robot and it is comparably slow to paint strokes than it is for users to draw them, we wanted to make sure users understood what was happening and what the potential final outcome would be. That meant having an up to date stroke representation on the client.

In order to do that, we had to track several things:
* Strokes a user has drawn that are waiting to be painted
* Strokes other users have drawn that are waiting to be painted
* The order for all pending strokes.
* Strokes that had been painted.
 
Our initial thought was to use Web Sockets and simply broadcast from the server when users created strokes or a stroke had been painted. The problem we ran into early on is: large amounts (tens of thousands of points) of annotations (or strokes) on the canvas take noticeable time to render when panning and zooming. You can fix panning by essentially moving the canvas with the underlying image, but zooming still requires a redraw. You can't just burn in the strokes, because we have to remove the painted strokes from each users canvas. We also had an interleaving problem. Since we were grouping strokes on the server, we couldn't just render strokes as received because they wouldn't actually be painted that way.

After some trial and error, the solution we ended up with has having the server raster the current state of the stroke queue which would solve the problem of the interleaved strokes and removing painted strokes. We update the image every couple of seconds on the server and clients simply cycle the image like they would a stream. Obviously we still use the HTML5 canvas (actually multiple canvases) to let users draw strokes, but once they've been accepted by the server we eventually just clear them off the canvas. 
