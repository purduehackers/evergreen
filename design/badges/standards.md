# Badge standards

## Software
Any vector design software that can export as SVG (Scalable Vector Graphics). Adobe Illustrator and Inkscape are the most commonly-used ones.

Inkscape is free, so if you don't have a Creative Cloud subscription etc., it's a good place to start.

## Where to start?
If this is your first badge, the easiest way to begin building is by using primitives (circles, squares, polygons).

It is very easy to shape primitives to your desire as they have a minimal amount of points and can be very easily adjusted. Unless your badge is some complex shape, then everything can be built out of rectangles, ellipses, or triangles. Most vector softwares should also have a shape builder tool that makes combining primitives easy. If your badge is a simple shape made up of primitives, you can simply duplicate the final shape and get rid of the fill in order to create the cut line around the outside of your badge.

## Material choice
See [ordering-material.md](ordering-material.md).

Be aware that different materials will cause engravings to show more or less clearly. Generally, lighter colors are more difficult to see engravings on (because engravings are white). Pearl acrylics also make the engravings much fainter. For an example, see the 5.0 badge (fluorescent) vs the 5.7 badge (pearl).

## Colors
In this section, colors will be represented with hex codes. Hex codes can be 3 (`#xxx`) or 6 (`#xxxxxx`) digits. For the sake of simplicity, hex codes in this document will be represented by a 3-digit code. To get the corresponding 6-digit code, simply double each digit. For example, `#F00` -> `#FF0000`

Trotec Ruby will recognize any grayscale color from `#000` to `#FFF`, and will recognize `#F00` as the cut path. Any other color cannot be engraved or cut by Trotec Ruby.

If it is your first attempt at making a badge, do not attempt grayscale. Instead, make sure everything is either `#F00` (red), for the cut path, `#FFF` (white), for no engraving, or `#000` (black), for engraving.

## Engraving
* Make sure all engraving lines have a thickness of at least 3% the size of the badge. Engraving patterns that are too thin will not show up well.
* You can actually use any grayscale color, from `#000` to `#FFF`, for the engraving. The lighter the engraving color, the less power the laser cutter will use for that segment of the engraving. (black being full power, and white being no power). But please use this wisely and sparingly:
    * The grayscale is not simply a map between light engraving and dark engraving; lighter engravings also have an increased "dithering" effect. See the badges for 3.0 beta, 3.6, and 4.2 for some examples.
    * You need *lots* of contrast between colors, otherwise it will appear muddy. Ruby does not do well with low-contrast engravings. See the Hack Night 2.3 ("scuba") badge for an example of how a seemingly good-looking design can actually look muddy and low-contrast on the actual badge.
    * Avoid more than 2 or 3 grayscale colors in a badge design. Can't stress enough: **If you do a grayscale engraving, it will appear much lower-contrast on the badge itself vs. in the design.**

## Cutting Path
There are three main things that can happen:
* Correct: If you import a connected path of a red line from your graphics software of choice, Figma will see it as a single vector path, Ruby (software for laser cutting) sees it as a vector, the laser cutter does one smooth pass
* Slightly Incorrect: If you use Joins on Figma to create your badge outline, Figma sees it as a single vector path, Ruby sees it as a complex object but still recognizes it as a cut line which causes the laser cutter to jump around and make redundant cuts
* Incorrect: If you use a shape as a cut line, Figma sees it as a fill, ruby sees it as a complex object and does not recognize it as a cut line so make sure that the red path indicating where to cut is not an outline of an object but a standalone path with a red stroke.
**TODO: put information here about how thick the physical cut actually is.**

## A brief warning on formatting
You will be creating a design, exporting to a Figma document, and then further exporting to Trotec Ruby for cutting. This makes for at least two, and most likely three, separate pieces of software the SVG has to go through. The following sections are dedicated to minimizing the issues that arise when moving between each program. 

## Text
By default, text you create is a text object that requires a font. The fonts you have on your computer are likely different from the fonts figma has, which means that text will not look right when you export it. To solve this, before exporting, make sure to convert your text to a series of vector paths. 

Before you do so, make extra certain that your text is accurate and / or keep a backup of your text. Check for typos, incorrect dates, version numbers, and unsatisfactory wording. You will not be able to edit your text easily after converting it.

The process for converting is different depending on the program you are running. 
- In illustrator, do Type -> Create Outlines
- In inkscape, do Path -> Stroke to Path
- In adobe animate, select everything and then break apart twice

## Outlines / Strokes
When you are drafting your design, you may have strokes in your file. Strokes will not resize proportionally when resizing the design in figma, and thus should be converted to paths before exporting. To do this,
- In illustrator, do Object -> Path -> Outline Stroke
- In inkscape, do Path -> Stroke to Path
- In adobe animate, do Modify -> Shape -> Convert lines to fills

The one exception to this rule is the cut path, which should remain as a stroke. This is because the goal is to cut a path, not an area.

## Other Various Pitfalls
* Always make sure the cut line is `#F00`, not any other shade of red. Trotec Ruby only recognizes `#F00`. This can be fixed in Ruby itself, so it's not a big deal, but it's better to get it right in the design so that we don't risk missing it when we make the badge & not having the cut line work.
* If you are using adobe illustrator, make sure your color mode is set to RGB. You can check this by going to File -> Document Color Mode and setting it to RGB Color. If it is not set to RGB Color, the colors will change on export without you noticing and bad things will happen.