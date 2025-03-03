# Studio v13

## <mark style="color:yellow;">`v0.13.01`</mark>

Release Date: 16 Jan 2025, 11:30 am&#x20;

<mark style="color:green;">`Change log`</mark>

* Spot Light and Point Light added
* Shadow Strength added in Lights
* SetActive functionalities added in Editor and Runtime.
  * Use SetActive(GameObject go, bool status) for it
* SetParent functionality added in T#
  * Use SetParent(Gameobject go, Gameobject parent); for it
* Added bundle support for Companion app.&#x20;
* New NavMesh baking functions added
  * StudioAI.Bake(BoxCollider volume)
  * StudioAI.Bake(GameObject parent)
* T# now supports Inheritance.
* Display Name support added to see who you are conflicting with. WIP.
* Mesh Compression added for Upload and Replace FBX.
* Optimized the Collider visualizations
* Fixed the black void shadow thingie
* SerializedFields in T# for UI GameObjects fixed.

### <mark style="color:yellow;">`v0.13.01 Patch Release 1`</mark>

Release Date: 20 Jan 2025, 5:03 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* SetParent and SetActive functions added in StudioBehaviour.
* GLTF copy paste bug fixed.

## <mark style="color:yellow;">`v0.13.02`</mark>

Release Date: 21 Jan 2025, 1:23 pm &#x20;

<mark style="color:green;">`Change log`</mark>

* New default scene code. `StudioExtensions.ChangeDefaultScene(SceneName)`
  * Use case - Level 1 needs to load as 1st scene in FTUE. So Mark Level 1 as the default scene. Once the user wins Level 1, use this function to set HomeScreen as the default scene. So now when the user opens the game again, Homescreen will be loaded instead of Level 1.
* Added delete button in the Companion App to delete all cache. If anything breaks because of this - Reinstall.
* Extensions for iOS vs Android vs Mac vs Windows and Quality Settings.
  * StudioExtensions.isIOSPlayer
  * StudioExtensions.isAndroidPlayer
  * StudioExtensions.isWebPlayer
  * StudioExtensions.isMacEditor
  * StudioExtensions.isWindowsEditor
  * StudioExtensions.GetDeviceQuality \[Debug for now]
* Inactive GameObject Reference bug has been fixed.

### <mark style="color:yellow;">`v0.13.02 Patch Release 1`</mark>

Release Date: 22 Jan 2025, 11:27 pm&#x20;

<mark style="color:green;">`Change log`</mark>

* CanvasScaler getting disabled fix.
* Bundle download logic fixes.
* Antistrippers for NavMeshAgent.





