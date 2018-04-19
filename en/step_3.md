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

+ Time for a bit of math! First you need somewhere to store a total. Create another variable called `totalWater`{:class="blockdata"} and set its value to `0` at the start of the program.

```blocks
    when green flag clicked
    set [totalWater v] to [0]
```

+ Go to **operators** and look for this block

```blocks
    () * ()
```

It lets you **multiply** two numbers.

+ Drag it into a `change totalWater by`{:class="blockdata"} block, like this:

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

To calculate how much water the person uses on showers each week, you'll need to ask them how many showers they have per week and multiply that by the amount of water per shower that you calculated above.

+ Ask how many showers the person has each week and create another variable to store the answer in.

```blocks
    when green flag clicked
    set [totalWater v] to [0]
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
```

+ You'll need extra multiplication operator for this bit! Drag one out and put the number of showers into the left side.

```blocks
    (showers) * ()
```

+ Then drag your previous calculation into the right hand side – so you're putting an operator inside an operator! 

```blocks
    (showers) * (((showerMinutes) * (7)))
```

+ Drag this into your `change totalWater by`{:class="blockdata"} block from earlier. Here's the full code: 

```blocks
    when green flag clicked
    set [totalWater v] to [0]
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
    change [totalWater v] by ((showers) * ((showerMinutes) * (7)))
    say [You use...] for (2) secs
    say (join(totalWater) [ litres of water per week!]) for (5) secs
```

--- challenge ---

## Challenge: Add more things

+ Add another question to find out how many times the user flushes the toilet per week.

+ Calculate how many litres of water this uses and add it to the total. Note: flushing the toilet once uses about 6 litres.

--- hints ---

--- hint ---

You'll need to create a variable to store the number of flushes per week. Use the `ask and wait`{:class="blocksensing"} and `answer`{:class="blocksensing"} blocks to get the information from the user and store it in the new variable.

--- /hint ---

--- hint ---

These blocks get the information from the user and store it.

```blocks
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
```

--- /hint ---

--- hint ---

To calculate the amount of water they use flushing the toilet, you'll need to multiply the number of flushes by `6` (the amount of water for one flush).

```blocks
    (flushes) * (6)
```

You can add the result to your total like this:

```blocks
    change [totalWater v] by (flushes) * (6)
```

--- /hint ---


--- hint ---

Your code should look something like this now:

```blocks
    when green flag clicked
    set [totalWater v] to [0]
    ask [How many minutes do you usually spend in the shower?] and wait
    set [showerMinutes v] to (answer)
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
    change [totalWater v] by ((showers) * ((showerMinutes) * (7)))
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
    change [totalWater v] by (flushes) * (6)
    say [You use...] for (2) secs
    say (join(totalWater) [ litres of water per week!]) for (5) secs
```

--- /hint ---

--- /hints ---

--- /challenge ---