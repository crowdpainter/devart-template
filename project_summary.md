# Project Title
Crowd Painter

## Authors
- Pindar Van Arman, https://github.com/crowdpainter
- Trillane Burlar, https://github.com/crowdpainter

## Description

Crowd Painter is an interactive installation that experiments with artificial creativity and crowd-sourced art.

We have built a painting robot in the Washington D.C. area that is capable of taking commands from both AI and internet participants through an intuitive web enabled interface. The robot uses these real time commands to apply paint with an artists brush to a stretched canvas.

Anyone with an internet connection can collaborate in the painting by visiting Crowd Painter's website and applying their own strokes. When no one is applying strokes, the robots AI examines what the last human was painting, and continues from there.  If another human begins to paint, the AI hands control back to the new contributor.

In this manner a crowd sourced painting emerges from the collaboration between the artists, the internet, and the robots custom written artificial creativity.

## Link to Prototype
[Crowd Painter Beta Prototype](http://www.crowdpainter.com "Crowd Beta Painter Prototype")


## Example Code
Our software converts Human and AI created strokes to commands for our robot controller to follow
```
private List<Command> convertStrokeToCommands( final BrushStroke stroke ) {
	final ArrayList<Command> commands = new ArrayList<Command>();
	if(stroke.getPoints() != null && stroke.getPoints().size > 1){
	 	CanvasPoint point1 = stroke.getPoints().get(0);
        	CanvasPoint point2;
        	for (int i = 1, size = stroke.getPoints().size(); i < size; i++) {
           	    point2 = stroke.getPoints().get(i);
	            commands.add(new PaintTo(
                    	point1.getX(),
                    	point1.getY(),
                    	point2.getX(),
                    	point2.getY(),
                    	stroke.getColor()));
	            point1 = point2;
        	}
	        commands.add(new StrokeComplete());
	}
	return commands;
}
```
## Links to External Libraries

[GWT (Google Web Toolkit)](http://www.gwtproject.org/ "GWT (Google Web Toolkit)") 

[Spring](http://spring.io/ "Spring")

[Hibernate](http://hibernate.org/ "Hibernate")

[Apache CXF](cxf.apache.org/ "Apache CXF")

## Images & Videos

![artists](project_images/pindartrillane.jpg?raw=true "artists")

The Artists, Trillane Burlar (left) and Pindar Van Arman (right)

http://youtu.be/GmGgXOxoEDs

Recently completed Video (March 10, 2014) describing how individuals can participate in Crowd Painting.
