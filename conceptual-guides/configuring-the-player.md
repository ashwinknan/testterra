# Configuring the Player

At the core of every Terra game is the "Player," the visual character that represents users in the game world. As a game developer, the model you see in the editor is a placeholder that lets you customize all of the player's actions and animations.&#x20;

However, you cannot alter the player's appearance for the user. The user has the ability to select their own custom avatar, which will follow the actions and animations you've set, but in the appearance they have chosen to play with.

## Finding and Selecting the Player

You can select the player by clicking on the player's avatar that is visible in the editor mode. If you are unable to find the player, you can follow these steps:&#x20;

* Click on <mark style="color:green;">`Layers`</mark> in the Quick Access Menu on the left&#x20;
* Locate and Click on "Player".&#x20;
* Press the F button&#x20;

You will notice that the Player has a default child element TopDownPlayer  which in turn has two more children - ModelRoot and CameraRoot.

Once you find and select the player in the editor,  the Inspector Panel on the right displays a list of customisable Player Properties.&#x20;

## Transforming Initial Player Configurations

To do this, you need to select the topmost parent  element in the Layers , named Player.&#x20;

You will notice that can do three basic transformations of the player's initial configuration- <mark style="color:red;">`Move`</mark> , <mark style="color:red;">`Rotate`</mark> and <mark style="color:red;">`Scale`</mark>. When an object is selected, the Gizmo containing 3 handles will appear around it, each representing an axis along which you can manipulate the object. Alternatively, you can also manually change the values in the Inspector panel to get the exact initial configuration of the player you want.&#x20;

## Selecting a Gameplay Controller

Gameplay Controller in the context of mobile or tablet gaming is a system that interprets the player's input on the touchscreen into actions and movements within the game.&#x20;

To change the player controller,  you need to select the topmost parent element in the Layers , named Player.&#x20;

When you select Player, you will see a dropdown on the inspector panel named Controller which shows the TopDown controller by default.&#x20;

You can also import other controller packages from the Main Toolbar on the top of the interface by going to `File` > `Import`

Controller behavior can be customized in T# using the `StudioController` class that helps you access the controller for the player in the game. It provides some functionalities to interact with and manipulate the player character's properties and behaviors, which are listed below:

#### Properties and Methods in StudioController

| **Type** | **Name**                     | **Description**                                                                 |
| -------- | ---------------------------- | ------------------------------------------------------------------------------- |
| Method   | `GetMyController`            | Retrieves the current player's `StudioController`.                              |
| Method   | `CheckIfController`          | Checks if a given GameObject has an associated `StudioController`.              |
| Property | `IsMoving`                   | Checks if the player is moving.                                                 |
| Property | `GetPlayerPosition`          | Gets the player's current position.                                             |
| Property | `SetPlayerPosition`          | Sets the player's position with optional smooth movement and camera transition. |
| Property | `GetPlayerForward`           | Gets the forward direction of the player.                                       |
| Property | `SetPlayerRotation`          | Sets the player's rotation.                                                     |
| Property | `GetOverHeadLocator`         | Gets the transform of the overhead locator.                                     |
| Property | `GetControllerCamera`        | Gets the camera associated with the player controller.                          |
| Property | `ResetCameraCurrentPosition` | Resets the camera to its current position.                                      |
| Property | `GetLocator`                 | Finds and returns a transform based on a given locator name.                    |
| Property | `GetPlayerData`              | Returns the underlying player data associated with this controller.             |
| Property | `GetLocatorEnumBased`        | Gets the transform of a location based on the `PlayerLocEnum`.                  |

#### Usage Example

```csharp

public class PlayerControllerExample : StudioBehavior
{
    void ManagePlayerController()
    {
        // Retrieve the current player's controller
        StudioController myController = StudioController.GetMyController();

        // Check if a GameObject has an associated StudioController
        StudioController controller = StudioController.CheckIfController(gameObject);

        // Check if the player is moving
        bool isMoving = myController.IsMoving();

        // Get the player's current position
        Vector3 playerPosition = myController.GetPlayerPosition();

        // Set the player's position with smooth movement and camera transition
        myController.SetPlayerPosition(new Vector3(0, 0, 0), smoothMove: true, smoothCamera: true);

        // Get the forward direction of the player
        Vector3 forwardDirection = myController.GetPlayerForward();

        // Set the player's rotation
        myController.SetPlayerRotation(Quaternion.identity);

        // Get the transform of the overhead locator
        Transform overHeadLocator = myController.GetOverHeadLocator();

        // Get the camera associated with the player controller
        Camera controllerCamera = myController.GetControllerCamera();

        // Reset the camera to its current position
        myController.ResetCameraCurrentPosition();

        // Find and return a transform based on a given locator name
        Transform locator = myController.GetLocator("locatorName");

        // Return the underlying player data associated with this controller
        IPlayerData playerData = myController.GetPlayerData();

        // Get the transform of a location based on the PlayerLocEnum
        Transform locatorEnumBased = myController.GetLocatorEnumBased(PlayerLocEnum.LeftLegWingLoc);
    }
}
```

## Editing Player Motion Properties

You can alter how players move through the game space. To edit these properties, you need to select the TopDown Player element (child of the Player element). Once you select it, you can by tweak these properties:

* **Lock to Look Sideways**: Toggle button to lock or unlock sideways view.
* **Scale**: Adjust the player's size (1 = Default).
* **Gravity**: Numerical field to set gravity strength. Higher values make jumps shorter and falls faster, affecting game difficulty.
* **Jump Height**: Set the maximum height for a player's jump. This influences gameplay difficulty and accessibility.
* **Jump Lock**: Toggle to disable jumping via a controller. Useful for creating specific challenges or controlling movement in certain areas.
* **Max Speed**: Define the player's maximum achievable speed.

## Editing Player Animation

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

## Editing Player Camera Controls&#x20;

Terra Studio allows creators to edit the following camera control parameters during game play and define how users experience their game visually. You can change this by  selecting the Camera`Root` element under the `TopDownPlayer` element in Layers.

* **Camera Arc X Rot**: A numerical field through which you can define the camera's tilt, allowing for vertical adjustments. Players can aim upwards or downwards, enhancing interactions with objects or enemies located above or below.
* **Spherical Camera Positioning**:
  * **Camera Arc X**: Manages the camera's horizontal positioning, facilitating left-right movements around a focal point.
  * **Camera Arc Y**: Governs the camera's vertical placement for up-down movements, enabling varied angles and perspectives on the game environment.
* **Field of View (FoV) / Size**: A numerical field through which you can specify the visible game world area. A narrow FoV brings the world closer, ideal for precision tasks like sniping, while a wide FoV expands the view for exploratory gameplay, although excessive width can lead to edge distortion.
* **Camera Distance**: A numerical field through which you can adjusting the camera's proximity to focus points or characters, influencing the player's depth perception and detail awareness. Closer settings heighten immersion, whereas greater distances offer expansive views of the surroundings.
* **Camera Type**: Terra Studio supports both **perspective** and **orthographic** cameras, with each type significantly affecting how players perceive and navigate the game world.



