# T# StudioController Wrappers

The StudioController class represents a controller for the player in the game. It provides various functionalities to interact with and manipulate the player character's properties and behaviors.

#### Method: **GetMyController**

Retrieves the current player's StudioController.

```csharp
StudioController myController = StudioController.GetMyController();
```

#### Method: **CheckIfController**

Checks if a given GameObject has an associated StudioController.

```csharp
StudioController controller = StudioController.CheckIfController(gameObject);
```

#### Property: **IsMoving**

Checks if the player is moving.

```csharp
bbool isMoving = StudioController.GetMyController().IsMoving();
```

#### Property: **GetPlayerPosition**

Gets the player's current position.

```csharp
Vector3 playerPosition = StudioController.GetMyController().GetPlayerPosition();
```

#### Property: **SetPlayerPosition**

Sets the player's position with optional smooth movement and camera transition.

```csharp
StudioController.GetMyController().SetPlayerPosition(new Vector3(0, 0, 0), smoothMove: true, smoothCamera: true);
```

#### Property: **GetPlayerForward**

Gets the forward direction of the player.

```csharp
Vector3 forwardDirection = StudioController.GetMyController().GetPlayerForward();
```

#### Property: **SetPlayerRotation**

Sets the player's rotation.

<pre class="language-csharp"><code class="lang-csharp"><strong>StudioController.GetMyController().SetPlayerRotation(Quaternion.identity);
</strong></code></pre>

#### Property: **GetOverHeadLocator**

Gets the transform of the overhead locator.

```csharp
Transform overHeadLocator = StudioController.GetMyController().GetOverHeadLocator();
```

#### Property: **GetControllerCamera**

Gets the camera associated with the player controller.

```csharp
Camera controllerCamera = StudioController.GetMyController().GetControllerCamera();
```

#### Property: **ResetCameraCurrentPosition**

Resets the camera to its current position.

```csharp
controller.ResetCameraCurrentPosition();
```

#### Property: **GetLocator**

Finds and returns a transform based on a given locator name.

```csharp
Transform locator = StudioController.GetMyController().GetLocator("locatorName");
```

#### Property: **GetPlayerData**

Returns the underlying player data associated with this controller.

```csharp
IPlayerData playerData = StudioController.GetMyController().GetPlayerData();
```

#### Property: **GetLocatorEnumBased**

Gets the transform of a location based on the PlayerLocEnum.

```csharp
Transform locatorEnumBased = StudioController.GetMyController().GetLocatorEnumBased(PlayerLocEnum.LeftLegWingLoc);
```

The avaliable locators are as follows:&#x20;

```
{
    LeftLegWingLoc,
    LeftLegGreavesLoc,
    RightLegWingLoc,
    RightLegGreavesLoc,
    LeftLGlovesLoc,
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
