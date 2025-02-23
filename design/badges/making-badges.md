This file serves as a step-by-step guide on how to make badges / stamps for Hack Night.

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
One 12x18 sheet with 1/8" thickness has produced 35-50 badges. Consider the theme to find a fitting acrylic or find something cool and inspiring! <br> <br>
More details at [ordering-material.md](ordering-material.md).

# 3. Design the badge
Starting with a drawing can help. Then import the drawing into a vector graphics software of your choice and trace around to make your design come alive digitally. Figma, Illustrator, or Vectr are probably your best bet. <br> <br>
Black = engrave. Red = cut. <br> <br>

Make sure to read [standards.md](/design/badges/standards.md) and follow the instructions within to ensure your badge design remains problem-free.

Read standards.md! Read it again! There are many problems people run into that have been documented. Hopefully this will cut down on the number of problems found when it comes time to laser cut.

**When you're finished, export your design as an SVG and put it on Figma.**



# 4. Design the stamp
Draw inspiration from an actual stamp shape, generate a blob, make a shape that inspires you, or take a shape from a previous stamp. <br>
Then alter your badge design so that it is only black and white. It can also sometimes help to remove the date, version, and "Hack Night" text. <br>
Fill your stamp shape with white and add an inner stroke of black and 5px. <br>
Add the titles of the stamp (- Hack Night ## - MM DD YYYY -) and update it to current date and version number. <br>
Align everything together to where you want everything to be. Select everything and invert the colors. <br>
Now copy paste the outline shape, get rid of the fill, and make it red (`#FF0000`). <br><br>
This process is very doable within Figma, but if it isn't on there already, put your stamp design on Figma as well.

* Although grayscale is allowed in badge designs, never use grayscale in a stamp; **only use `#000000` and `#FFFFFF`.
  * If you think about the way the stamp works: the laser cutter will engrave (or, shave a layer off the top of) the rubber everywhere it's black, and leave everything that's white. So the white parts will be protruding out uniformly, and black parts inward uniformly, so the white parts will stamp nicely. If you add grayscale, it will just shave off less of the top of the rubber, so it'll be set inward from the white parts and won't appear when you actually stamp it.

# 5. Laser cut badge
Prerequisite: be certified and reserve a time slot.
I imagine most of the information below will be learned when you get laser cutter certified <br>

Export the stamp and badge designs separately as SVG files and put them on a USB.
Once you're in the lab, move the designs to Ruby Trotec on the design tab and set the size of the badge on the prepare tab.
Set the material you are cutting on.
Align the badges on the page to optimize space and make them fit on the size of the acrylic sheet. A lot of copy paste and resizing.
Calculate job time and you can create a job. <br>

Place acrylic on the plate of the laser cutter and push it to the top left.
Put the metal thing on the laser and push the plate up so that there is a precise distance between laser and acrylic. Move laser to zero position (top left).
Push the job to the laser cutter, open blast gate, start the machine and watch your badges cut.

# 6. Laser cut stamp
Follow steps above to import the stamp design. Set the material to "Rubber (2.3mm)".

Choose a reasonable size to fit on your rubber sheet. Typically the longest dimension is set to 1.5in.

Horizontally flip the stamp design.
Modify the rubber material profile to configure *10 passes* on the cut. When prompted to "restore from database", click "No".

Laser cut the stamp and yippee! Ready for Hack Night B)
