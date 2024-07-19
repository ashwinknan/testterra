# Configuring the Player

At the heart of every Terra game is the "Player" block. This is the visual character that represents users in the game. Here are the different actions you can perform to configure your player in Terra Studio:&#x20;

## Finding and Selecting the Player

You can select the player by clicking on the player's avatar that is visible in the editor mode. If you are unable to find the player, you can follow these steps:&#x20;

* Click on "Layers" in the Quick Access Menu on the left&#x20;
* Locate and Click on "Player".&#x20;
* Press the F button&#x20;

You will notice that the Player has a default child element TopDownPlayer  which in turn has two more children - ModelRoot and CameraRoot

## Editing Player Characteristics&#x20;

Once you find and select the player in the editor,  the Inspector Panel on the right displays a list of customisable Player Properties. A list of these customisation actions are given below:&#x20;

### Transforming Initial Player Configurations

To do this, you need to select the topmost parent  element in the Layers , named Player.&#x20;

You will notice that can do three basic transformations of the player's initial configuration- `Move` , `Rotate` and `Scale`. When an object is selected 3 handles will appear around it, each representing an axis along which you can manipulate the object. Alternatively, you can also manually change the values in the Inspector panel to get the exact initial configuration of the player you want.&#x20;

### Selecting a Gameplay Controller

Gameplay Controller in the context of mobile or tablet gaming is a system that interprets the player's input on the touchscreen into actions and movements within the game.&#x20;

To change the player controller,  you need to select the topmost parent element in the Layers , named Player.&#x20;

When you select Player, you will see a dropdown on the inspector panel named Controller which shows the TopDown controller by default.&#x20;

**The TopDownController** Offers a third-person perspective without panning, this controller enables movement in all directions, allowing players to navigate their character in a figure-eight pattern. This type of controller is designed to enhance spatial awareness and maneuvering within the game environment, providing a comprehensive view of the surrounding area to facilitate exploration and strategy.

There are also other controlles which are currently hidden.&#x20;

* **RunForwardControllerNonAuto:** This controller requires the player to actively engage with the game by touching the screen to move the character forward. The character stops as soon as the touch is removed. Lateral movements to the left or right are controlled by swiping in the respective direction. This mode does not allow for backward movement, focusing entirely on forward progression and sidestepping.
* **RunForwardControllerAuto:** Similar in concept to the RunForwardControllerNonAuto but with a continuous forward movement mechanic. The player's character automatically moves forward, eliminating the need to constantly touch the screen for movement. Swipes to the left or right enable gradual lateral movement, diverging from instantaneous lane switches to a more fluid transition. This ensures a gameplay experience that requires strategic planning for movement while on the go.

### Editing Player Motion Properties

You can alter how players move through the game space. To edit these properties, you need to select the TopDown Player element (child of the Player element). Once you select it, you can by tweak these properties:

* **Lock to Look Sideways**: Toggle button to lock or unlock sideways view.
* **Scale**: Adjust the player's size (1 = Default).
* **Gravity**: Numerical field to set gravity strength. Higher values make jumps shorter and falls faster, affecting game difficulty.
* **Jump Height**: Set the maximum height for a player's jump. This influences gameplay difficulty and accessibility.
* **Jump Lock**: Toggle to disable jumping via a controller. Useful for creating specific challenges or controlling movement in certain areas.
* **Max Speed**: Define the player's maximum achievable speed.

### Editing Player Animation

The Player's animation can be edited by selecting the `ModelRoot` element under the `TopDownPlayer` element in Layers. The following animations can be edited by choosing from a list of pre-existing animations:

* Idle&#x20;
* Forward Running
* Back Waling
* Walking Forward
* Walk to Right
* Walk Left
* On Jump Start
* While in Air
* On Jump End
* Bump from back
* Bump from front
* Bump from left
* Bump from right

### Editing Player Camera Controls&#x20;

Terra Studio allows creators to edit the following camera control parameters during game play and define how users experience their game visually. You can change this by  selecting the Camera`Root` element under the `TopDownPlayer` element in Layers.

* **Camera Arc X Rot**: A numerical field through which you can define the camera's tilt, allowing for vertical adjustments. Players can aim upwards or downwards, enhancing interactions with objects or enemies located above or below.
* **Spherical Camera Positioning**:
  * **Camera Arc X**: Manages the camera's horizontal positioning, facilitating left-right movements around a focal point.
  * **Camera Arc Y**: Governs the camera's vertical placement for up-down movements, enabling varied angles and perspectives on the game environment.
* **Field of View (FoV) / Size**: A numerical field through which you can specify the visible game world area. A narrow FoV brings the world closer, ideal for precision tasks like sniping, while a wide FoV expands the view for exploratory gameplay, although excessive width can lead to edge distortion.
* **Camera Distance**: A numerical field through which you can adjusting the camera's proximity to focus points or characters, influencing the player's depth perception and detail awareness. Closer settings heighten immersion, whereas greater distances offer expansive views of the surroundings.
* **Camera Type**: Terra Studio supports both **perspective** and **orthographic** cameras, with each type significantly affecting how players perceive and navigate the game world.



