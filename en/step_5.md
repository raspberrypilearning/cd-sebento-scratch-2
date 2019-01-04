## Matching things up

Now that you've got the water amounts in a list, you're going to put the sprite names in another list. Since the sprite names and the water amounts are related to each other, you'll be using the same counter variable to keep track of which list item you're on in both lists.

+ Make another list and call it `Sprites`{:class="block3variables"}.

+ Add two items to the list: `Tap` and `Toilet`. Make sure that what you type is exactly the same as the names of the `Tap` and `Toilet` sprites!

+ Once you're done adding things to the list, you can hide it from the stage.

+ Now look at your script with the loops and find the two `go to`{:class="block3motion"} blocks that make the talking sprite move to the `Tap` and the `Toilet` sprites.

![blocks_1546557380_418138](images/blocks_1546557380_418138.png)

+ Just like you did before, drag an `item`{:class="block3variables"} block into each one — it doesn't look like you can place something else into the box, but you can! Give it a try.

![blocks_1546557381_479629](images/blocks_1546557381_479629.png)

+ Your code should look like this now:

![blocks_1546557382_570534](images/blocks_1546557382_570534.png)

Do you see that you are now using the same **index** to select the sprite name from a list and the matching water amount from the other list? This is the perfect opportunity to use a variable. Let's do that now!

+ Create a new variable called `counter`{:class="block3variables"}.

+ At the start of the program, set the value of `counter`{:class="block3variables"} to `0`:

![blocks_1546557383_729176](images/blocks_1546557383_729176.png)

+ Drag the `counter`{:class="block3variables"} block into the four blocks where you get an item from a list, in place of the numbers `1` and `2`.

![blocks_1546557384_804162](images/blocks_1546557384_804162.png)

![blocks_1546557385_897502](images/blocks_1546557385_897502.png)

One thing is still missing: the value of `counter`{:class="block3variables"} is `0` at the moment! You need to set it to the correct value before you use it each time. To do this, you will add `1`. This is also known as **incrementing**.

+ Add in two `change counter by 1`{:class="block3variables"} blocks into your code so that it looks like this:

![blocks_1546557386_976539](images/blocks_1546557386_976539.png)

+ Run your code to check that everything is still working as it should! Here is what the full program should look like by now:

![blocks_1546557388_149](images/blocks_1546557388_149.png)

On the next card you will learn how to make your code even shorter with another clever loop!
