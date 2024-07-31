# T# Haptics & Extensions

## StudioHaptics

This class provides static methods to play different haptic feedback patterns. It uses the Lofelt Nice Vibrations library to trigger haptic feedback on supported devices.

#### Method: **PlayHapticSelection**

Plays the haptic feedback for selection.

```csharp
StudioHaptics.PlayHapticSelection();
```

Method: **PlayHapticSuccess**

Plays the haptic feedback for success.

```csharp
StudioHaptics.PlayHapticSuccess();
```

Method: **PlayHapticWarning**

Plays the haptic feedback for warning.

```csharp
StudioHaptics.PlayHapticWarning();
```

Method: **PlayHapticFailure**

Plays the haptic feedback for failure.

```csharp
StudioHaptics.PlayHapticFailure();
```

Method: **PlayHapticLightImpact**

Plays the haptic feedback for light impact.

```csharp
StudioHaptics.PlayHapticLightImpact();
```

Method: **PlayHapticMediumImpact**

Plays the haptic feedback for medium impact.

```csharp
StudioHaptics.PlayHapticMediumImpact();
```

Method: **PlayHapticHeavyImpact**

Plays the haptic feedback for heavy impact.

```csharp
StudioHaptics.PlayHapticHeavyImpact();
```

Method: **PlayHapticRigidImpact**

Plays the haptic feedback for rigid impact.

```csharp
StudioHaptics.PlayHapticRigidImpact();
```

Method: **PlayHapticSoftImpact**

Plays the haptic feedback for soft impact.

```csharp
StudioHaptics.PlayHapticSoftImpact();
```



## StudioExtensions

This class provides static methods for various utility functions within the Terra Studio environment.

#### Methods: **SetCurrentScore**

Sets the current score for a specified group.

```csharp
StudioExtensions.SetCurrentScore("group1", 100);
```

Methods: **GetCurrentScore**

Gets the current score for a specified group.

```csharp
int score = StudioExtensions.GetCurrentScore("group1");
```

Methods: **DestroyObject**

Destroys the specified GameObject. (Deprecated: Use `StudioBehaviour.Destroy()` instead)

```csharp
StudioExtensions.DestroyObject(gameObject);
```

Methods: **LoadScene**

Loads the specified scene by name.

```csharp
StudioExtensions.LoadScene("SceneName");
```

Methods: **GetAllScenes**

Returns a list of all scenes.

```csharp
TerraList allScenes = StudioExtensions.GetAllScenes();
```

Methods: **GetCurrentScene**

Returns the name of the current scene.

```csharp
string currentScene = StudioExtensions.GetCurrentScene();
```

Methods: **GetColorFromHex**

Converts a hex string to a Color.

```csharp
Color color = StudioExtensions.GetColorFromHex("#FFFFFF");
```

Methods: **FindDeepChild**

Finds a child transform by name, searching recursively.

```csharp
Transform child = StudioExtensions.FindDeepChild(parentTransform, "ChildName");
```

#### Example Usage:

```csharp
csharpCopy codeusing Terra.Studio.Exposed;

// Set the current score for a group
StudioExtensions.SetCurrentScore("group1", 100);

// Get the current score for a group
int score = StudioExtensions.GetCurrentScore("group1");

// Destroy a GameObject (deprecated)
StudioExtensions.DestroyObject(gameObject);

// Load a scene by name
StudioExtensions.LoadScene("SceneName");

// Get all scenes
TerraList allScenes = StudioExtensions.GetAllScenes();

// Get the current scene name
string currentScene = StudioExtensions.GetCurrentScene();

// Convert a hex string to a Color
Color color = StudioExtensions.GetColorFromHex("#FFFFFF");

// Find a child transform by name
Transform child = StudioExtensions.FindDeepChild(parentTransform, "ChildName");
```
