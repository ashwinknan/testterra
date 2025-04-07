---
description: >-
  List of the properties, events and methods wrappers available for each logic
  template
---

# Terra Pro: T# Wrappers

## How to customize pre-built logic components

Terra Studio provides wrappers to access and customize pre-built logic components.&#x20;

To access the wrapper, we first declare a variable that helps retrieve the logic template component using the GetTemplate method. &#x20;

```csharp
//This line retrieves a template of type CollectableTemplate using the GetTemplate method and then casts it to the CollectableTemplate type.
TemplateName template = (GetTemplate(typeof(TemplateName)) as TemplateName);
```

This variable allows you to access and modify the template's properties. We then use the variable to update the properties of the template:

```csharp
//Replace PropertyName with the property you want to change and newValue with the value you want to set.
template.PropertyName = newValue;
```

#### Specific Example

The code below illustrates how to do this using the CollectableTemplate Wrapper, where we set the `Score` property of the `collectable` is set to `10`.

```csharp
// Example to access the Collectable template wrapper and then set the values of one of its exposed properties
CollectableTemplate collect = (GetTemplate(typeof(CollectableTemplate)) as CollectableTemplate);
collect.Score = 10; // Set the score property to 10
```

## TerraScene Class

The TerraScene class provides comprehensive scene management functionality for your game, allowing you to load, unload, and manipulate scenes and assets.

#### Methods in TerraScene

| Load Scene(string sceneName)                            | Loads a scene by name                                 |
| ------------------------------------------------------- | ----------------------------------------------------- |
| UnLoad Scene(string sceneName)                          | Unloads a scene by name                               |
| bool IsSceneDownloaded(string sceneName)                | Checks if a scene bundle has been downloaded          |
| Scene GetGameMainScene()                                | Returns the game's main scene                         |
| Scene GetCurrentLoadedSubScene()                        | Returns the currently loaded additive scene           |
| void MoveGameObjectToScene(GameObject obj, Scene scene) | Moves a GameObject from one scene to another          |
| T LoadAsset\<T>(string assetPath)                       | Loads an asset from the resource folder               |
| void ShowHomeButton(bool show)                          | Enables or disables the Terra Home Button             |
| void ShowLeaderboard()                                  | Displays the Core Leaderboard UI                      |
| LeaderboardData GetLeaderboardData()                    | Retrieves leaderboard data from Core                  |
| string\[] GetUsernamesDB()                              | Returns a collection of fake player names for testing |
| int GetTerraCoins()                                     | Gets the current Terra Coins balance                  |
| void SubtractTerraCoins(int amount)                     | Subtracts Terra Coins from balance                    |
| void SetScore(int score)                                | Sets a score in the leaderboard                       |
| void GiveTrophy(string milestoneId)                     | Updates a milestone achievement                       |
| void SetGameAnalyticsPrefs(string key, string value)    | Sets game analytics preferences                       |
| void SetGameAnalyticsPrefs\_2(string key, string value) | Sets additional game analytics preferences            |

#### Events in TerraScene

| Event                      | Event Description                                 |
| -------------------------- | ------------------------------------------------- |
| OnSceneLoaded(Scene scene) | Invoked when a scene is fully loaded              |
| OnGameReady()              | Invoked when the main scene is fully loaded       |
| OnTextureReady()           | Invoked when all game KTX textures are downloaded |



#### Usage Example for TerraScene

```csharp
public class SceneManager : TerraBehaviour
{
    private void Start()
    {
        // Subscribe to events
        TerraScene.OnSceneLoaded += HandleSceneLoaded;
        TerraScene.OnGameReady += HandleGameReady;
        TerraScene.OnTextureReady += HandleTexturesReady;
        
        // Check if a scene is downloaded
        bool isDownloaded = TerraScene.IsSceneDownloaded("Level1");
        
        if (isDownloaded)
        {
            // Load a scene
            TerraScene.Load("Level1");
        }
    }
    
    private void HandleSceneLoaded(Scene scene)
    {
        Debug.Log("Scene loaded: " + scene.name);
        
        // Move an object to the newly loaded scene
        GameObject player = GameObject.Find("Player");
        TerraScene.MoveGameObjectToScene(player, scene);
    }
    
    private void HandleGameReady()
    {
        Debug.Log("Main game scene is ready!");
        
        // Show leaderboard
        TerraScene.ShowLeaderboard();
        
        // Set a score
        TerraScene.SetScore(1000);
    }
    
    private void HandleTexturesReady()
    {
        Debug.Log("All textures are ready!");
    }
    
    private void OnDestroy()
    {
        // Unsubscribe from events
        TerraScene.OnSceneLoaded -= HandleSceneLoaded;
        TerraScene.OnGameReady -= HandleGameReady;
        TerraScene.OnTextureReady -= HandleTexturesReady;
    }
}





```

### TerraHelper Class

The TerraHelper class provides utility functions that assist with various game development tasks.

|                                                   |                                                 |
| ------------------------------------------------- | ----------------------------------------------- |
| ToggleGlobalAudioListener(bool enable)            | Enables or disables the global audio listener   |
| GetCurrentDateTime()                              | Returns the current UTC time                    |
| FindDeepChild(Transform parent, string childName) | Finds a deeply nested child by name             |
| GetCustomTag(string tag)                          | Retrieves a PS custom tag value                 |
| TriggerHapticPresets(HapticPreset preset)         | Triggers haptic feedback on supported devices   |
| GetDeviceQuality ()                               | Returns the quality level of the current device |

#### Usage Example for TerraHelper

```csharp
csharpCopypublic class GameUtilities : TerraBehaviour
{
    private void Start()
    {
        // Get current time
        DateTime currentTime = TerraHelper.GetCurrentDateTime();
        Debug.Log("Current UTC Time: " + currentTime.ToString());
        
        // Find a deeply nested child GameObject
        Transform playerModel = TerraHelper.FindDeepChild(transform, "PlayerModel");
        if (playerModel != null)
        {
            Debug.Log("Found player model!");
        }
        
        // Check device quality
        DeviceQuality quality = TerraHelper.GetDeviceQuality();
        if (quality == DeviceQuality.High)
        {
            // Enable high-quality effects
            EnableHighQualityEffects();
        }
        
        // Trigger haptic feedback when player collects an item
        TerraHelper.TriggerHapticPresets(HapticPreset.ItemCollected);
    }
    
    private void OnObjective_Complete()
    {
        // Trigger stronger haptic feedback on objective completion
        TerraHelper.TriggerHapticPresets(HapticPreset.ObjectiveComplete);
    }
    
    private void EnableHighQualityEffects()
    {
        // Your code to enable high-quality effects
    }
}
```



## TerraCharacter

The TerraCharacter class provides information about the player's character and profile.

#### Methods in TerraCharacter

| Method              | Description                             |
| ------------------- | --------------------------------------- |
| GetMyPlayerName()   | Returns the player's username           |
| GetMyPlayerIcon()   | Returns the sprite of the player's icon |
| GetMyAvatarGender() | Returns the gender selected by the user |





