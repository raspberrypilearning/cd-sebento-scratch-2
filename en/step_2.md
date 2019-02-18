## Getting information from the user

On this card you'll make the water usage calculator. To personalise the calculation for your program's user, you'll use a new block to ask them questions that they can type in answers to.

--- task ---
Open a new Scratch project and go to the Costumes tab for the cat sprite.

Add a new costume from the library. Choose a character that will do some talking. I'm using this monkey:

![The talking monkey costume](images/askMonkeyCostume.png)
--- /task ---

--- task ---
Click on the Scripts tab and add the following blocks to your sprite. You will find the `ask and wait`{:class="block3sensing"} block in the **Sensing** category.

```blocks3
+    when green flag clicked
+    set size to (80) %
+    switch costume to [monkey-a v]
+    ask [What's your name?] and wait
```
--- /task ---

--- task ---
Change the question to `How many times do you flush the toilet each week?`.
--- /task ---

You've asked the user for information — now you need to get the answer.

--- task ---
First, create a variable called `flushes`{:class="block3variables"}. You will use it to store the user's answer.

[[[generic-scratch3-add-variable]]]
--- /task ---

--- task ---
Drag out the `set flushes to`{:class="block3variables"} block from **Variables**.
--- /task ---

--- task ---
Then, look in the **Sensing** section and find the `answer`{:class="block3sensing"} block. This is a special variable where a Scratch program puts the most recent answer it's received from an `ask and wait`{:class="block3sensing"} block.

Plug the block into your code like this:

```blocks3
    when green flag clicked
    set size to (80) %
    switch costume to [monkey-a v]
    ask [How many times do you flush the toilet each week?] and wait
+    set [flushes v] to (answer)
```
--- /task ---

Time for a bit of math! First you need somewhere to store a total.

--- task ---
Create another variable called `totalWater`{:class="block3variables"} and set its value to `0` at the start of the program.

```blocks3
+    when green flag clicked
+    set [totalWater v] to [0]
```
--- /task ---

--- task ---
Go to **Operators** and look for this block:

```blocks3
    () * ()
```

It lets you **multiply** two numbers.

Drag it into a `change totalWater by`{:class="block3variables"} block, like this:

```blocks3
    change [totalWater v] by (() * ())
```
--- /task ---

--- task ---
Plug your `flushes`{:class="block3variables"} block into one side of the operator block and on the other side, type in the number `6`. 6 litres is roughly how much water is used for one toilet flush.

```blocks3
    when green flag clicked
    set [totalWater v] to [0]
    set size to (80) %
    switch costume to [monkey-a v]
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
+    change [totalWater v] by ((flushes) * (6))
```
--- /task ---

--- task ---
Finish off the script with a couple of `say`{:class="block3looks"} blocks to tell the user the result! You'll find the `join`{:class="block3operators"} block in **Operators**.

```blocks3
    when green flag clicked
    set [totalWater v] to [0]
    set size to (80) %
    switch costume to [monkey-a v]
    ask [How many times do you flush the toilet each week?] and wait
    set [flushes v] to (answer)
    change [totalWater v] by ((flushes) * (6))
+    say [You use...] for (2) secs
+    say (join(totalWater) [ litres of water each week!]) for (5) secs
```
--- /task ---

--- task ---
Click the green flag to test your code.
--- /task ---
