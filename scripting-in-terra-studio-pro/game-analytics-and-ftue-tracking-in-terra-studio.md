# 📊 Game Analytics & FTUE Tracking in Terra Studio

Understanding how players interact with your game is essential to improving design, retention, and progression. Terra Studio supports in-game analytics out of the box via built-in methods integrated with Mixpanel. You don’t need to do any setup — just call the APIs as needed, and your data will automatically be sent to Mixpanel as structured events.

This guide helps you track game events (like combat stats, level progress) and FTUE (First-Time User Experience) milestones using Terra’s analytics system.

***

## 🎮 Using PlayerPrefs with Analytics

Terra Studio fully supports Unity's `PlayerPrefs` system for persistent local storage — and this becomes especially powerful when combined with analytics tracking.

In your analytics implementation, **`PlayerPrefs` acts as the local cache for all analytics strings** before they’re sent to Mixpanel via Terra’s `SetGameAnalyticsPrefs()` methods.

This ensures:

* Your data is saved **even if the game is closed unexpectedly**
* You can build up longer strings across sessions
* You always retain a fallback before transmitting events

### **✅ What You Can Store**

You can store any stringified version of game data using:

```csharp
csharpCopyEditPlayerPrefs.SetString("Key", value);
PlayerPrefs.GetString("Key");
PlayerPrefs.Save(); // Optional, but ensures immediate persistence
```

Terra Studio internally uses `PlayerPrefs` to store:

* Game value strings for progression, combat, sessions, FTUE, and more
* FTUE milestone arrays (in JSON format)
* Any transient data that you want to log incrementally over time

### **🧠 Why PlayerPrefs Matters in Analytics**

When you call:

```csharp
csharpCopyEditTerraScene.SetGameAnalyticsPrefs(...);
```

It pulls data from your locally maintained strings — most of which are stored and updated using `PlayerPrefs`. Without `PlayerPrefs`, you’d lose tracking progress on app restarts or session reloads.

***

### ✍️ Quick Example

Here’s how you’d log a gameplay event and ensure it's retained:

```csharp
csharpCopyEditPlayerPrefs.SetString("LevelProgressionData", levelProgressionData);
PlayerPrefs.Save(); // Ensures it's saved before calling analytics
TerraScene.SetGameAnalyticsPrefs(...);
```

***

By integrating `PlayerPrefs` with your analytics logic, you make sure your event data is always:

* Persisted across sessions
* Trimmed properly to meet limits
* Sent when ready

Use it as your **local data log** and rely on Terra Studio’s analytics API to **push it live** when the time is right.

## 🎯 How Game Analytics Work in Terra Studio

Terra Studio provides **12 game values** to log analytics data. You have access to two built-in methods:

* `TerraScene.SetGameAnalyticsPrefs()`
* `TerraScene.SetGameAnalyticsPrefs_2()`

Each accepts **6 values** (strings, up to **256 characters each**), allowing you to track up to **12 types of game data** simultaneously.

{% hint style="info" %}
&#x20;The **12th game value** is **reserved exclusively for FTUE tracking.**
{% endhint %}

You can think of these values as containers — use them to store data like level completions, deaths, power-up usage, etc.

***

### 🧭 Step-by-Step Implementation

#### ✅ Step 1: Decide What to Track

Here are examples of what you might want to track:

| Game Value | What to Track                        |
| ---------- | ------------------------------------ |
| 1          | Level progression                    |
| 2          | Combat statistics                    |
| 3          | Resource collection                  |
| 4          | Power-up or item usage               |
| 5          | Session info                         |
| 6          | Player customization                 |
| 7–11       | Economy, multiplayer stats, UI, etc. |
| 12         | **FTUE tracking (fixed)**            |

***

#### 🧩 Step 2: Design a Compact Format

Each value is limited to 256 characters — use compact formats with delimiters. Examples:

* **Level Completion:** `levelNumber_completionTime_exitType`
* **Combat Stats:** `levelNumber_enemyType_killCount`

Multiple entries can be chained using `||`:

```
perlCopyEdit1_45.3_exit||2_30.1_death
```

***

#### 💾 Step 3: Store Analytics Variables in Code

```csharp
public static class GameAnalytics
{
    private static string levelProgressionData;
    private static string combatStatisticsData;
    private static string resourceCollectionData;
    private static string featureUsageData;
    private static string sessionData;
    private static string customizationData;

    private static string purchaseData;
    private static string socialInteractionData;
    private static string errorData;
    private static string performanceData;
    private static string advertisingData;
    private static string ftueData; // Always for FTUE
}
```

***

#### 🧠 Step 4: Initialize Variables on Startup

```csharp
public static void Initialize()
{
    levelProgressionData = PlayerPrefs.GetString("LevelProgressionData", "");
    combatStatisticsData = PlayerPrefs.GetString("CombatStatisticsData", "");
    // ...continue for all
    ftueData = PlayerPrefs.GetString("FTUEData", "");
}
```

***

#### 🛠️ Step 5: Record Game Events

Here's how to record level completion data:

```csharp
public static void RecordLevelCompletion(int levelNumber, float completionTime, string exitType)
{
    string newEntry = $"{levelNumber}_{completionTime}_{exitType}";
    if (levelProgressionData.Length > 0) newEntry = "||" + newEntry;

    if (levelProgressionData.Length + newEntry.Length > 256)
    {
        int trimIndex = levelProgressionData.IndexOf("||") + 2;
        while (levelProgressionData.Length - trimIndex + newEntry.Length > 256)
        {
            int nextDelimiter = levelProgressionData.IndexOf("||", trimIndex);
            if (nextDelimiter == -1)
            {
                levelProgressionData = newEntry.Substring(2);
                SaveAndSendLevelProgressionData();
                return;
            }
            trimIndex = nextDelimiter + 2;
        }
        levelProgressionData = levelProgressionData.Substring(trimIndex) + newEntry;
    }
    else
    {
        levelProgressionData += newEntry;
    }

    SaveAndSendLevelProgressionData();
}
```

```csharp
private static void SaveAndSendLevelProgressionData()
{
    PlayerPrefs.SetString("LevelProgressionData", levelProgressionData);
    SendFirstSetOfGameValues();
}
```

***

#### 📡 Step 6: Send Data to Mixpanel

```csharp
public static void SendFirstSetOfGameValues()
{
    TerraScene.SetGameAnalyticsPrefs(
        levelProgressionData,
        combatStatisticsData,
        resourceCollectionData,
        featureUsageData,
        sessionData,
        customizationData
    );
}

public static void SendSecondSetOfGameValues()
{
    TerraScene.SetGameAnalyticsPrefs_2(
        purchaseData,
        socialInteractionData,
        errorData,
        performanceData,
        advertisingData,
        ftueData
    );
}

public static void SendAllAnalyticsData()
{
    SendFirstSetOfGameValues();
    SendSecondSetOfGameValues();
}
```

***

### 🧪 Example: Combat Stats

```csharp
public static void RecordEnemyKills(int levelNumber, string enemyType, int killCount)
{
    string newEntry = $"{levelNumber}_{enemyType}_{killCount}";
    if (combatStatisticsData.Length > 0) newEntry = "||" + newEntry;

    if (combatStatisticsData.Length + newEntry.Length > 256)
    {
        int trimIndex = combatStatisticsData.IndexOf("||") + 2;
        while (combatStatisticsData.Length - trimIndex + newEntry.Length > 256)
        {
            int nextDelimiter = combatStatisticsData.IndexOf("||", trimIndex);
            if (nextDelimiter == -1)
            {
                combatStatisticsData = newEntry.Substring(2);
                SaveAndSendCombatStatisticsData();
                return;
            }
            trimIndex = nextDelimiter + 2;
        }

        combatStatisticsData = combatStatisticsData.Substring(trimIndex) + newEntry;
    }
    else
    {
        combatStatisticsData += newEntry;
    }

    SaveAndSendCombatStatisticsData();
}

private static void SaveAndSendCombatStatisticsData()
{
    PlayerPrefs.SetString("CombatStatisticsData", combatStatisticsData);
    SendFirstSetOfGameValues();
}
```

***

## 🚀 FTUE (First-Time User Experience) Tracking

FTUE tracks key player milestones during onboarding (e.g., first level completed, first weapon upgrade).

#### 💡 How It Works

* Store FTUE milestones in an integer array
* 1 = completed, 0 = not completed
* Stored in `game_value12` (last value in `SetGameAnalyticsPrefs_2`)

#### 🧠 Initialize FTUE Data

```csharp
public int[] ftueData;

private void InitializeFtueData()
{
    int totalFtueData = 20;
    ftueData = new int[totalFtueData];

    if (PlayerPrefs.HasKey("fTUEData")) {
        ftueData = JsonConvert.DeserializeObject<int[]>(PlayerPrefs.GetString("fTUEData"));
        // Resize if version changed
        int currentLength = ftueData.Length;
        if (currentLength != totalFtueData) {
            int[] newFtueData = new int[totalFtueData];
            for (int i = 0; i < Math.Min(currentLength, totalFtueData); i++) {
                newFtueData[i] = ftueData[i];
            }
            ftueData = newFtueData;
        }
    }
}
```

#### 📨 Log FTUE Data

```csharp
public void LogFtueAnalytics()
{
    string ftueString = JsonConvert.SerializeObject(ftueData);
    PlayerPrefs.SetString("fTUEData", ftueString);

    string analyticsFormat = ftueString.TrimStart('[').TrimEnd(']');
    TerraScene.SetGameAnalyticsPrefs_2(
        PlayerPrefs.GetString("value6"),
        PlayerPrefs.GetString("value7"),
        PlayerPrefs.GetString("value8"),
        PlayerPrefs.GetString("value9"),
        "",
        analyticsFormat
    );
}
```

#### ⚙️ Optional Helper

```csharp
public void SetFtueTrue(int index)
{
    if (index >= 0 && index < ftueData.Length) {
        ftueData[index] = 1;
        LogFtueAnalytics();
    }
}
```

***

### 🧪 FTUE Tracking Examples

```csharp
// Level 1 completion
if (currentLevelIndex == 1 && isLevelCompleted) {
    LevelManager._Instance.ftueData[6] = 1;
    LevelManager._Instance.LogFtueAnalytics();
}

// First coin
if (currentCoin == 1 && !coin1st) {
    LevelManager._Instance.SetFtueTrue(4);
    coin1st = true;
}

// First weapon upgrade
if (weaponLevel == 2 && GameplayScreen._Instance.uiLevelIndex == 2) {
    LevelManager._Instance.ftueData[10] = 1;
    LevelManager._Instance.LogFtueAnalytics();
}
```

***

### 📌 Best Practices

* Use clear constants for FTUE milestone indices
* Avoid tracking unrelated data in FTUE
* Always call `LogFtueAnalytics()` after setting data
* Handle FTUE versioning with array resizing
* Keep event strings short and meaningful (within 256 chars)
