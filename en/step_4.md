## Draw a chart

Let's draw a chart to help the user understand the quantities of water more easily than if you just told them all the numbers.

--- task ---
Make two new sprites called `Tap` and `Toilet`. Select this costume for both:

![The grey rectangular button costume](images/drawBlankButton.png)

[[[generic-scratch3-rename-sprite]]]
--- /task ---

--- task ---
Draw on the costumes to add descriptive text to them. The `Tap` will be labelled with "Tap running for 1 minute" and the `Toilet` with "Flushing the toilet". To add text to your costume you can click on the **T** icon:

![The T icon for adding text to a picture](images/drawTicon.png)
--- /task ---

--- task ---
Place the two sprites one above the other on the left hand side of the stage:

![The two button sprites placed at the left edge](images/drawSpritesOnLeft.png)
--- /task ---

--- task ---
Add another costume to your cat sprite, choosing the glass of water from the library.

![The glass of water costume](images/drawGlassCostume.png)
--- /task ---

--- task ---
Then add the following blocks to the end of your code:

```blocks3
+    say [How about brushing your teeth?] for (2) secs
+    say [It can be tempting to leave the tap running while you brush. But did you know...] for (4) secs
+    say [...a running tap loses 6 litres of water per minute?] for (3) secs
+    switch costume to [glass water-a v]
+    set size to (35) %
```
--- /task ---

--- task ---
Click the green flag to test your program.
--- /task ---

--- collapse ---
---
title: Do I have to wait for the old code to run all the time?
---

If, like me, you don't want to go through the **whole** program every time you want to test a new bit of code, then you can move the parts you don't need out of the way for the moment!

+ Detach all the code from the previous card from the green flag block and drag it off to one side — but don't get rid of it entirely! Just leave it in a space on the current sprite panel.

![The code moved to one side away from the green flag](images/drawMoveCodeAside.png)

+ Then attach your new code directly onto the green flag.

```blocks3
    when green flag clicked
    say [How about brushing your teeth?] for (2) secs
    say [It can be tempting to leave the tap running while you brush. But did you know...] for (4) secs
    say [...a running tap loses 6 litres of water per minute?] for (3) secs
    switch costume to [glass water-a v]
    set size to (35) %
```

+ When you're ready, you can put everything back together again.


```blocks3
    when green flag clicked
    set [totalWater v] to [0]
    set size to (80) %
    switch costume to [monkey-a v]
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
    change [totalWater v] by ((flushes) * (6))
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
    change [totalWater v] by ((showers) * ((showerMinutes) * (7)))
    say [You use...] for (2) secs
    say (join(totalWater) [ litres of water per week!]) for (5) secs
    say [How about brushing your teeth?] for (2) secs
    say [It can be tempting to leave the tap running while you brush. But did you know...] for (4) secs
    say [...a running tap loses 6 litres of water per minute?] for (3) secs
    switch costume to [glass water-a v]
    set size to (35) %
```

**Note**: you should be careful when doing this, as sometimes there might be blocks that you need to run in the code you're moving aside — you'll need to keep them in your script to avoid problems!

--- /collapse ---

To use the Pen blocks in Scratch, you need add the **Pen extension**.

+ Click on the **Add extension** button in the bottom left-hand corner.

![add extension button highlighted](images/add-extension-annotated.png)

+ Click on the **Pen** extension to add it.

![pen extension highlighted](images/click-pen-annotated.png)

+ The Pen section then appears at the bottom of the blocks menu.

![pen extension blocks](images/pen-extension-blocks.png)

--- task ---
Add the following blocks to the end of your script. You'll find the `stamp`{:class="block3extensions"} block in the **Pen** category.

```blocks3
+    go to [Tap v]
+    move (45) steps
+    repeat (6)
        move (20) steps
        stamp
        wait (0.5) secs
    end
```
--- /task ---

--- task ---
Click the green flag to watch your new animation!
--- /task ---

**Note:** You might need to change the `move 45 steps`{:class="block3motion"} to another number depending on the size of your `Tap` sprite. The purpose of this block is to place the glass **beside** the text so you can see it.

--- collapse ---
---
title: How does it work?
---

The `stamp`{:class="block3extensions"} block makes a sprite stamp an image of itself onto the stage.

It draws the image straight onto the background, so no new sprites are created.

You can double-click the `clear`{:class="block3extensions"} block to remove everything that was added with **Pen** blocks.

--- /collapse ---

--- task ---
When you run your code again, you'll see that the stamped glasses are still there at the start. To clear them away, add the `clear`{:class="block3extensions"} block to the top of your script, right after the green flag. You can reset the position of the sprite to the centre as well using a `go to`{:class="block3motion"} block.

```blocks3
    when green flag clicked
+    clear
    go to x:(0) y:(0)
```
--- /task ---

--- task ---
Add similar code to make the sprite illustrate the amount of water that's used by flushing the toilet (remember, one flush uses 6 litres).
--- /task ---

--- hints ---

--- hint ---

+ Use the `go to mouse-pointer`{:class="block3motion"} block to move the sprite to the correct sprite, and select the sprite by clicking on the little triangle in the block.

+ Repeat the stamp code `6` times, which is the number of litres of water used per flush.

--- /hint ---

--- hint ---

+ Here is the code you need to add:

```blocks3
    go to [Toilet v]
    move (45) steps
    repeat (6)
        move (20) steps
        stamp
        wait (0.5) secs
    end
```

--- /hint ---

--- /hints ---
