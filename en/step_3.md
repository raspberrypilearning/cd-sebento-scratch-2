## Make a water calculator

+ Open a new Scratch project and go to the Scripts tab for the cat sprite.

+ Add the following blocks. You will find the `ask and wait`{:class="blocksensing"} in the **sensing** category.

```blocks
    when green flag clicked
    ask [What's your name?] and wait
```

+ Change the question to `How many minutes do you usually spend in the shower?`.

You've asked the user for information, now you need to get the answer! 

+ First, create a variable called `showerMinutes`. You will use it to store the answer.

[[[generic-scratch-add-variable]]]

+ Drag out the `set [showerMinutes v] to []`{:class="blockdata"} block from **data**.

+ Then, look in the **sensing** blocks and find the `answer`{:class="blocksensing"} block. This is a special variable that Scratch has where it puts the most recent answer it's received from an `ask and wait`{:class="blocksensing"}

+ Plug the block into your code like this:

```blocks
    when green flag clicked
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
```

+ Time for a bit of math! Create another variable called `totalWater`{:class="blockdata"} and add the `set [totalWater v] to []`{:class="blockdata"} to your code.

+ Go to the **operators** blocks and look for this block

```blocks
    () * ()
```

It lets you **multiply** two numbers.

+ Drag it into your `set [totalWater v] to []`{:class="blockdata"} block, like this:

```blocks
    set [totalWater v] to (() * ())
```

+ Put your `showerMinutes`{:class="blockdata"} block into one side of the operator block and in the other side, type in the number `7`.

```blocks
    when green flag clicked
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    set [totalWater v] to ((showerMinutes) * (7))
```

+ Finish off the code with a couple of `say`{:class="blocklooks"} to tell the user the answer!

```blocks
    when green flag clicked
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    set [totalWater v] to ((showerMinutes) * (7))
    say [The number of litres of water you use per shower is...] for (5) secs
    say (totalWater) for (3) secs
```