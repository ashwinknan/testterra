# Basic Components of Terra Studio

Terra Studio, a versatile 3D game engine, works by using four key components: Player, Playground, Behavior and Game Systems. These components can be combined to create virtually any game supported by Terra Studio. The seamless interaction among these components provides a robust platform for developing a wide variety of games.

## Player

"Player" refers to the entity represented through a graphical avatar that acts as the user's representative within the game world, allowing for interaction with the game environment, other characters, and gameplay mechanics. You can control the player's characteristics and the nature of response to your actions through a set of "Player Properties".&#x20;

**Primary Properties**: These properties are essential attributes that define the player's initial conditions and fundamental interactions with the game:

* **Spawn Position**: The location within the game world where the player initially appears.
* **Spawn Orientation**: The direction the player is facing upon entering the game world.
* **Spawn Scale**: The size of the player's avatar upon spawning.
* **Gameplay Controller**: The system that interprets the player's input (from keyboards, mice, gamepads, etc.) into actions performed by the player's avatar.
* **Camera**: The perspective through which the player views the game world

**Behavior Specific Properties**:  These properties dictate the specific actions and reactions of the player within the game world. They directly influence how the player interacts with the environment and other entities.

## Playground

"Playground" refers to the interactive space where the game unfolds. It's essentially the world or scene that gamers interact with. This space is built using Objects and Environment.&#x20;

**Objects:** These include all the following:&#x20;

* "Assets" that are part of the game's world. Assets can range from characters, items, to structures
* "Sound Effects or SFX" that add auditory texture to the game
* "Particles or VFX", which are small graphical effects that can simulate anything from fire to rain, enhancing the visual appeal and realism of the game.

**Environment:** This refers to the global settings that affect the overall look of the game space. These settings include lighting, camera perspectives, physics properties, and global shaders that give the game its unique atmosphere.

You can alter this space where your character plays through a set of editable "Playground Properties", which when carefully designed help in creating an immersive and engaging player experience.

## Behaviour

"Behaviors" are instructions you can give to Assets that can set up the Player and the Playground to work exactly the way you want. Behaviors are basically logic blocks that you can drag and drop onto Assets. Once you add a Behavior to an Asset, you can quickly set it up to do anything: make a character jump or open a door, or even make a neighbouring Asset disappear.

Behaviors can be simple, like moving an object, or complex, incorporating conditional logic for triggering specific actions when certain criteria are met, thereby creating intricate gameplay mechanics.

## Game Systems

Game Systems are integral components that shape the overall gameplay experience. They are the foundation upon which games are built, dictating the rules, mechanics, and overall structure of the game world. Game Systems can be divided into two categories:

* **Primitive Game Systems**: These are the basic systems that handle elementary functions such as timing (e.g., countdowns, time limits), scoring (e.g., points awarded for achievements), and . They are fundamental to almost all games and provide the necessary structure for more complex systems to build upon.
* **Advanced Game Systems**: These involve more sophisticated mechanics that can include  progression mechanics (e.g., levels, unlocking features) AI behavior, economy systems (e.g., currency, trade), environmental interactions, and narrative elements. Advanced systems generally require more intricate design and programming, offering deeper and more engaging gameplay experiences.

## Game Systems versus Behaviors

Game Systems establish the structure and rules of the game world, Behaviors define the actions and reactions of its elements, thereby enabling a dynamic and interactive gameplay experience.&#x20;

* **Scope and Application**: Game Systems are the overarching frameworks that define the game's core mechanics and rules. In contrast, Behaviors are applied to individual assets within those systems to dictate their actions and reactions.
* **Complexity and Integration**: While both can range from simple to complex, Game Systems are generally more integrated and comprehensive, affecting the game as a whole. Behaviors, however, are more focused, affecting specific assets or scenarios.



