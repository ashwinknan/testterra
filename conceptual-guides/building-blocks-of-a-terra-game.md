---
description: The high level design of any game
---

# Building Blocks of a Terra Game

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

## Summary

Games are built using four basic blocks:

* **Player**: Represents the character avatar you control.
* **GameObjects**: Construct the environment of the game.
* **Components**: Make elements interactive, allowing you to engage with the world.
* **Broadcasts**: Messages that are used by Components and GameObjects to communicate with each other



