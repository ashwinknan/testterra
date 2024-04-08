---
description: The basic building blocks of game logic in Terra Studio
---

# Behaviour

## Understanding Behaviors in Terra Studio

In Terra Studio, a "behavior" is a key component that allows game developers to bring specific functionalities to life within their projects seamlessly, without any coding knowledge. Each behavior acts as a modular logic block that can be easily assigned to Assets through a drag-and-drop interface, followed by a simple configuration to meet the game’s design requirements.

These behaviors are highly customizable, featuring adjustable parameters that empower developers to fine-tune their games to perfection. At its core, a behavior is defined by its trigger and the subsequent outcome it brings into the gaming environment.

Behaviors, this refer to the scripts or logic assigned to individual assets within the game environment. These assets can be characters, objects, or any element that players can interact with or that can perform actions automatically. Behaviors are what make the game world dynamic and responsive to player actions. They can range from simple (e.g., moving an object) to complex (e.g., an NPC making decisions based on the player's actions) systems, depending on the game's requirements.&#x20;

Behaviors are characterized by:

* **Modularity**: Behaviors are often designed as modular logic blocks that can be easily attached to or detached from assets, allowing for flexible and reusable code.
* **Interactivity and Responsiveness**: They directly influence how assets react to player inputs or other in-game events, creating an interactive gameplay environment.
* **Customizability**: Developers can quickly implement and adjust behaviors to fine-tune the game's feel and mechanics, often without altering the core game systems.

### Trigger

There are two primary categories of triggers:

#### Interaction-Based Triggers

These triggers are activated by direct player interaction within the playground. They include:

* **Mouse Clicks:** Actions are initiated by clicking on various elements in the game.
* **Player-Asset Collisions:** Triggered when the player's character interacts with Assets.
* **Asset-Asset Collisions:** Activated through interactions between assets.

#### Event-Based Trigger

Other occurrences in the game can also act as triggers. For example, reaching significant game milestones like the start of the game or checkpoints, or receiving a broadcast from another event.

### Outcome:&#x20;

The activation of a trigger can lead to various outcomes, such as:

* Change in player or asset properties&#x20;
* Change in environment
* Change in game systems&#x20;
* Change in asset's orientation&#x20;
* Trigger another behavior
* Visual or auditory effects
* Creation or elimination game objects.

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
