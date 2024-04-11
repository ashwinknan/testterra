---
description: The basic building blocks of game logic in Terra Studio
---

# Configuring Behaviors

To make our game interactive, we introduce Behavior Blocks. After setting up the game area and character, Behavior Blocks bring the game to life. They change a simple, static game into an engaging world that reacts to what the player does.

## What is a Behavior?

A "Behavior" is a modular logic block that is added to an Asset.  It contains instructions on how  the Player, Assets and Game Systems should behave.  Here are some important things to remember about an asset&#x20;

1. A Behavior is always added to an Asset.
2. Execution of a Behavior is always triggered by a Behavior Start Event
3. A Behavior can affect not only the Asset to which it is attached, but also other Assets, Game Scene Objects and Game Systems&#x20;

## Start Events for Behavior blocks&#x20;

Behavior blocks in Terra Studio start executing only when one of five events occur - Mouse Click, Broadcast Listened, Player Touch, Other Object Touch and Game Start.&#x20;

### Game Start

When you set the Start Event to Game Start, the behavior begins as soon as the game starts.&#x20;

### Mouse Click

When you click your mouse, the Behavior begins.

### Player Touch

When the Start Event is set to either Player Touch or Player Collide, the Behavior activates immediately after the Player touches or collides with the Asset’s collider.

### Other Object Touch

When the Start Event is "Other Object Touch," the Behavior starts when the other object's collision boundary touches the collision boundary of the object with the Behavior.

### Broadcast Listened

When you choose "Broadcast Listened" as the Start event, the Behavior only starts if it gets a specific signal. You must name the trigger signal. For example, if you set "Broadcast Listened" to react to `portal_opened`, then the Behavior will only start when the `portal_opened` signal occurs in the game.

## Effects of Behavior Blocks

A Behavior block when added to an Asset can be set up to not only affect that Asset, but also other Assets, the Player, the Game Scene or even Game Systems. The most common effects of Behavior blocks are :&#x20;

* Change in Player or Asset properties&#x20;
* Change in Game Scene Environment
* Change in Game Systems&#x20;
* Change in an Asset's Orientation&#x20;
* Trigger another behavior
* Enable an SFX or Particle
* Create or Elimination existing Game Scene Objects.

These effects can be configured in the Editable Properties of each behavior.&#x20;

## Adding Behavior Blocks

To add behavior to an asset and customise it, follow these steps:

1. Select the Asset in the scene editor or through the Layers Panel.
2. Click Add Behaviour in the Inspector Panel.
3. You'll see selector with a search bar listing all possible behaviors. Choose the behavior you want and click "OK".
4. The Behavior has been added to the Asset. Scroll down in the Inspector panel to customize it. You can change its settings using the fields provided.
5. Once you make changes, click the Save button in the main toolbar.&#x20;

## Parallel Execution of Behavior Blocks

You can add multiple Behaviors on the same Asset, each of which can function independently and gets independently triggered by its own Start Event. &#x20;

## Sequential Execution of Behaviors&#x20;

You can execute behaviors sequentially one after the other  with broadcast signals. You need to do the following:

1. **First Behavior - Sending Signal**
   * Set the action of the first behavior to **Broadcast Custom signal**.
   * For the signal value, input any alphanumeric signal name. This will be sent out once the behavior completes its task.
2. **Second Behavior - Waiting for Signal**
   * Change the Start Event of the second behavior to **Broadcast Listened**.
   * Specify the alphanumetic signal you set in the first step as the signal to listen for. This ensures the behavior only starts after receiving signal from the first behavior.

### Behavior Categories

To streamline development, behaviors are grouped into three distinct categories:

* **Dependent Behaviors:** Function based on other behaviors or specific events.
* **Independent Behaviors:** Operate without any external dependencies.
* **Joiners:** Serve as a bridge, connecting various behaviors together.

This structured approach to behaviors in Terra Studio significantly eases the game development process, enabling creators to bring their visions to life with greater efficiency and less technical complexity.

#### **Independent Behaviors:**

1. Click
2. [Collectable](https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/\~/changes/59/overview/terra-studio-component-overview/behaviour/behavior-categories/collectable)
3. Collider&#x20;
4. Destroy Self
5. Grow or shrink
6. Instantiate&#x20;
7. Jump
8. Pad
9. Load scene
10. Reset player Health
11. Increase player Health
12. Decrease player Health
13. Modify&#x20;
14. Reset Score&#x20;
15. Reset Timer
16. Kill player
17. Rotate (Oscillate)&#x20;
18. Rotate
19. Teleport self
20. Teleport player
21. Move
22. Update Score
23. Update Timer
24. Update Magnet
25. Move to Player&#x20;
26. Teleport
27. Carriable
28. Cinematic&#x20;
29. Advance move
30. Kill player old&#x20;
31. Advance rotate&#x20;
32. Play player's animation&#x20;
33. Level up
34. Debris Destructible&#x20;
35. Destroy On Persistence
36. Instantiate on element
37. Instantiate persistently&#x20;

Dependent Behaviour:

1. Stop object animation&#x20;
2. Stop player movement
3. Stop rotate&#x20;
4. Stop move
5. Start player movement
6. Deposit&#x20;
7. Debris&#x20;

#### Joiners:&#x20;

1. Delay
2. Or operator&#x20;
3. And operator&#x20;

