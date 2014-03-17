# Project Title
Crowd Painter

## Authors
- Pindar Van Arman, crowdpainter
- Trillane Burlar, crowdpainter

## Description
Our art is an experimentation in artificial intelligence, artificial creativity, and crowd sourced art.  We are building a painting robot in the Washington D.C. area that takes commands from both AI and internet participants to create acrylic paintings on stretched canvases.  This robot uses an artist brush to create paintings stroke by stroke.  When operating, anyone with an internet connection is able to visit our website and apply their own strokes.  When no one is applying strokes, the robots built in AI examines what the last human was painting, and takes over from there.  If another command comes in from the internet, the AI hands control back to the new contributor.  In this manner a crowd sourced painting emerges from the collaboration between us, the internet, and our custom written AI.  At the basest level this asks who and what is an artist, at others it asks, does creativity even exist.

## Link to Prototype
[Crowd Painter Beta Prototype](http://www.crowdpainter.com "Crowd Beta Painter Prototype")


## Example Code
Our software converts Human and AI created stokes to commands for robot to follow
```
	private List<Command> convertStrokeToCommands(
			final BrushStroke stroke ) {
		final ArrayList<Command> commands = new ArrayList<Command>();
		CanvasPoint point1 = stroke.getPoints().get(
				0);
		CanvasPoint point2;
		for (int i = 1, size = stroke.getPoints().size(); i < size; i++) {
			point2 = stroke.getPoints().get(
					i);
			commands.add(new PaintTo(
					point1.getX(),
					point1.getY(),
					point2.getX(),
					point2.getY(),
					stroke.getColor()));
			point1 = point2;
		}
		commands.add(new StrokeComplete());
		return commands;
	}
```
## Links to External Libraries

[GWT (Google Web Toolkit)](http://www.gwtproject.org/ "GWT (Google Web Toolkit)") 

[Spring](http://spring.io/ "Spring")

[Hibernate](http://hibernate.org/ "Hibernate")

[Apache CXF](cxf.apache.org/ "Apache CXF")

## Images & Videos

![Artists](project_images/pindartrillane.jpg?raw=true "Artists")

The Artists, Trillane Burlar (left) and Pindar Van Arman (right)

http://youtu.be/GmGgXOxoEDs

Recently completed Video (March 10, 2014) describing how individuals can participate in Crowd Painting.
