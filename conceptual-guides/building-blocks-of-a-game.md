---
description: The high level design of any game
---

# Building Blocks of a Game

Any game in Terra consists of four basic blocks -  Player, GameObjects, Components and Broadcasts

## Player

At the core of any game in Terra lies the "Player" , which is the graphical avatar representing players in the game world. The Player is customisable through a collection of editable features called Player Properties

## GameObjects

Having a player isn't enough for a game. You need GameObjects which the  the player can explore and interact with. Without GameObjects, the player would just have a big empty space. There are three main types of GameObjects in Terra Studio:

* The "Asset" GameObject - Any 3D object that is part of the game's world.&#x20;
* The "SFX" GameObject - A GameObject with a Sound file attached to it
* The "Particle" GameObject - A GameObject with a visual effect or a particle effect attached to it

## Components

Simply having a Player block and a GameObject block won't create an engaging game experience. Interactivity is key, and this is where Components plays a pivotal role. They are the essence of gameplay, turning a static scene into an immersive, interactive world. Components are attached to GameObjects in a way where you can program the Components  to follow specific instructions, enabling interactivity in the game in precisely the ways you want.

Integrating Components into your game transforms the game into dynamic, interactive elements. Without Components, you're left with a mere navigation through static scenes.&#x20;

A lot of Components for game logic are pre-built in the form of Logic Templates or Game Systems. However, you can also build your own Components using scripting.&#x20;

## Broadcasts

Broadcasts are messages that are used by Components and GameObjects to communicate with each other. There are a few readily available broadcasts in the editor&#x20;

* **Game Win**: It is the broadcast message automatically generated when the player meets the win condition for a game
* **Game Lose**: It is the broadcast message automatically generated when the player meets the lose condition for a game
* **Custom Broadcast**: This lets you send a unique alert whenever a specific game condition happens. You can name each custom signal differently - and this is usually a string field.

## Putting it all together

In a game, the player’s journey is shaped by the seamless interaction of these four core components: Player, GameObjects, Components, and Broadcasts. Here's how these elements work together to create an immersive experience:

1. **Starting as the Player**
   * The journey begins with the **Player**, the avatar representing the user within the game world. As the player steps into the game, they control this avatar, navigating through the environment and interacting with the world around them.
2. **Interacting with GameObjects**
   * As the Player moves through the game, they encounter various **GameObjects**. These are the elements that fill the game world—3D assets, sound effects, and particle effects—that make the environment rich and engaging. GameObjects provide the physical and visual context within which the player’s journey unfolds.
3. **Engaging with Components**
   * However, simply moving through a world of GameObjects would be a passive experience without the **Components** that bring it to life. Components are attached to GameObjects, turning them from static objects into interactive elements. For example, when the Player approaches a door (a GameObject), a Component might trigger the door to open. Similarly, picking up an item might increase the Player's score or trigger a sound. Components are the rules and logic that govern how GameObjects respond to the Player, making the game interactive and engaging.
4. **Triggering Events with Broadcasts**
   * Throughout the journey, certain actions or events need to be communicated across different parts of the game. This is where **Broadcasts** come into play. For instance, when the Player reaches the end of a level, a "Game Win" Broadcast might be sent out, triggering the display of a victory screen. Or if the Player loses all their health, a "Game Lose" Broadcast could initiate the game-over sequence. **Custom Broadcasts** allow for more specific interactions, such as triggering an alarm when the Player steps into a restricted area. Broadcasts ensure that all game elements work together, responding to the Player’s actions in real-time.

## Summary

Games are built using four basic blocks:

* **Player**: Represents the character avatar you control.
* **GameObjects**: Construct the environment of the game.
* **Components**: Make elements interactive, allowing you to engage with the world.
* **Broadcasts**: Messages that are used by Components and GameObjects to communicate with each other



