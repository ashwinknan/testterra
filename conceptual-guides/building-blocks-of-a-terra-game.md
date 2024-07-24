---
description: The high level design of any game
---

# Building Blocks of a Terra Game

Any game in Terra consists of four basic blocks -  Player, Game Scene, Game Logic and Game System.&#x20;

## Player

At the core of any game in Terra lies the "Player" , which is the graphical avatar representing players in the game world. The Player is customisable through a collection of editable features called Player Properties

## Game Scene

Having a player isn't enough for a game. You need a scene where the player can explore and interact. Game Scene blocks let you build this world. Without them, the player would just have a big empty space. There are four main types of Game Scene blocks:

* The "Asset" block - Any 3D object that is part of the game's world.&#x20;
* The "SFX" block - Any sound effect  that is added to the game
* The "Particle" block - Any visual graphical effect simulating anything from fire to rain to enhance the visual appeal and realism of the game
* The "Environment" block**:** This refers to the global settings that affect the overall look of the game space. Includes lighting, camera perspectives, and global shaders that give the game its unique atmosphere.

Each of these blocks is customizable & configurable through an associated set of editable properties.&#x20;

Each game can have multiple scenes.&#x20;

## Game Logic

Simply having a Player block and a Game Scene Object block won't create an engaging game experience. Interactivity is key, and this is where Game Logic plays a pivotal role. They are the essence of gameplay, turning a static scene into an immersive, interactive world. Game Logic is always added to Asset Blocks. That way you can program Asset blocks to follow specific instructions, enabling interactivity in the game in precisely the ways you want.

Integrating Game Logic into your game transforms the game into dynamic, interactive elements. Without Game Logic, you're left with a mere navigation through static scenes. It's the Game Logic that turns these scenes into a captivating game.

## Game System

Creating an engaging game requires more than just setting up Game Logic for individual Asset blocks. It's essential to establish a broader framework that outlines the game's fundamental mechanics and rules. This is achieved through the Game Systems. Unlike Game Logic, which dictates how specific assets react, the Game System influences the entire game's operation.

Game Systems can be divided into two categories:

* **Primitive**: These are the basic systems that handle elementary functions such as timing (e.g., countdowns, time limits), scoring (e.g., points awarded for achievements). They are fundamental to almost all games and provide the necessary structure for more complex systems to build upon.
* **Advanced**: These involve more sophisticated mechanics that can include progression mechanics (e.g., levels, unlocking features) AI behavior and economy systems (e.g., currency, trade)

## Game Signals

Game Signals are a mechanism for different blocks to communicate. Common game signals are Game Win , Game Lose or Custom Broadcast&#x20;

### Game Win

It is the signal generated when the player meets the win condition for a game

### Game Lose

It is the signal generated when the player meets the lose condition for a game

### Custom Broadcast

In Terra Studio, the most crucial tool is a custom broadcast signal. This lets you send a unique alert whenever a specific game condition happens. You can name each custom signal differently.

#### Generating a Broadcast Signal

The Custom Broadcast can be generated by any Game Logic, any SFX, any Particle or any Game System. Each broadcast signal is identified by a unique name that you can give it.&#x20;

#### Listening to a Broadcast Signal

Creating a Custom Broadcast isn't enough on its own. It becomes valuable only when there are broadcast listeners set up to receive it. In Terra Studio, Game Logic, Sound SFX, Particles, and Game Systems can all "listen" for these broadcast signals.

Multiple listeners can all receive and act on the same broadcast signal at the same time.&#x20;

## Summary

Games are built using several types of blocks:

* **Player**: Represents the character avatar you control.
* **Game Scene**: Construct the environment of the game.
* **Game Logic**: Make elements interactive, allowing you to engage with the world.
* **Game Systems**: Define the rules and dynamics that keep the game enjoyable and challenging, such as scoring and difficulty progression.


