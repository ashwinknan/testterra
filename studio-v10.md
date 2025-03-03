# Studio v10

## <mark style="color:yellow;">`v0.10.03`</mark>

Release Date: 23 Oct 2024, 3:38 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* **Procedural Image Support:** Added support for procedural images in UI version 4.
* **UI Importer Update:** Implemented a null check to prevent issues with UIImporter
* **Antistrippers Added:** Added support for 4 games - War of India, Sniper Hitman, and OP Bike Rider
* **New TPV Controller:** Added a new TPV controller option in the controller dropdown

<mark style="color:red;">`Known issues`</mark>&#x20;

* TPV Controller might show some issues

### <mark style="color:yellow;">`v0.10.03 Patch release 1`</mark>&#x20;

Release Date: 23 Oct 2024, 4:33  pm&#x20;

<mark style="color:green;">`Change log`</mark>

* **Resolved GameObject Reference Issues:** Fixed issues causing unnecessary GameObject references.
* **Improved Logging:** Removed redundant logs to enhance performance.
* **Enhanced Null Error Handling:** Added safe checks to prevent null errors that disrupted the Inspector.

<mark style="color:red;">`Known issues`</mark>

* TPV Controller might show some issues

### <mark style="color:yellow;">`v0.10.03 Patch release 2`</mark>&#x20;

Release Date: 23 Oct 2024, 8:05  pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Attaching scripts to player and gameobjects inside player solved.
* TPV Controller issues fixed



## <mark style="color:yellow;">`v0.10.04`</mark>

Release Date: 28 Oct 2024, 4:15 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Fullscreen pan option added via T#
* Analytics functions for the Funnel Step added in StudioAnalytics class
* Changed all client-related logs to Toasts.
* StudioUser.GetAvatarImage changed.
* Added StudioUser.GetUserAvatarCinematicImage for the full body image of the 3D avatar
* Added all antistrippers for Wheel Collider&#x20;



### <mark style="color:yellow;">`v0.10.04 Patch release 1`</mark>&#x20;

Release Date: 29 Oct 2024, 7:12  pm&#x20;

<mark style="color:green;">`Change log`</mark>

New Animations added  - _load\_failure , load\_success, magazine\_failure, magazine\_success, fire\_pose_

## <mark style="color:yellow;">`v0.10.05`</mark>

Release Date: 5 Nov 2024, 7:12 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Added Camera Offset in Camera Properties.
* Added T# Wrapper for adjusting Camera Offset via code.
* Added T# wrappers to change jump height.
* Object Animation bug fixed where it played \[0] index animation on spawning
* StudioController is now broken down into 2 subclasses - StudioCamera and StudioPlayerMovement. This will break a lot of games that were accessing this directly from StudioController.GetMyController().FuncName(); Now they need to use StudioController.GetMyController().PlayerCamera.FuncName() instead.
* Added a lot of wrappers inside StudioCamera and StudioPlayerMovement.

<mark style="color:red;">`Known issues`</mark>&#x20;

* Inspector Window malfunctioning because of Collider's BasicDropdown fields
* Textures/Colors going missing

### <mark style="color:yellow;">`v0.10.05 Patch release 1`</mark>&#x20;

Release Date: 11 Nov 2024, 3:27 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Added Explosion and Explosion2 shader.
* Fixed the Vector3NullabeType Error.

<mark style="color:red;">`Known issues`</mark>&#x20;

* Inspector Window malfunctioning because of Collider's BasicDropdown fields
* Textures/Colors going missing



## <mark style="color:yellow;">`v0.10.06`</mark>

Release Date: 14 Nov 2024, 2:02 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* New wrappers for the AB testing added in StudioUser
  * SetABTest \[Debug function to test A or B]
  * GetCurrentABTest
  * CurrentUserXP
  * TotalXPRequired
  * PlayerLevel
  * OnItemConsumed
  * GetRewardedItems
  * ShowRewardNotification
* Added nullchecks for the WorldCanvas bugs
* Antistripper for Physics.bounceThreshold added.

<mark style="color:red;">`Known issues`</mark>&#x20;

* Inspector Window malfunctioning because of Collider's BasicDropdown fields
* Textures/Colors going missing

### <mark style="color:yellow;">`v0.10.06 Patch Release 1`</mark>

Release Date: 18 Nov 2024, 10:37 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Fixed old controllers.
* Added Aim\_Pistol and Aim\_Rifle animations.
* Added 3 shaders
* Fixed a core issue with UIV4/Object Reference.

<mark style="color:red;">`Known Issues`</mark>

* Inspector Window malfunctioning because of Collider's BasicDropdown fields
* Textures/Colors going missing.
* Pan jumping.

## <mark style="color:yellow;">`v0.10.07`</mark>

Release Date: 20 Nov 2024, 10:45 am&#x20;

<mark style="color:green;">`Change log`</mark>

* Pan jumping issue's potential fix
* Client merges
* VFXes now download in the background for Companion App and Client App

<mark style="color:red;">`Known issues`</mark>

* Inspector Window malfunctioning because of Collider's BasicDropdown fields.
* Textures/Colors going missing.

### <mark style="color:yellow;">`v0.10.07 Patch Release 1`</mark>

Release Date: 21 Nov 2024, 2:58 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* UI instantiation fixes
* Script name vs folder fixes

<mark style="color:red;">`Known issues`</mark>

* &#x20;Inspector Window malfunctioning because of Collider's BasicDropdown fields.
* Textures/Colors going missing.

### <mark style="color:yellow;">`v0.10.07 Patch Release 2`</mark>

Release Date: 21 Nov 2024, 4:29 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* UI instantiation fixes
* Script name vs folder fixes

<mark style="color:red;">`Known issues`</mark>

* &#x20;Inspector Window malfunctioning because of Collider's BasicDropdown fields.
* Textures/Colors going missing.

## <mark style="color:yellow;">`v0.10.07`</mark>

Release Date: 22 Nov 2024, 7:02 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* Linear fog is added to antistripping.
* Particle download delay code reverted.
* Added new functions that can help developers change the "look at" of the camera. They are all added inside the PlayerCamera
  * RotateTowardsPosition
  * RotateTowardsDirection
  * GetFacingDirection
  * GetAimingDirection
  * GetStrafeDirection
  * GetUpDirection





