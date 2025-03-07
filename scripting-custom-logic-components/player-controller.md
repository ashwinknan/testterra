# T# StudioController Wrappers

### **StudioController**

The `StudioController` class in the `Terra.Studio.Exposed.Layers` namespace serves as a central controller for player-related functionalities, including camera handling, player movement, and animations. Below is a comprehensive guide to its properties, methods, and usage:

#### Properties and Methods

<table data-full-width="true"><thead><tr><th width="130">Type</th><th width="208">Name</th><th width="202">DataType</th><th>Description</th></tr></thead><tbody><tr><td><strong>Method</strong></td><td><code>GetMyController()</code></td><td><code>StudioController</code></td><td>This method resolves the current player's data and returns an existing or new instance of <code>StudioController</code> for that player.</td></tr><tr><td><strong>Method</strong></td><td><code>CheckIfController()</code></td><td><code>StudioController</code></td><td>Checks if a <code>StudioController</code> exists for a specified <code>GameObject</code> and returns it. If not, a new controller is created.</td></tr><tr><td><strong>Property</strong></td><td><code>Equals()</code></td><td><code>bool</code></td><td>Compares two <code>StudioController</code> instances and returns <code>true</code> if they are the same, <code>false</code> otherwise.</td></tr><tr><td><strong>Property</strong></td><td><code>operator ==</code></td><td><code>bool</code></td><td>Overloaded equality operator for comparing two <code>StudioController</code> instances.</td></tr><tr><td><strong>Property</strong></td><td><code>operator !=</code></td><td><code>bool</code></td><td>Overloaded inequality operator for comparing two <code>StudioController</code> instances.</td></tr><tr><td><strong>Method</strong></td><td><code>GetLocator()</code></td><td><code>Transform</code></td><td>Retrieves the <code>Transform</code> of a specific locator in the player’s hierarchy by name.</td></tr><tr><td><strong>Method</strong></td><td><code>GetLocatorEnumBased()</code></td><td><code>Transform</code></td><td>Retrieves the <code>Transform</code> of a locator based on the provided <code>PlayerLocEnum</code> value.</td></tr><tr><td><strong>Enum</strong></td><td><code>PlayerLocEnum</code></td><td></td><td>Enumeration for player locator types such as arms, legs, eyewear, etc.</td></tr><tr><td>Method</td><td><code>EnablePan()</code></td><td></td><td>Enables the pan functionality and triggers the pan toggling event as enabled.</td></tr><tr><td>Method</td><td><code>DisablePan()</code></td><td></td><td>Disables the pan functionality and triggers the pan toggling event as disabled.</td></tr><tr><td>Method</td><td><code>ToggleFullScreenPan(bool a_bEnableFullScreenPan)</code></td><td></td><td>Enables pan and toggles it to full-screen mode if <code>a_bEnableFullScreenPan</code> is <code>true</code>. If <code>false</code>, it disables the full-screen pan.</td></tr></tbody></table>



### StudioController.GetMyController().StudioCamera

The `StudioCamera` sub-class manages the camera's properties and behavior in the studio environment. It interacts with the `IPlayerCamera` interface to provide functionalities for controlling the camera's pan limits, speed, offset, field of view (FOV), and projection type (orthographic or perspective). This class offers various methods to adjust the camera settings in real-time, helping provide a customisable and dynamic viewing experience in the studio

#### Properties and Methods

<table data-header-hidden data-full-width="true"><thead><tr><th>Type</th><th>Name</th><th>DataType</th><th>Description</th></tr></thead><tbody><tr><td>Property</td><td>playerCamera</td><td></td><td>A reference to the <code>IPlayerCamera</code> interface that provides the underlying camera manipulation methods. This is injected through the constructor.</td></tr><tr><td>Method</td><td>ChangePanUpperVerticalLimit</td><td></td><td>Changes the upper vertical pan limit for the camera. Accepts a value between 0 and 90 degrees.</td></tr><tr><td>Method</td><td>ChangePanLowerVerticalLimit</td><td></td><td>Changes the lower vertical pan limit for the camera. Accepts a value between 0 and 360 degrees.</td></tr><tr><td>Method</td><td>ToggleClampOfHorizontalPan</td><td></td><td>Toggles whether the horizontal pan is limited. Accepts a boolean value to either enable or disable the clamp.</td></tr><tr><td>Method</td><td>ChangePanLowerHorizontalLimit</td><td></td><td>Changes the lower horizontal pan limit for the camera. Accepts a value between 0 and 360 degrees.</td></tr><tr><td>Method</td><td>ChangePanUpperHorizontalLimit</td><td></td><td>Changes the upper horizontal pan limit for the camera. Accepts a value between 0 and 360 degrees.</td></tr><tr><td>Method</td><td>ChangePanSpeed</td><td></td><td>Changes the pan sensitivity, adjusting how quickly the camera responds to pan input.</td></tr><tr><td>Method</td><td>ChangeCameraOffset</td><td></td><td>Changes the camera's offset from the target (e.g., player or scene). Takes a <code>Vector3</code> for the new offset.</td></tr><tr><td>Method</td><td>ChangeCameraFOVOrSize</td><td></td><td>Changes the field of view (FOV) for a perspective camera or the orthographic size for an orthographic camera. Accepts a <code>float</code> value.</td></tr><tr><td>Method</td><td>SetOrthographicCamera</td><td></td><td>Switches between orthographic and perspective views. Accepts a boolean value to specify whether the camera should be orthographic.</td></tr><tr><td>Method</td><td>IsCameraOrthographic</td><td>bool</td><td>Returns a boolean value indicating whether the camera is currently using an orthographic projection.</td></tr><tr><td>Method</td><td>GetPlayerCameraFOV</td><td>float</td><td>Returns the current field of view (FOV) of the camera in perspective mode.</td></tr><tr><td>Method</td><td>GetWorldToViewPortPoint</td><td>Vector3</td><td>Converts a world-space 3D point to viewport space.</td></tr><tr><td>Method</td><td>GetWorldToScreenPoint</td><td>Vector3</td><td>Converts a world-space 3D point to screen space, giving its screen position.</td></tr><tr><td>Method</td><td>ResetCameraCurrentPosition</td><td>void</td><td>Resets the camera's position to its default state.</td></tr></tbody></table>





### StudioController.GetMyController().StudioAnimation

The `StudioPlayerAnimation` sub-class is responsible for controlling the animation of a player character in the studio environment. It interacts with the `IPlayerAnimation` interface to play, reset, and control animations. The class encapsulates animation-related functionalities and provides a convenient interface for other components to trigger player animations.

#### Properties and Methods

<table data-header-hidden data-full-width="true"><thead><tr><th>Type</th><th>Name</th><th>Data Type</th><th>Description</th></tr></thead><tbody><tr><td>Property</td><td><code>playerAnimation</code></td><td>IPlayerAnimation</td><td>A reference to the <code>IPlayerAnimation</code> interface that handles the actual animation logic. This is injected through the constructor.</td></tr><tr><td>Method</td><td><code>PlayAnimation()</code></td><td>void</td><td>Plays an animation for the player character. It takes a <strong>string</strong> (<code>animation name</code>) and a callback (<code>Action&#x3C;bool></code>) which is called when the animation is complete.</td></tr><tr><td>Method</td><td><code>ResetAnimation()</code></td><td>void</td><td>Resets the current animation, stopping it and returning the player to a default state.</td></tr></tbody></table>

The following animations can be edited by choosing from a list of pre-existing animations:

* Idle
* Forward Running
* Back Walking
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

### StudioController.GetMyController().StudioPlayerMovement

The `StudioPlayerMovement` class handles player movement-related functionalities such as setting movement speed, jump height, joystick input, magnet range for collectibles, and toggling player movement and rotation. It interacts with two interfaces: `IPlayerInfo` for player movement mechanics and `IPlayerTransform` for player positioning and transformations (e.g., rotation, respawn point).

#### Properties and Methods

<table data-header-hidden data-full-width="true"><thead><tr><th>Type</th><th>Name</th><th>Data Type</th><th>Description</th></tr></thead><tbody><tr><td>Method</td><td><code>SetMaxMovementSpeed</code></td><td>void</td><td>Sets the maximum movement speed of the player.</td></tr><tr><td>Method</td><td><code>GetMaxMovementSpeed()</code></td><td>float</td><td>Returns the maximum movement speed of the player.</td></tr><tr><td>Method</td><td><code>GetMagnetRange()</code></td><td>float</td><td>Returns the current magnet range for collectible behaviour.</td></tr><tr><td>Method</td><td><code>SetMagnetRange()</code></td><td>void</td><td>Sets the magnet range for collectible behaviour.</td></tr><tr><td>Method</td><td><code>GetMagnetStrength()</code></td><td>float</td><td>Returns the current magnet strength for collectible behavior.</td></tr><tr><td>Method</td><td><code>SetJumpHeight()</code></td><td>void</td><td>Sets the player's jump height.</td></tr><tr><td>Method</td><td><code>GetJumpHeight()</code></td><td>float</td><td>Returns the player's jump height.</td></tr><tr><td>Method</td><td><code>GetHorizontalJoystick()</code></td><td>float</td><td>Returns the value of the joystick's horizontal axis.</td></tr><tr><td>Method</td><td><code>GetVerticalJoystick()</code></td><td>float</td><td>Returns the value of the joystick's vertical axis.</td></tr><tr><td>Method</td><td><code>IsJumpPressed()</code></td><td>bool</td><td>Checks if the jump button has been pressed by the player.</td></tr><tr><td>Method</td><td><code>AllowPlayerMovement()</code></td><td>void</td><td>Toggles whether player movement is enabled or disabled.</td></tr><tr><td>Method</td><td><code>TogglePlayerRotation()</code></td><td>void</td><td>Toggles whether the player's rotation is enabled or disabled.</td></tr><tr><td>Method</td><td><code>ToggleVisibilityOfJoystick()</code></td><td>void</td><td>Toggles the visibility of the movement joystick.</td></tr><tr><td>Method</td><td><code>GetPlayerRespawnPoint()</code></td><td>Vector3</td><td>Retrieves the player's respawn point.</td></tr><tr><td>Method</td><td><code>SetPlayerRespawnPoint()</code></td><td>void</td><td>Sets the player's respawn point to the given position.</td></tr><tr><td>Method</td><td><code>IsMoving()</code></td><td>bool</td><td>Checks if the player is currently moving.</td></tr><tr><td>Method</td><td><code>GetPlayerPosition()</code></td><td>Vector3</td><td>Retrieves the player's current position.</td></tr><tr><td>Method</td><td><code>SetPlayerPosition()</code></td><td>void</td><td>Sets the player's position with optional smoothing for movement and camera.</td></tr><tr><td>Method</td><td><code>GetPlayerForward()</code></td><td>Vector3</td><td>Retrieves the direction the player is facing (forward vector).</td></tr><tr><td>Method</td><td><code>SetPlayerRotation()</code></td><td>void</td><td>Sets the player's rotation to the specified quaternion.</td></tr></tbody></table>

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
