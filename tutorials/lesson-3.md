### @explicitHints 1

# Lesson 3

## Step 1

For **Ana's** puzzle, you'll need to have the ``||agent:agent move||`` forward **30** times, so the ``||loops:repeat||`` block is already set to **30**.  Use ``||agent:agent destroy||`` to clear the blocks in its path.

Can you add the code to help the agent get to the end and have the ``||agent:agent interact||`` with the switch?

#### ~ tutorialhint

Try using an ``||logic:if||`` block to have the ``||agent:agent detect||`` whether there's a block in its path.

## Step 2

For **Bea's** puzzle, the path is still **30** blocks long, so the ``||loops:repeat||`` block still needs to be set to **30**.

But make sure to have the ``||agent:agent destroy||`` only the blocks that are in the way. We want to leave the torches intact.

#### ~ tutorialhint

Having the ``||agent:agent destroy||`` only ``||logic:if||`` the ``||agent:agent detects||`` a block in the way sounds similar to the previous problem.

## Step 3

For **Craig's** puzzle, the path is **30** blocks long again, but the placement of blocks and torches has changed.

But do the changes to the blocks and torches even make a difference?

#### ~ tutorialhint

Have you tried using the code you've already written to see if it can also work for this problem?

## Step 4

For **Diane's** puzzle you'll still need to have the ``||agent:agent move||`` forward **30** times.

But can you figure out when to have the ``||agent:agent move||`` up? And don't forget to have the ``||agent:agent interact||`` to flip the switch at the end.

#### ~ tutorialhint

Use an ``||logic:if||`` block to have the ``||agent:agent detect||`` whether to ``||agent:move||`` up.

## Step 5

For **Ella's** puzzle this new maze layout may look intimidating, but can you find a path for the agent to follow to get to the switch?

#### ~ tutorialhint

Does the same strategy from the **Diane's** puzzle apply to this puzzle too?

## Step 6

For **Fred's** mini-game, the goal is to collect an **Emerald**, a **Diamond**, a **Gold Nugget**, and an **Iron Nugget**. There are four different types of ``||mobs:monsters||`` to defeat.

To start, place an ``||mobs:on animal killed||`` event block, then put a ``||mobs:monster||`` block to replace the ``||mobs:animal||``.

#### ~ tutorialhint

Your event should say ``||mobs:on monster (egg) killed||``. The blue egg represents a **Zombie**.

## Step 7

Use the ``||blocks:test for||`` block to determine ``||logic:if||`` an ``||blocks:item||`` should be given.  Click the hint for more info.

Can you write code to make it so that killing a **Zombie** will ``||mobs:give||`` you an **Emerald** ``||blocks:item||`` only ``||logic:if||`` you're standing on a **Block of Emerald**``?

#### ~ tutorialhint

Use the ``||blocks:test for||`` block with the coordinates **(0, -1, 0)** to check ``||logic:if||`` you're standing on a certain block type.

## Step 8

Use three more ``||mobs:on monster killed||`` events to get the other items.  

Defeating a **Drowned** ``||logic:if||`` you're on a **Block of Diamond** should ``||mobs:give||`` a **Diamond** ``||blocks:item||``. Defeating a **Zombie Pigman** ``||logic:if||`` you're on a **Block of Gold** should ``||mobs:give||`` a **Gold Nugget** ``||blocks:item||``.

#### ~ tutorialhint

And defeating a **Spider** (not a Cave Spider) ``||logic:if||`` you're on a **Block of Iron** should ``||mobs:give||`` an **Iron Nugget**.

Don't forget about ``||blocks:test for||`` with **(0, -1, 0)** to check what you're standing on.

## Step 9

This is the end of the lesson. Have fun playing the mini-game!

```template
player.onChat("ana", function () {
    for (let index = 0; index < 30; index++) {
    	
    }
})
```

```ghost
mobs.onMobKilled(mobs.monster(SKELETON), function () {
    if (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.interact(FORWARD)
        agent.turn(LEFT_TURN)
        player.say(":)")
    }
    if (blocks.testForBlock(GRASS, pos(0, 0, 0))) {
        mobs.give(
        mobs.target(NEAREST_PLAYER),
        IRON_SHOVEL,
        1
        )
    }
})

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
	
})
blocks.onBlockBroken(GRASS, function () {
	
})
```
