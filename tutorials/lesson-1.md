### @explicitHints 1

# Lesson 1

## Step 1
For Barry's puzzle, place an ``||agent:agent move||`` block in the ``||player:on chat command||`` block.  Set the direction and distance to make the agent walk up to the switch. 

Use  ``||agent:agent interact||`` to make the agent flip the switch.

#### ~ tutorialhint
Type **Barry** in the chat to run your code.

## Step 2
For Carrie's puzzle, make a new ``||player:on chat command||`` event and change the text to **Carrie**.

Use ``||agent:agent move||`` and ``||agent:agent interact||`` to complete the task. You may also want to use ``||agent:agent turn||`` in your solution.

#### ~ tutorialhint
Use the drop-down menu in the ``||agent:agent move||`` and ``||agent:agent turn||`` blocks to change direction.

Type **Carrie** in the chat to run your code.

## Step 3

For Dale's puzzle, make another ``||player:on chat command||`` event  and change the text to **Dale**.  

The ``||agent:agent interact||`` block doesn't just flip switches; it can open gates too.

#### ~ tutorialhint
The ``||agent:agent interact||`` block allows you to change which direction the agent interacts.

Type **Dale** in the chat to run your code.

## Step 4

For Elizabeth's section, you get to create your own puzzle. Go upstairs and talk to the Puzzle Master if you haven't already.

When your puzzle is ready, use an ``||player:on chat command||`` event with **Elizabeth** as the name and code your solution.

#### ~ tutorialhint
If you change your puzzle, you can change your solution or make another ``||player:on chat command||`` block with a new name.

## Step 5

This is the end of the tutorial. Thanks for playing.

```template
player.onChat("Barry", function () {
})
```

```ghost
player.onChat("jump", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
    agent.interact(FORWARD)	
})
```
