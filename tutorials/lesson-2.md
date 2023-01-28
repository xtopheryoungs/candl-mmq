### @explicitHints 1

# Lesson 2

## Step 1

Use the provided ``||player:on chat command||`` event block for Abe's puzzle

You'll need to make the ``||agent:agent move||`` four times and then have the ``||agent:agent interact||`` to flip the switch.

#### ~ tutorialhint

Try using a ``||loops:repeat||`` block to reduce the amount of code you have to write.

Change the number in the ``||loops:repeat||`` block to repeat your code the correct number of times.

## Step 2

For Ben's puzzle, make a new ``||player:on chat command||`` event with **Ben** as the name.  

Can you find the pattern and use a ``||loops:repeat||`` block to have the ``||agent:agent move||`` to the spot beneath the switch?

#### ~ tutorialhint

There's a pattern that occurs **3** times to get the agent to the spot beneath the switch.

Don't forget to use ``||agent:agent interact||`` after the ``||loops:repeat||`` block.

## Step 3

For Cal's puzzle, there is a pattern but it doesn't start where the agent starts.

Use an ``||agent:agent move||`` block to put the agent at the start of the pattern, then ``||loops:repeat||`` the movement pattern.

#### ~ tutorialhint

Locate the spot in front of the switch where the agent will stop.

Follow a zigzag path backwards to find where the pattern starts.

## Step 4

For Deb's puzzle, use a ``||loops:repeat||`` block to have the agent build a column out of **Blocks of Gold**.

Use ``||agent:agent set block||`` to give the agent a block and ``||agent:agent place||`` to place the block.

#### ~ tutorialhint

``||agent:agent set block||`` has a drop-down menu with a lot of different Minecraft block types.

Use the search bar to quickly find **Block of Gold**.

## Step 5

For Eva's puzzle, there are several different ways to build the two towers.

By default, the ``||agent:agent places||`` blocks from **Slot 1**, but you can change which slot the agent uses with ``||agent:agent set active slot||``.

#### ~ tutorialhint

You can ``||agent:set blocks||`` in different slots of the agent's inventory at the start of your code.

Or you can ``||agent:set blocks||`` in the agent's inventory as necessary just before the ``||agent:agent places||`` them.

## Step 6

For Frida's section, it's up to you to have the agent create (and perhaps destroy) some interesting structures with the ``||loops:repeat||`` block.

Practice by trying to create structures similar to the examples behind the building area.

#### ~ tutorialhint

If you want to stop your code when it's running, press C to open CodeBuilder again.

Then have Frida reset the building area to clear the blocks.

## Step 7

For Gina's bonus puzzle, there's a pattern inside a pattern. Can you find both patterns?

Use ``||agent:agent destroy||`` to destroy a block in the specified direction.

#### ~ tutorialhint

What happens when you use a ``||loops:repeat||`` block inside a ``||loops:repeat||`` block?

Try using ``||agent:agent turn||`` to turn the agent around after completing one row of blocks.

## Step 8
This is the end of the tutorial. Thanks for playing.

```template
player.onChat("Abe", function () {

})
```

```ghost
player.onChat("run", function () {
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
        agent.interact(FORWARD)
        agent.place(FORWARD)
        agent.destroy(FORWARD)
        agent.setItem(GRASS, 1, 1)
        agent.setSlot(1)
    }
})

blocks.onBlockPlaced(GRASS, function () {
	player.say(":)")
})
blocks.onBlockBroken(GRASS, function () {
    
})
```
