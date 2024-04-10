# Configuring the Player

At the heart of every Terra game is the "Player" block. This is the visual character that represents users in the game. Here are the different actions you can perform to configure your player in Terra Studio:&#x20;

## Finding and Selecting the Player

You can select the player by clicking on the player's avatar that is visible in the editor mode. If you are unable to find the player, you can follow these steps:&#x20;

* Click on "Essentials" in the Quick Access Menu on the left&#x20;
* Click on "PlayerControllerDrawer"
* Press the F button&#x20;

## Editing Player Characteristics&#x20;

Once you find and select the player in the editor,  the Inspector Panel on the right displays a list of customisable Player Properties. A list of these customisation actions are given below:&#x20;

### Transforming Initial Player Configurations

You can do three basic transformations of the player's initial configuration- `Move` , `Rotate` and `Scale`. When an object is selected 3 handles will appear around it, each representing an axis along which you can manipulate the object. Alternatively, you can also manually change the values in the Inspector panel to get the exact initial configuration of the player you want.&#x20;

### Selecting a Gameplay Controller

Gameplay Controller in the context of mobile or tablet gaming is a system that interprets the player's input on the touchscreen into actions and movements within the game. Terra Studio allows four types of gameplay controllers:&#x20;

* **RunForwardControllerNonAuto:** This controller requires the player to actively engage with the game by touching the screen to move the character forward. The character stops as soon as the touch is removed. Lateral movements to the left or right are controlled by swiping in the respective direction. This mode does not allow for backward movement, focusing entirely on forward progression and sidestepping.
* **RunForwardControllerAuto:** Similar in concept to the RunForwardControllerNonAuto but with a continuous forward movement mechanic. The player's character automatically moves forward, eliminating the need to constantly touch the screen for movement. Swipes to the left or right enable gradual lateral movement, diverging from instantaneous lane switches to a more fluid transition. This ensures a gameplay experience that requires strategic planning for movement while on the go.
* **TopDownController:** Offering a third-person perspective without panning, this controller enables movement in all directions, allowing players to navigate their character in a figure-eight pattern. This type of controller is designed to enhance spatial awareness and maneuvering within the game environment, providing a comprehensive view of the surrounding area to facilitate exploration and strategy.
* **TerraController (Deprecated):** Previously used for games that employ a third-person view, this controller featured separate buttons for panning the camera and for player movement. However, due to its deprecation, it is no longer recommended for use in new game designs.&#x20;

### Editing Player Motion Properties

You can alter how players move through the game space by tweaking these properties:

* **Allow Double Jump**: Toggle that enables players to perform a second jump while mid-air, adding a layer of strategy and mobility to gameplay.
* **Jump Lock**: Toggle that disables the jumping ability when using a controller that allows jumping. This can be useful for creating specific challenges or controlling player movement in certain areas.
* **Jump Height**: A numerical field where you can specify the maximum height a player can reach with a single jump. Adjusting this setting can directly affect gameplay difficulty and accessibility.
* **Ground Friction**: A numerical field where you can define how quickly players can stop or change direction while on the ground. Higher friction means faster stopping and more precise movements.
* **Air Friction**: A numerical field through which you can affects the drag experienced by players while they are airborne. This will influence how far and how fast players can move in the air.
* **Gravity**: A numerical field through which you can sets the strength of gravitational pull on the players. Higher gravity values make jumps shorter and falls faster, greatly impacting game feel and challenge
* **Deceleration Rate**: A numerical field through which you can controls how quickly players come to a stop from their maximum speed
* **Acceleration Rate**: A numerical field through which you can defines the rate at which players can reach their maximum speed. Adjusting this rate can make movement feel more sluggish or responsive
* **Max Speed**: A numerical field through which you can specify the fastest speed a player can achieve

### Editing Magnet Properties

When configuring a game character's magnetic abilities, there are key characteristics you'll need to fine-tune to affect how they interact with collectible items. Here's a quick guide:

* **Magnet Strength**: A numerical field through which you can set the power of the magnet. This affects how easily the player can attract collectible items within a given range.
* **Is MultiLevel**: Toggle setting indicating whether the magnet's strength can be upgraded. When `true`, it implies that the player can enhance their magnetic abilities based on specific game achievements or milestones.
* **Magnet Range**: A numerical field through which you can specify the radius around the player character within which the magnetic properties are effective.&#x20;

Remember, magnet properties come into play only if the scene's collectibles are configured with a trigger that responds to being "In Magnet Range". By fine-tuning these parameters, you can create a more engaging and dynamic collectible system in your game.

### Editing Player Camera Controls&#x20;

Terra Studio allows creators to edit the following camera control parameters during game play and define how users experience their game visually.&#x20;

* **Camera Arc X Rot**: A numerical field through which you can define the camera's tilt, allowing for vertical adjustments. Players can aim upwards or downwards, enhancing interactions with objects or enemies located above or below.
* **Spherical Camera Positioning**:
  * **Camera Arc X**: Manages the camera's horizontal positioning, facilitating left-right movements around a focal point.
  * **Camera Arc Y**: Governs the camera's vertical placement for up-down movements, enabling varied angles and perspectives on the game environment.
* **Field of View (FoV) / Size**: A numerical field through which you can specify the visible game world area. A narrow FoV brings the world closer, ideal for precision tasks like sniping, while a wide FoV expands the view for exploratory gameplay, although excessive width can lead to edge distortion.
* **Camera Distance**: A numerical field through which you can adjusting the camera's proximity to focus points or characters, influencing the player's depth perception and detail awareness. Closer settings heighten immersion, whereas greater distances offer expansive views of the surroundings.
* **Camera Type**: Terra Studio supports both **perspective** and **orthographic** cameras, with each type significantly affecting how players perceive and navigate the game world.

### Editing Carryable Properties

In the interest of enhancing the interaction and handling of items in-game, we introduce the following customizable properties related to the "Carryable" behavior of assets:

* **Stack Offset**: This parameter determines the vertical spacing between items when they are stacked atop one another. It ensures that items do not overlap unrealistically and maintains a visually coherent stack.
* **Limit**: This sets a cap on the number of items a player can carry simultaneously. It introduces a strategic element to gameplay, requiring players to prioritize which items are essential to carry at any given time.
* **Locator for Carryable**: Specifies the precise position of the carryable item relative to the player, once it has been collected. This feature becomes operative only when the Carryable behavior is allocated to an asset within the game scene, ensuring a realistic interaction between the player and the item.

### Editing Auto Run Properties&#x20;

When using the **RunForwardControllerNonAuto** controller, the following motion properties can be configured to adjust your movement boundaries:

* **Max Right Distance**: Defines the maximum distance you can move to the right from the starting position.
* **Max Left Distance**: Determines the maximum distance you can move to the left from the starting position.

### Editing Player Size

The Player Scale property, with a default value of 1, controls the size of the player model. For instance, Adjusting this value to 2 will increase the player's size to twice its original scale.



