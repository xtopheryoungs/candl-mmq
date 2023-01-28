### @explicitHints 1

# Lesson 4

## Step 1

For **Alex's** challenge, you could try to count all the **obsidian** blocks on the agent's path to the switch, but that seems like busywork.

Is there something different about the path the agent must follow and where the agent must stop to flip the switch?

#### ~ tutorialhint

Use a ``||loops:while||`` block and an ``||logic:equals (=)||`` block to compare what the ``||agent:agent inspects||`` to **obsidian**.

And have the ``||agent:agent move||`` as long as it's still standing on **obsidian**.

## Step 2

For **Bill's** challenge, the **prismarine** path that leads the agent to the switch isn't a straight line.

How can you determine when to make the ``||agent:agent turn||``?

#### ~ tutorialhint

Remember that ``||agent:agent detect (forward)||`` can be used to determine if there's a block in front of the agent.

What else needs to happen after the agent is no longer standing on **prismarine** blocks?
    
## Step 3

For **Cedric's** challenge, you're going to have to make the ``||agent:agent turn||`` quite a few times. But with the right code, you shouldn't need more than one ``||agent: agent turn||`` block.

The path to the center of the spiral is made of **cobblestone**.

#### ~ tutorialhint

Think carefully about the order of the code inside your loop. This could affect which direction the agent is facing when it reaches the center of the spiral.

## Step 4

For **Dana's** challenge, the floor is made of **Brick Blocks**. 

Is there something about the way the obstacles are placed that can lead the agent to the switch at the end?

#### ~ tutorialhint

Use ``||agent:agent detect||`` to figure out when to make the agent turn.

## Step 5

For  **Elise's** challenge, there are many different blocks, but the ``||agent:agent inspect||`` block can be compared with only one other block type at a time.

Can you use a condition that allows the agent to continue moving until it reaches the **Blocks of Iron** at the end?

#### ~ tutorialhint

For a secondary challenge, can you find a solution that uses two ``||loops:while||`` loops? It leads the agent on a much shorter path to the switch.

## Step 6

For Frank's mini-game, use an ``||player:on item used||`` event block with a **snowball** to start the game, since Frank will give you a snowball.

You need to make the ``||agent:agent move||`` upwards until it reaches the **Block of Diamond** at the top, then ``||player:say||`` that the agent has reached the top.

#### ~ tutorialhint

If the agent is moving too fast, add a ``||loops:pause||`` block to slow it down.

Try using different values for the ``||loops:pause||`` block to control the agent's speed.

## Step 7

This is the end of the tutorial. Thanks for playing!

```template
player.onChat("Alex", function () {
	
})
```

```ghost
player.onItemInteracted(SNOWBALL, function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
    agent.destroy(FORWARD)
    agent.interact(FORWARD)
    if (agent.detect(AgentDetection.Block, FORWARD)) {
        mobs.give(
        mobs.target(NEAREST_PLAYER),
        GRASS,
        1
        )
    }
    while (agent.inspect(AgentInspection.Block, FORWARD) == GRASS) {
        for (let index = 0; index < 4; index++) {
            player.say(":)")
            loops.pause(100)
        }
    }
})
blocks.onBlockBroken(GRASS, function () {
	
})
blocks.onBlockPlaced(GRASS, function () {
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
```
