## Make a water calculator

+ Open a new Scratch project and go to the Scripts tab for the cat sprite.

+ Add the following blocks. You will find the `ask and wait`{:class="blocksensing"} block in the **sensing** category.

```blocks
    when green flag clicked
    ask [What's your name?] and wait
```

+ Change the question to `How many minutes do you usually spend in the shower?`{:class="blocksensing"} .

You've asked the user for information, now you need to get the answer! 

+ First, create a variable called `showerMinutes`{:class="blockdata"}. You will use it to store the answer.

[[[generic-scratch-add-variable]]]

+ Drag out the `set showerMinutes to`{:class="blockdata"} block from **data**.

+ Then, look in the **sensing** blocks and find the `answer`{:class="blocksensing"} block. This is a special variable that Scratch has where it puts the most recent answer it's received from an `ask and wait`{:class="blocksensing"}

+ Plug the block into your code like this:

```blocks
    when green flag clicked
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
```

Time for a bit of math! 

+ Create another variable called `totalWater`{:class="blockdata"} and set its value to `0` at the start of the program.

```blocks
    when green flag clicked
    set [totalWater v] to [0]
```

+ Add a `change totalWater by`{:class="blockdata"} to your code.

+ Go to **operators** and look for this block

```blocks
    () * ()
```

It lets you **multiply** two numbers.

+ Drag it into your `set [totalWater v] to []`{:class="blockdata"} block, like this:

```blocks
    change [totalWater v] by (() * ())
```

+ Plug your `showerMinutes`{:class="blockdata"} block into one side of the operator block and in the other side, type in the number `7`.

```blocks
    when green flag clicked
    set [totalWater v] to [0]
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    change [totalWater v] by ((showerMinutes) * (7))
```

+ Finish off the code with a couple of `say`{:class="blocklooks"} to tell the user the answer! You'll find the `join`{:class=:"blockoperator"} block in **operators**.

```blocks
    when green flag clicked
    set [totalWater v] to [0]
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    change [totalWater v] by ((showerMinutes) * (7))
    say [You use...] for (2) secs
    say (join(totalWater) [ litres of water per shower!]) for (5) secs
```

+ Click the green flag to test your code.