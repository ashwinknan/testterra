---
description: >-
  List of the properties, events and methods wrappers available for each class
  in Terra Studio Pro
---

# 📘 Terra Studio Runtime Classes

## 🗺️ TerraScene Class

The `TerraScene` class provides **scene management utilities** that let you load, unload, and interact with game scenes and related assets. It also includes game-ready event hooks for initializing gameplay and UI.

### **✅ Methods in TerraScene**

* `TerraScene.IsSceneDownloaded(string sceneName)`\
  Returns `true` if the specified scene has been downloaded.
* `TerraScene.Load(string sceneName)`\
  Loads the specified scene.
* `TerraScene.MoveGameObjectToScene(GameObject obj, Scene scene)`\
  Moves a given GameObject into a specified scene.
* `TerraScene.ShowLeaderboard()`\
  Displays the leaderboard UI.
* `TerraScene.SetScore(int score)`\
  Sets the current player's score.

### **📡 Events in TerraScene**

* `TerraScene.OnSceneLoaded`\
  Invoked when a scene has finished loading. Callback signature: `(Scene scene)`
* `TerraScene.OnGameReady`\
  Invoked when the main game scene is fully ready.
* `TerraScene.OnTextureReady`\
  Invoked when all textures in the scene are ready for rendering.

### **🧪 Usage Example - TerraScene**

```csharp
public class SceneManager : TerraBehaviour
{
    private void Start()
    {
        TerraScene.OnSceneLoaded += HandleSceneLoaded;
        TerraScene.OnGameReady += HandleGameReady;
        TerraScene.OnTextureReady += HandleTexturesReady;

        if (TerraScene.IsSceneDownloaded("Level1"))
        {
            TerraScene.Load("Level1");
        }
    }

    private void HandleSceneLoaded(Scene scene)
    {
        GameObject player = GameObject.Find("Player");
        TerraScene.MoveGameObjectToScene(player, scene);
    }

    private void HandleGameReady()
    {
        TerraScene.ShowLeaderboard();
        TerraScene.SetScore(1000);
    }

    private void HandleTexturesReady()
    {
        Debug.Log("All textures are ready!");
    }

    private void OnDestroy()
    {
        TerraScene.OnSceneLoaded -= HandleSceneLoaded;
        TerraScene.OnGameReady -= HandleGameReady;
        TerraScene.OnTextureReady -= HandleTexturesReady;
    }
}
```

***

## 🛠️ TerraHelper Class

The `TerraHelper` class provides **utility functions** that assist with common gameplay, device, and feedback operations.

### **✅  Methods in TerraHelper**

* `TerraHelper.GetCurrentDateTime()`\
  Returns the current UTC time as a `DateTime` object.
* `TerraHelper.FindDeepChild(Transform parent, string childName)`\
  Recursively searches for a deeply nested child by name.
* `TerraHelper.GetDeviceQuality()`\
  Returns a `DeviceQuality` enum indicating device capability (e.g., `Low`, `Medium`, `High`).
* `TerraHelper.TriggerHapticPresets(HapticPreset preset)`\
  Triggers predefined haptic feedback patterns.

### **🧪 Usage Example - TerraHelper**

```csharp
public class GameUtilities : TerraBehaviour
{
    private void Start()
    {
        DateTime currentTime = TerraHelper.GetCurrentDateTime();
        Debug.Log("Current UTC Time: " + currentTime.ToString());

        Transform playerModel = TerraHelper.FindDeepChild(transform, "PlayerModel");
        if (playerModel != null)
        {
            Debug.Log("Found player model!");
        }

        DeviceQuality quality = TerraHelper.GetDeviceQuality();
        if (quality == DeviceQuality.High)
        {
            EnableHighQualityEffects();
        }

        TerraHelper.TriggerHapticPresets(HapticPreset.ItemCollected);
    }

    private void OnObjective_Complete()
    {
        TerraHelper.TriggerHapticPresets(HapticPreset.ObjectiveComplete);
    }

    private void EnableHighQualityEffects()
    {
        // Add logic to enable high-quality settings
    }
}
```



## 🧍 TerraCharacter Class

The `TerraCharacter` class provides access to the **local player’s character and profile data**, such as their username, selected avatar icon, and gender. This is especially useful for personalizing the in-game experience or populating UI elements with player-specific information.

### **✅ Methods in TerraCharacter**

* `TerraCharacter.GetMyPlayerName()`\
  Returns the player’s **username** as a `string`.
* `TerraCharacter.GetMyPlayerIcon()`\
  Returns the player’s **avatar icon** as a `Sprite`.
* `TerraCharacter.GetMyAvatarGender()`\
  Returns the player’s **selected gender** as a `string`.\
  &#xNAN;_(e.g., `"Male"`, `"Female"`, depending on the profile setup)_

### **🧪 Usage Example - TerraCharacter**

```csharp
public class PlayerProfileDisplay : TerraBehaviour
{
    public UnityEngine.UI.Text playerNameText;
    public UnityEngine.UI.Image playerIconImage;

    private void Start()
    {
        string playerName = TerraCharacter.GetMyPlayerName();
        Sprite playerIcon = TerraCharacter.GetMyPlayerIcon();
        string gender = TerraCharacter.GetMyAvatarGender();

        Debug.Log("Player Name: " + playerName);
        Debug.Log("Gender: " + gender);

        if (playerNameText != null)
            playerNameText.text = playerName;

        if (playerIconImage != null && playerIcon != null)
            playerIconImage.sprite = playerIcon;
    }
}
```





