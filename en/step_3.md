## Challenge: add more water uses to the calculation

Add another question to find out how many showers the person has per week. Then calculate how many litres of water this uses and add it to the total. 

A shower uses about 7 litres per minute, so a five-minute shower uses around 35 litres.

--- hints ---

--- hint ---

+ You'll need to create a variable to store the number of showers per week. 

+ Use the `ask and wait`{:class="block3sensing"} and `answer`{:class="block3sensing"} blocks to get the information from the user and store it in the new variable.

```blocks3
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
```

--- /hint ---

--- hint ---

+ To calculate the amount of water used on showering, you'll need to multiply the number of showers by `35` (the amount of water for one five-minute shower).

```blocks3
    (showers) * (35)
```

+ You can add the result to your total like this:

```blocks3
    change [totalWater v] by ((showers ::variables) * (35))
```

--- /hint ---

--- hint ---

Your code should look something like this now:

```blocks3
    when green flag clicked
    set [totalWater v] to [0]
    set size to (80) %
    switch costume to [monkey-a v]
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
    change [totalWater v] by ((flushes) * (6))
    ask [How many showers do you have per week?] and wait
    set [showers v] to (answer)
    change [totalWater v] by ((showers) * (35))
    say [You use...] for (2) secs
    say (join(totalWater) [ litres of water per week!]) for (5) secs
```

--- /hint ---

--- hint ---

If you want to, you can also ask them how many minutes they spend in the shower! In that case, you would need to do an extra calculation: multiply the number of minutes by `7` (litres per minute in the shower), and then multiply the result by the number of showers. You can put an operator inside an operator to do that, like this:

```blocks3
    (showers) * ((showerMinutes ::variables) * (7))
```

Here's how your code would look:

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
```
--- /hint ---

--- /hints ---