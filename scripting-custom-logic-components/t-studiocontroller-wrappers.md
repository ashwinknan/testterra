# T# StudioController Wrappers

### **StudioController**

The `StudioController` class represents a controller for the player in the game. It provides various functionalities to interact with and manipulate the player character's properties and behaviors.

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

#### Available Locators for `PlayerLocEnum`

```csharp
PlayerLocEnum
{
    LeftLegWingLoc,
    LeftLegGreavesLoc,
    RightLegWingLoc,
    RightLegGreavesLoc,
    LeftGlovesLoc,
    LeftLowerArmLoc,
    LeftShoulderLoc,
    LeftShoulderArmourLoc,
    HaloLoc,
    EyewearLoc,
    RightEarWearLoc,
    HeadWearLoc,
    MaskLoc,
    LeftEarWearLoc,
    CamLoc,
    ShootIKLoc,
    RightPalmLoc,
    RightGlovesLoc,
    RightLowerArmLoc,
    RightShoulderLoc,
    RightShoulderArmourLoc,
    WeaponLoc,
    BackLoc,
    NeckLoc,
    PetLoc,
    LegendaryPetLoc,
    ShoulderPetLoc,
    BaseLoc
}
```
