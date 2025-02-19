# Badge standards for less problems

## Software
Any vector design software that can export as SVG (Scalable Vector Graphics). Adobe Illustrator and Inkscape are the most commonly-used ones.

Inkscape is free, so if you don't have a Creative Cloud subscription etc., it's a good place to start.

## Building your badge
Unless you are tracing over a design or have a complex design that requires a lot of nodes, refrain from using lines to build your badge, especially if this is your first one. The easiest way to begin building is by using primitives (circles, squares, polygons).

### Why should I use primitives?  
Because I said so. 

Joking aside, it's very easy to shape primitives to your desire as they have a minimal amount of points and can be very easily adjusted. Unless your badge is some complex shape, then everything can be built out of rectangles, ellipses, or triangles. Most vector softwares should also have a shape builder tool that makes combining primitives easy. Finally, you can simply duplicate the final shape and get rid of the fill in order to easily create the cut line around the outside of your badge.

## Text
Make sure you are certain that this is the font you want to use. Ensure the content inside your text is accurate (this means no typos, no wrong dates, and you are satisfied with the wording). Then flatten, convert object to path, whatever it is called on the software of your choice to convert the text to a vector. Make sure the ensuing vector does not have any outlines and is only fill. This means looking at the properties of the vector in your software and making sure there are no strokes or outlines or whatever they are called in your software, present. 

### Why do we convert text to vectors?
Fonts do not always translate accurately between softwares because some may not be available. Sometimes Figma, the place where we store all our badge designs, may not have the font you are using. This is particularly tricky if the font itself is a crucial part of your design (ex. Wingdings as a decorative border). If you like the look of a certain font then it is always better to flatten as an added security measure against Figma not having your font.

### Why can't the text have strokes? I want to make my text bolder.
Weird and dark magic will happen when exporting to Figma, where unneeded groups, masks and layers will be added. This will mess up the engraving when laser cutting. Even if it doesn't cause a problem, it is better to keep things simple to prevent last minute mishaps. If you want the text to be bolder, 90% of the time the font that you are using will probably have a bolder version. Again, make sure you are satsified with the look of the text before flattening.

## Colors
If it is your first attempt at making a badge, do not attempt grayscale. If you must attempt greyscale, keep things high contrast in the design. Ruby does not do well with low contrast engravings. 
Make sure everything is either FFFF00 or 000000, the colors needed to cut or engrave. This means everything. If another color is present then whatever has that color cannot be engraved or cut by Trotec Ruby.
