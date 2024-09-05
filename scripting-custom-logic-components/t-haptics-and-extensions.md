# T# Haptics & Extensions

### **StudioHaptics**

This class provides static methods to play different haptic feedback patterns. It uses the Lofelt Nice Vibrations library to trigger haptic feedback on supported devices.

#### Properties and Methods in StudioHaptics

<table data-header-hidden><thead><tr><th width="209"></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td>Method</td><td><code>PlayHapticSelection</code></td><td>Plays the haptic feedback for selection.</td></tr><tr><td>Method</td><td><code>PlayHapticSuccess</code></td><td>Plays the haptic feedback for success.</td></tr><tr><td>Method</td><td><code>PlayHapticWarning</code></td><td>Plays the haptic feedback for warning.</td></tr><tr><td>Method</td><td><code>PlayHapticFailure</code></td><td>Plays the haptic feedback for failure.</td></tr><tr><td>Method</td><td><code>PlayHapticLightImpact</code></td><td>Plays the haptic feedback for light impact.</td></tr><tr><td>Method</td><td><code>PlayHapticMediumImpact</code></td><td>Plays the haptic feedback for medium impact.</td></tr><tr><td>Method</td><td><code>PlayHapticHeavyImpact</code></td><td>Plays the haptic feedback for heavy impact.</td></tr><tr><td>Method</td><td><code>PlayHapticRigidImpact</code></td><td>Plays the haptic feedback for rigid impact.</td></tr><tr><td>Method</td><td><code>PlayHapticSoftImpact</code></td><td>Plays the haptic feedback for soft impact.</td></tr></tbody></table>

#### Usage Example

```csharp
public class HapticFeedbackExample : StudioBehavior
{
    void TriggerHapticFeedback()
    {
        // Play haptic feedback for selection
        StudioHaptics.PlayHapticSelection();

        // Play haptic feedback for success
        StudioHaptics.PlayHapticSuccess();

        // Play haptic feedback for warning
        StudioHaptics.PlayHapticWarning();

        // Play haptic feedback for failure
        StudioHaptics.PlayHapticFailure();

        // Play haptic feedback for light impact
        StudioHaptics.PlayHapticLightImpact();

        // Play haptic feedback for medium impact
        StudioHaptics.PlayHapticMediumImpact();

        // Play haptic feedback for heavy impact
        StudioHaptics.PlayHapticHeavyImpact();

        // Play haptic feedback for rigid impact
        StudioHaptics.PlayHapticRigidImpact();

        // Play haptic feedback for soft impact
        StudioHaptics.PlayHapticSoftImpact();
    }
}
```

***

### **StudioExtensions**

This class provides static methods for various utility functions within the Terra Studio environment.

#### Properties and Methods in StudioExtensions

| **Type** | **Name**          | **Description**                                                                           |
| -------- | ----------------- | ----------------------------------------------------------------------------------------- |
| Method   | `SetCurrentScore` | Sets the current score for a specified group.                                             |
| Method   | `GetCurrentScore` | Gets the current score for a specified group.                                             |
| Method   | `DestroyObject`   | Destroys the specified GameObject. _(Deprecated: Use `StudioBehavior.Destroy()` instead)_ |
| Method   | `LoadScene`       | Loads the specified scene by name.                                                        |
| Method   | `GetAllScenes`    | Returns a list of all scenes.                                                             |
| Method   | `GetCurrentScene` | Returns the name of the current scene.                                                    |
| Method   | `GetColorFromHex` | Converts a hex string to a Color.                                                         |
| Method   | `FindDeepChild`   | Finds a child transform by name, searching recursively.                                   |

#### Usage Example

```csharp

public class UtilityFunctionsExample : StudioBehavior
{
    void ExecuteUtilityFunctions()
    {
        // Set the current score for a group
        StudioExtensions.SetCurrentScore("group1", 100);

        // Get the current score for a group
        int score = StudioExtensions.GetCurrentScore("group1");

        // Destroy a GameObject (deprecated)
        StudioExtensions.DestroyObject(gameObject);

        // Load a scene by name
        StudioExtensions.LoadScene("SceneName");

        // Get all scenes. Remember to use TerraList and not List, since List is not supported
        TerraList allScenes = StudioExtensions.GetAllScenes();

        // Get the current scene name
        string currentScene = StudioExtensions.GetCurrentScene();

        // Convert a hex string to a Color
        Color color = StudioExtensions.GetColorFromHex("#FFFFFF");

        // Find a child transform by name
        Transform child = StudioExtensions.FindDeepChild(parentTransform, "ChildName");
    }
}
```

***
