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

## Size
When aligning badges in Trotec Ruby, you’ll have to decide on a size for each of them. This is an annoying and complex dance because you want to balance making them the right size while also maximizing space & getting as many badges as you can out of the material.

For a 12x18 sheet, you should aim to make 40-50 badges per sheet (80-100 badges total, since we usually use 2 12x18 sheets). For a 12x12 badge you should aim to make 30-35 badges.

The ideal size for a badge is somewhere between 2.0 and 2.7 inches. Try not to make the dimension on either side larger or smaller than this if you can. Though larger is ok if you think the badge warrants it.

In general, a badge should not be smaller than 2.0 inches in any direction unless it’s super warranted or there are material constraints. 1.9 or 1.8 in one direction (so >2.0 in the other direction) can be fine if the design is good.

Never make a badge smaller than 2.0 inches in _both_ directions or smaller than 1.7 inches in one direction. See the Hack Night 3.3 “lightning time” badge for an example of a solid badge that was kneecapped by being too small.

*Important:* The total size of the whole thing should not exceed `acrylic sheet width and height - 0.125` inches, or `- 0.15` if you want to really be safe. Acrylic manufacturers like Canal Plastics have a tolerance of +-1/8 inch, and in our experience it’s almost always on the minus side. This means that if the supposed width of a sheet of acrylic is 12x18 inches, you should assume it’s actually 11.875x17.875 inches.

## Colors
In this section, colors will be represented with hex codes. Hex codes can be 3 (`#xxx`) or 6 (`#xxxxxx`) digits. For the sake of simplicity, hex codes in this document will be represented by a 3-digit code. To get the corresponding 6-digit code, simply double each digit. For example, `#F00` -> `#FF0000`

Trotec Ruby will recognize any grayscale color from `#000` to `#FFF`, and will recognize `#F00` as the cut path. Any other color cannot be engraved or cut by Trotec Ruby.

If it is your first attempt at making a badge, do not attempt grayscale. Instead, make sure everything is either `#F00` (red), for the cut path, `#FFF` (white), for no engraving, or `#000` (black), for engraving.

## Engraving
* Make sure all engraving lines have a thickness of at least 3% the size of the badge. Engraving patterns that are too thin will not show up well.
* You can actually use any grayscale color, from `#000` to `#FFF`, for the engraving. The lighter the engraving color, the less power the laser cutter will use for that segment of the engraving. (black being full power, and white being no power). But please use this wisely and sparingly:
    * The grayscale is not simply a map between light engraving and dark engraving; lighter engravings also have an increased "dithering" effect. See the badges for 3.0 beta, 3.6, and 4.2 for some examples.
    * Grayscale colors will not engrave the way you think they will. Anything lighter than something around `#666666` is unlikely to show up, so don’t attempt it for anything that must be clear. For any lines or other pieces of engraving that you want to make sure show up, please use `#000000` or a color near to it.
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

# Stamp standards

* The largest size in Trotec Ruby should be 1.5 inches
* The design in the center of the stamp should not include any text or complex items. Make it a simple version of the badge that removes a lot of elements.
* The only allowed engraving colors are `#000000` and `#FFFFFF`. Do not use grayscale in a stamp, otherwise the stamp will be uneven and none of the grayscale strokes will show up when stamped.