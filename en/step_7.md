## Repetition is key

Right now you have two sets of code blocks in your script that are identical:

```blocks
    change [counter v] by (1)
    go to (item (counter) of [Sprites v])
    move (45) steps
    repeat (item (counter) of [WaterAmounts v])
        move (20) steps
        stamp
        wait (0.5) secs
    end
```

If you were to add more sprites to illustrate amounts of water for other things like showers or washing dishes, this would very quickly get out of hand! Seems like these blocks should be inside a loop of some sort, right?

+ On your script, detach the first `change counter by 1`{:class="blockdata"} block and everything after it and drag it to one side (don't delete it just yet!), so that the last blocks in your green flag script are

```blocks
    switch costume to [glass water-a v]
    set size to (35) %
```

+ Look in the **control** category and take out this block:

```blocks
    repeat until <>
    end
```

+ Attach it after the `set size to 35%`{:class="blocklooks"} block.

+ Then take one group of the the other blocks and put it inside the loop. You can now delete the other identical set of those blocks, as you no longer need them!

```blocks
    switch costume to [glass water-a v]
    set size to (35) %
    repeat until <>
        change [counter v] by (1)
        go to (item (counter) of [Sprites v])
        move (45) steps
        repeat (item (counter) of [WaterAmounts v])
            move (20) steps
            stamp
            wait (0.5) secs
        end
    end
```

Finally, you need to put something in the `until`{:class="blockcontrol"}! You want the code to repeat for each item in the lists, so a good thing to check for would be if the the counter has reached the last item in one of them. You can use another handy block here, from the list blocks in **data**:

```blocks
    length of [Sprites v]
```

+ The first thing you'll need is an **operator** block to check if two things are equal:

```blocks
    [] = []
```

+ Place this into the space in the `repeat until`{:class="blockcontrol"} block:

```blocks
    repeat until <[] = []]>
    end
```

+ Grab the `counter`{:class="blockdata"} block and plug it into the left hand side of the operator block.

+ Then, from **data**, place the `length of`{:class="blockdata"} block into the right hand side of the operator.

```blocks
    repeat until <(counter) = (length of [Sprites v])>
    end
```

--- collapse ---
---
title: About the new loop
---

You've used the `repeat`{:class="blockcontrol"} with a number to tell Scratch how many times to repeat something. 

But if you add more things to your lists of sprites and water amounts, you'll have to change the code each time to update the the `repeat`{:class="blockcontrol"} number. 

With a `repeat until`{:class="blockcontrol"} block, the code checks how many times it needs to repeat so you don't have to!

--- /collapse ---

+ Click the green flag to see your new and improved script run – it does the same thing using half the amount of blocks!

Let's really make the most of this new loop and display some more water usage information to the program.

+ Create 5 more sprites, naming them `Shower`, `Bath`, `Dishwasher`, `Dishes`, and `Washing`. You can give them more descriptive text on their costumes if you want to.

![All the sprites showing watery household activities](images/finalSprites.png)

Here are the descriptions I've used:

| Sprite name | Text description | 
|-----|-------|
| Shower | 5 minute shower |
| Bath | A bath |
| Dishwasher | Dishwasher |
| Dishes | Handwash dishes|
| Washing | Washing machine |

+ Tick the checkboxes to show both your lists on the stage so you can add the new information to them.

+ Add all the new sprite names to the `Sprites`{:class="blockdata"} list, making sure to type them exactly correct.

+ Then add the water usage to the `WaterAmounts`{:class="blockdata"} list. The table below shows the litres of water for each thing. Make sure you add them in the same order as the sprites, so that their list index numbers match up!

| Sprite | WaterAmount | 
|-----|-------|
| Shower | 35 |
| Bath | 80 |
| Dishwasher | 15 |
| Dishes | 10|
| Washing | 50 |

![The two lists full of water data](images/finalDataLists.png)

+ Finally, hide the lists again by unticking the checkboxes next to the code blocks, and click the green flag to run the code. You should see all the new water amounts get animated – that was without having to add any new code! Cool, right?

You might notice some of the items run out of space on the screen because the amount of water is so huge, and maybe you want to speed up the animation a little. Here are some small tweaks you can make.

+ Change the number of steps after the `stamp`{:class="blockpen"} from `20` to `4`. You'll probably need make the first `move`{:class="blockmotion"} bigger, try `60` instead of `45`, to get the glass of water out from behind the text sprite again.

+ Move the `wait`{:class="blockcontrol"} out of the first loop, putting it after the loop instead, but still inside the `repeat until`{:class="blockcontrol"}, and change the value to `1` or `2` seconds, or whatever you like.

+ Test it out, and tweak the numbers to suit you!

+ Finally, why not add a `say`{:class="blocklooks"} block to have the sprite display the number of litres of water being shown? 

```blocks
    say (join (item (counter) of [WaterAmounts v]) [ litres!])
```

+ I'm also adding in some code at the very end to change the sprite back to the monkey and get the user to think about ways to conserve water.

```blocks
    when green flag clicked
    set [counter v] to [0]
    clear
    go to x:(0) y:(0)
    set [totalWater v] to [0]
    set size to (80) %
    switch costume to [monkey2-a v]
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
    repeat until <(counter) = (length of [Sprites v])>
        change [counter v] by (1)
        go to (item (counter) of [Sprites v])
        move (45) steps
        say (join (item (counter) of [WaterAmounts v]) [ litres!])
        repeat (item (counter) of [WaterAmounts v])
            move (20) steps
            stamp
            wait (0.5) secs
        end
    end
    hide
    go to x: (0) y:(0)
    switch costume to [monkey2-a v]
    set size to (100) %
    show
    say [Think about ways you could use less water!] for (5) secs
```

--- collapse ---
---
title: Show me all the code!
---

Here is how the whole program looks now, so you can check it if something is not working right:

```blocks
    repeat until <(counter) = (length of [Sprites v])>
        change [counter v] by (1)
        go to (item (counter) of [Sprites v])
        move (45) steps
        say (join (item (counter) of [WaterAmounts v]) [ litres!])
        repeat (item (counter) of [WaterAmounts v])
            move (20) steps
            stamp
            wait (0.5) secs
        end
    end
    hide
    go to x: (0) y:(0)
    switch costume to [monkey2-a v]
    set size to (100) %
    show
    say [Think about ways you could use less water!] for (5) secs
```

--- /collapse

