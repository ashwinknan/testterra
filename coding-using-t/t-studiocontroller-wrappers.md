# T# StudioController Wrappers

The StudioController class represents a controller for the player in the game. It provides various functionalities to interact with and manipulate the player character's properties and behaviors.

#### Enum: **PlayerLocEnum**

An enumeration of player locations used for referencing specific parts of the player model.

```csharp
public enum PlayerLocEnum
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

#### Constructor: **StudioController(IPlayerData backingController)**

Creates an instance of the StudioController class.

```csharp
StudioController controller = new StudioController(backingController);
```

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
bbool isMoving = controller.IsMoving();
```

#### Property: **GetPlayerPosition**

Gets the player's current position.

```csharp
Vector3 playerPosition = controller.GetPlayerPosition();
```

#### Property: **SetPlayerPosition**

Sets the player's position with optional smooth movement and camera transition.

```csharp
controller.SetPlayerPosition(new Vector3(0, 0, 0), smoothMove: true, smoothCamera: true);
```

#### Property: **GetPlayerForward**

Gets the forward direction of the player.

```csharp
Vector3 forwardDirection = controller.GetPlayerForward();
```

#### Property: **SetPlayerRotation**

Sets the player's rotation.

<pre class="language-csharp"><code class="lang-csharp"><strong>controller.SetPlayerRotation(Quaternion.identity);
</strong></code></pre>

#### Property: **GetOverHeadLocator**

Gets the transform of the overhead locator.

```csharp
Transform overHeadLocator = controller.GetOverHeadLocator();
```

#### Property: **GetControllerCamera**

Gets the camera associated with the player controller.

```csharp
Camera controllerCamera = controller.GetControllerCamera();
```

#### Property: **ResetCameraCurrentPosition**

Resets the camera to its current position.

```csharp
controller.ResetCameraCurrentPosition();
```

#### Property: **GetLocator**

Finds and returns a transform based on a given locator name.

```csharp
Transform locator = controller.GetLocator("locatorName");
```

#### Property: **GetPlayerData**

Returns the underlying player data associated with this controller.

```csharp
IPlayerData playerData = controller.GetPlayerData();
```

#### Property: **GetLocatorEnumBased**

Gets the transform of a location based on the PlayerLocEnum.

```csharp
Transform locatorEnumBased = controller.GetLocatorEnumBased(PlayerLocEnum.LeftLegWingLoc);
```

#### Operators:

**Equals**

Compares this instance with another StudioController.

```csharp
bool isEqual = controller.Equals(otherController);
```

**== Operator**

Checks if two StudioController instances are equal.

```csharp
bool areEqual = controller1 == controller2;
```

**!= Operator**

Checks if two StudioController instances are not equal.

```csharp
bool areNotEqual = controller1 != controller2;
```

#### Method: **GetHashCode**

Returns the hash code for this instance.

```csharp
int hashCode = controller.GetHashCode();
```
