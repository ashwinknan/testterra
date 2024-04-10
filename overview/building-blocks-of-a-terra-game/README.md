---
description: The high level design of any game
---

# Building Blocks of a Terra Game

Any game in Terra consists of four basic blocks -  Player, Game Scene, Behaviour and Game System.&#x20;

## Player

At the core of any game in Terra lies the "Player" block, which is the graphical avatar representing players in the game world. This block is customisable through a collection of editable features known as "Player Properties".

## Game Scene

Having a player isn't enough for a game. You need a scene where the player can explore and interact. Game Scene blocks let you build this world. Without them, the player would just have a big empty space. There are four main types of Game Scene blocks:

* The "Asset" block - Any 3D object that is part of the game's world.&#x20;
* The "SFX" block - Any sound effect  that is added to the game
* The "Particle" block - Any visual graphical effect simulating anything from fire to rain to enhance the visual appeal and realism of the game
* The "Environment" block**:** This refers to the global settings that affect the overall look of the game space. Includes lighting, camera perspectives, and global shaders that give the game its unique atmosphere.

Each of these blocks is customizable & configurable through an associated set of editable properties. &#x20;

## Behaviour

Simply having a Player block and a Game Scene Object block won't create an engaging game experience. Interactivity is key, and this is where Behavior blocks play a pivotal role. They are the essence of gameplay, turning a static scene into an immersive, interactive world. With Behavior blocks, you can program Asset blocks to follow specific instructions, enabling the Player block to interact with the Game Scene blocks in precisely the ways you want.

Integrating Behavior blocks into your game transforms static Asset blocks into dynamic, interactive elements. Without Behavior blocks, you're left with a mere navigation through static scenes. It's the Behavior blocks that turn these scenes into a captivating game.

## Game System

Creating an engaging game requires more than just setting up Behavior blocks for individual Asset blocks. It's essential to establish a broader framework that outlines the game's fundamental mechanics and rules. This is achieved through the Game System block. Unlike the Behavior block, which dictates how specific assets react, the Game System block influences the entire game's operation.

Game Systems can be divided into two categories:

* **Primitive**: These are the basic systems that handle elementary functions such as timing (e.g., countdowns, time limits), scoring (e.g., points awarded for achievements). They are fundamental to almost all games and provide the necessary structure for more complex systems to build upon.
* **Advanced**: These involve more sophisticated mechanics that can include progression mechanics (e.g., levels, unlocking features) AI behavior and economy systems (e.g., currency, trade)

## Summary

In summary, games are made with a "Player" block for the character avatar you control, and "Game Scene" blocks to build the world around them. "Behaviour" blocks make everything interactive, letting you play in the world. "Game System" blocks are the rules and setups that make the game fun and challenging, covering everything from keeping score to making things harder as you go.



