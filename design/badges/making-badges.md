This file serves as a guide on how to make badges / stamps for Hack Night.

Outline:
1. Brainstorm an idea
2. Buy acrylic
3. Design the badge
4. Design the stamp
5. Laser cut badge
6. Laser cut stamp

---

# 1. Brainstorm an idea
Steps 1 and 2 are interchangeable as it can be easier to come up with a theme / badge idea after looking at the acrylic.
Past themes we have done include references to pop culture and media, relevant things happening in the world or on campus (ex. 4.6, 3.11), or something new on its own like 3.2, 3.16, 4.7.
Typically a standalone theme works best on average, but some reference badges have been very strong as well (ex. 4.3, barbenheimer).
Also consider basing the badge off of an idea rather than a specific thing like 4.2.

# 2. Buy acrylic
We get a lot of our acrylic from [Canal Plastics Center](https://www.canalplastic.com/products/0b008-rt-radiant-iridescent-acrylic-sheet) but Amazon and others are fine too.
One 12x18 sheet with 1/8" thickness have produced 35-50 badges. Consider the theme to find a fitting acrylic or find something cool and inspiring! <br> <br>
More details at [ordering-material.md](ordering-material.md).

# 3. Design the badge
Starting with a drawing can help. Then import the drawing into a vector graphics software of your choice and trace around to make your design come alive digitally. Figma, Illustrator, or Vectr are probably your best bet. <br> <br>
Black = engrave. Red = cut. <br> <br>
The laser cutter can be picky about the cutting path. For details see [Cutting Path](#cutting-path) <br>

Please follow the standards in [standards.md](/design/badges/standards.md) to ensure your badge design remains problem-free.

Note on engraving: you can use shades to control the strength of the engraving. Some acrylic such as the "pearl" kinds don't engrave as dramatically as others so you can increase the cut strength on Ruby. Also, you can do intricate designs with the engravings as the laser cutter makes a standard pass through the whole acrylic sheet, but intricate cutting paths can increase laser cutting times. <br> <br>

**When you're finished, export your design in .svg and put it on Figma.**

## Common Pitfalls
* If you use text effects like warp or use fonts that don't exist on Figma, you need to "Create Outline" of the text. This will make the text vector shapes. Note that this results in the text being non-editable so do this after you've finalized the design or after you make a backup.
* Always make sure the cut line is `#FF0000`, not any other shade of red. Trotec Ruby only recognizes `#FF0000`. This can be fixed in Ruby itself, so it's not a big deal, but it's better to get it right in the design so that we don't risk missing it when we make the badge & not having the cut line work.
### Cutting Path
There are three main things that can happen: <br>
* Correct: If you import a connected path of a red line from your graphics software of choice, Figma will see it as a single vector path, Ruby (software for laser cutting) sees it as a vector, the laser cutter does one smooth pass
* Slightly Incorrect: If you use Joins on Figma to create your badge outline, Figma sees it as a single vector path, Ruby sees it as a complex object but still recognizes it as a cut line which causes the laser cutter to jump around and make redundant cuts
* Incorrect: If you use a shape as a cut line, Figma sees it as a fill, ruby sees it as a complex object and does not recognize it as a cut line so make sure that the red path indicating where to cut is not an outline of an object but a standalone path with a red stroke.
### Engraving
* Make sure all engraving lines have a thickness of at least 3px — 1px and 2px lines don't show up well when laser cut.
* You can actually use any grayscale color, from `#000000` to `#FFFFFF`, for the engraving. The lighter the engraving color, the less power the laser cutter will use for that segment of the engraving, with black being full power. But please use this wisely and sparingly:
  * The grayscale is not simply a map between light engraving and dark engraving; lighter engravings also have an increased "dithering" effect. See the badges for 3.0 beta, 3.6, and 4.2 for some examples.
  * You need *lots* of contrast between colors, otherwise it will appear muddy. See the Hack Night 2.3 ("scuba") badge for an example of how a seemingly good-looking design can actually look muddy and low-contrast on the actual badge.
  * Avoid more than 2 or 3 grayscale colors in a badge design. Can't stress enough: **If you do a grayscale engraving, it will appear much lower-contrast on the badge itself vs. in the design.**

# 4. Design the stamp
Draw inspiration from an actual stamp shape, generate a blob, make a shape that inspires you, or take a shape from a previous stamp. <br>
Then alter your badge design so that it is only black and white. It can also sometimes help to remove the date, version, and "Hack Night" text. <br>
Fill your stamp shape with white and add an inner stroke of black and 5px. <br>
Add the titles of the stamp (- Hack Night ## - MM DD YYYY -) and update it to current date and version number. <br>
Align everything together to where you want everything to be. Select everything and invert the colors. <br>
Now copy paste the outline shape, get rid of the fill, and make it red (#FF0000). <br><br>
This process is very doable within Figma, but if it isn't on there already, put your stamp design on Figma as well.

## Common pitfalls

* Although grayscale is allowed in badge designs, never use grayscale in a stamp; **only use `#000000` and `#FFFFFF`.
  * If you think about the way the stamp works: the laser cutter will engrave (or, shave a layer off the top of) the rubber everywhere it's black, and leave everything that's white. So the white parts will be protruding out uniformly, and black parts inward uniformly, so the white parts will stamp nicely. If you add grayscale, it will just shave off less of the top of the rubber, so it'll be set inward from the white parts and won't appear when you actually stamp it.

# 5. Laser cut badge
Prerequisite: be certified and reserve a time slot.
I imagine most of the information below will be learned when you get laser cutter certified <br> <br>

Export the stamp and badge designs separately as SVG files and put them on a USB.
Once you're in the lab, move the designs to Ruby Trotec on the design tab and set the size of the badge on the prepare tab.
Set the material you are cutting on.
Align the badges on the page to optimize space and make them fit on the size of the acrylic sheet. A lot of copy paste and resizing.
Calculate job time and you can create a job. <br> <br>

Place acrylic on the plate of the laser cutter and push it to the top left.
Put the metal thing on the laser and push the plate up so that there is a precise distance between laser and acrylic. Move laser to zero position (top left).
Push the job to the laser cutter, open blast gate, start the machine and watch your badges cut.

# 6. Laser cut stamp
Follow steps above to import the stamp design. Set the material to "Rubber (2.3mm)".

Choose a reasonable size to fit on your rubber sheet. Typically the longest dimension is set to 1.5in.

Horizontally flip the stamp design.
Modify the rubber material profile to configure *10 passes* on the cut. When prompted to "restore from database", click "No".

Laser cut the stamp and yippee! Ready for Hack Night B)
