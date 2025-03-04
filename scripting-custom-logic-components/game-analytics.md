# Game Analytics

## Introduction to Game Analytics

When you create a game, you want to understand how players interact with it. Game analytics is the process of collecting, storing, and analyzing data about player behavior. This guide will walk you through implementing a basic analytics system for your game, taking into account the technical constraints and best practices.

## Understanding Game Values and Technical Limitations

At the core of game analytics are <mark style="color:yellow;">`game values`</mark> - these are specific pieces of data you want to track. Before we begin implementation, you should be aware of two important technical constraints:

1. The analytics system provides two separate methods: <mark style="color:green;">`SetGameAnalyticsPrefs`</mark> and <mark style="color:green;">`SetGameAnalyticsPrefs_2`</mark>. Each can handle up to 6 game values, giving you a total of 11 possible game values. (The 12th game value is usually reserved for the FTUE data tracking)&#x20;
2. Each game value has a 256-character limit. This means you need to be efficient with how you format and structure your data.

Think of these 12 game values as containers that hold important information about different aspects of gameplay. You'll need to decide which aspects of your game to track with each container.

### Step 1: Decide What to Track

First, determine what player actions or game events you want to track. Common examples include:

* Level completions and progression
* Player deaths or failures
* Resource collection and usage
* Feature usage (weapons, power-ups, etc.)
* Session information
* Tutorial progression

Since you have up to 11 game values, you can assign different types of events to different game values. For example:

* <mark style="color:yellow;">`game_value1`</mark>: Level progression data
* <mark style="color:yellow;">`game_value2`</mark>: Combat statistics
* <mark style="color:yellow;">`game_value3`</mark>: Resource collection
* <mark style="color:yellow;">`game_value4`</mark>: Feature usage
* <mark style="color:yellow;">`game_value5`</mark>: Session information
* <mark style="color:yellow;">`game_value6`</mark>: Player customization choices
* <mark style="color:yellow;">`game_value7`</mark> through game\_value12: Additional metrics

### Step 2: Design Your Data Format

For each game value, decide on a consistent format that maximizes information while staying within the 256-character limit. Since space is limited, you'll want to use compact representations.

Let's look at some example formats:

For level completions (game\_value1):

```
levelNumber_completionTime_exitType||levelNumber_completionTime_exitType
```

For combat statistics (game\_value2):

```
levelNumber_enemyType_killCount||levelNumber_enemyType_killCount
```

The `||` delimiter allows you to store multiple events of the same type within a single game value, maximizing the use of your 256 characters.&#x20;

{% hint style="info" %}
You can also use commas, colons or underscores as delimiters.
{% endhint %}

### Step 3: Create Variables to Store Analytics Data

In your code, you'll need variables to store each type of analytics data:

```csharp
public static class GameAnalytics
{
    // First set of game values (for SetGameAnalyticsPrefs)
    private static string levelProgressionData;    // game_value1
    private static string combatStatisticsData;    // game_value2
    private static string resourceCollectionData;  // game_value3
    private static string featureUsageData;        // game_value4
    private static string sessionData;             // game_value5
    private static string customizationData;       // game_value6
    
    // Second set of game values (for SetGameAnalyticsPrefs_2)
    private static string purchaseData;            // game_value7
    private static string socialInteractionData;   // game_value8
    private static string errorData;               // game_value9
    private static string performanceData;         // game_value10
    private static string advertisingData;         // game_value11
    private static string ftueData;                // game_value12 (FTUE)
}
```

### Step 4: Initialize Your Analytics Variables

When your game starts, you'll want to load any previously saved analytics data:

```csharp
public static void Initialize()
{
    // Load first set of game values
    levelProgressionData = StudioPrefs.GetString("LevelProgressionData", "");
    combatStatisticsData = StudioPrefs.GetString("CombatStatisticsData", "");
    resourceCollectionData = StudioPrefs.GetString("ResourceCollectionData", "");
    featureUsageData = StudioPrefs.GetString("FeatureUsageData", "");
    sessionData = StudioPrefs.GetString("SessionData", "");
    customizationData = StudioPrefs.GetString("CustomizationData", "");
    
    // Load second set of game values
    purchaseData = StudioPrefs.GetString("PurchaseData", "");
    socialInteractionData = StudioPrefs.GetString("SocialInteractionData", "");
    errorData = StudioPrefs.GetString("ErrorData", "");
    performanceData = StudioPrefs.GetString("PerformanceData", "");
    advertisingData = StudioPrefs.GetString("AdvertisingData", "");
    ftueData = StudioPrefs.GetString("FTUEData", "");
}
```

### Step 5: Create Methods to Record Game Events

Now, create methods to record each type of event you want to track. These methods need to handle the 256-character limit carefully.

```csharp
public static void RecordLevelCompletion(int levelNumber, float completionTime, string exitType)
{
    // Format the data
    string newEntry = $"{levelNumber}_{completionTime}_{exitType}";
    
    // Add delimiter if needed
    if (levelProgressionData.Length > 0)
    {
        newEntry = "||" + newEntry;
    }
    
    // Check if adding this entry would exceed the 256-character limit
    if (levelProgressionData.Length + newEntry.Length > 256)
    {
        // If it would exceed, we need to trim the oldest entries
        // This keeps the most recent data while staying within the character limit
        int trimIndex = levelProgressionData.IndexOf("||") + 2;
        while (levelProgressionData.Length - trimIndex + newEntry.Length > 256)
        {
            int nextDelimiter = levelProgressionData.IndexOf("||", trimIndex);
            if (nextDelimiter == -1)
            {
                // If there are no more delimiters, we can't trim further
                // In this case, we'll just reset the data to the new entry
                levelProgressionData = newEntry.Substring(2); // Remove the delimiter
                SaveAndSendLevelProgressionData();
                return;
            }
            trimIndex = nextDelimiter + 2;
        }
        
        levelProgressionData = levelProgressionData.Substring(trimIndex) + newEntry;
    }
    else
    {
        // If it wouldn't exceed, simply add the new entry
        levelProgressionData += newEntry;
    }
    
    SaveAndSendLevelProgressionData();
}

private static void SaveAndSendLevelProgressionData()
{
    // Save the updated data
    StudioPrefs.SetString("LevelProgressionData", levelProgressionData);
    
    // Send the data to your analytics service
    SendFirstSetOfGameValues();
}
```

### Step 6: Send Analytics Data to Your Analytics Service

After recording data, you'll want to send it to your analytics service using both available methods:

```csharp
public static void SendFirstSetOfGameValues()
{
    // Send the first set of game values
    StudioAnalytics.SetGameAnalyticsPrefs(
        levelProgressionData,    // game_value1
        combatStatisticsData,    // game_value2
        resourceCollectionData,  // game_value3
        featureUsageData,        // game_value4
        sessionData,             // game_value5
        customizationData        // game_value6
    );
}

public static void SendSecondSetOfGameValues()
{
    // Send the second set of game values
    StudioAnalytics.SetGameAnalyticsPrefs_2(
        purchaseData,           // game_value7
        socialInteractionData,  // game_value8
        errorData,              // game_value9
        performanceData,        // game_value10
        advertisingData,        // game_value11
        ftueData                // game_value12
    );
}

public static void SendAllAnalyticsData()
{
    // Send both sets of game values
    SendFirstSetOfGameValues();
    SendSecondSetOfGameValues();
}
```

### Step 7: Call Your Analytics Methods When Events Happen

Finally, integrate your analytics methods into your game code:

```csharp
// In your player controller or game manager
public void OnLevelComplete()
{
    // Game logic for level completion
    float completionTime = Time.time - levelStartTime;
    ShowVictoryScreen();
    
    // Record the level completion for analytics
    GameAnalytics.RecordLevelCompletion(currentLevel, completionTime, "Victory");
}
```

## Example 1: Tracking Combat Statistics

Let's walk through a complete example of tracking combat statistics (kills, deaths, etc.) in your game.

1. **Decide on a format**: For combat statistics, we'll track the level number, enemy type, and kill count in the format: `levelNumber_enemyType_killCount`
2. **Create the storage variable**:

```csharp
private static string combatStatisticsData;
```

3. **Initialize the variable**:

```csharp
combatStatisticsData = StudioPrefs.GetString("CombatStatisticsData", "");
```

4. **Create a method to record combat statistics**:

```csharp
public static void RecordEnemyKills(int levelNumber, string enemyType, int killCount)
{
    // Format: levelNumber_enemyType_killCount
    string newEntry = $"{levelNumber}_{enemyType}_{killCount}";
    
    // Add delimiter if needed
    if (combatStatisticsData.Length > 0)
    {
        newEntry = "||" + newEntry;
    }
    
    // Check if adding this entry would exceed the 256-character limit
    if (combatStatisticsData.Length + newEntry.Length > 256)
    {
        // If it would exceed, trim the oldest entries
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
        // If it wouldn't exceed, simply add the new entry
        combatStatisticsData += newEntry;
    }
    
    SaveAndSendCombatStatisticsData();
}

private static void SaveAndSendCombatStatisticsData()
{
    // Save the updated data
    StudioPrefs.SetString("CombatStatisticsData", combatStatisticsData);
    
    // Send the data to your analytics service
    SendFirstSetOfGameValues();
}
```

5. **Call this method when an enemy is killed**:

```csharp
public void OnEnemyKilled(Enemy enemy)
{
    // Game logic for enemy killed
    killCount++;
    AddScore(enemy.pointValue);
    
    // Group kills by enemy type for analytics
    if (!enemyKillsByType.ContainsKey(enemy.type))
        enemyKillsByType[enemy.type] = 0;
    
    enemyKillsByType[enemy.type]++;
    
    // Record the kills for analytics at appropriate intervals
    // (e.g., when changing levels or when the count reaches a threshold)
    if (killCount % 10 == 0 || isLevelComplete)
    {
        foreach (var entry in enemyKillsByType)
        {
            GameAnalytics.RecordEnemyKills(currentLevel, entry.Key, entry.Value);
        }
        // Reset the counts after recording
        enemyKillsByType.Clear();
    }
}
```

## Example 2: Using Both Sets of Game Values for a Racing Game

For a racing game, you might want to track different aspects using both sets of game values:

First set (`SetGameAnalyticsPrefs`):

* <mark style="color:yellow;">`game_value1`</mark>: Race completions (level, time, position)
* <mark style="color:yellow;">`game_value2`</mark>: Car performance (car type, top speed, drift count)
* <mark style="color:yellow;">`game_value3`</mark>: Track statistics (shortcuts taken, obstacles hit)
* <mark style="color:yellow;">`game_value4`</mark>: Item usage (item type, frequency, effectiveness)
* <mark style="color:yellow;">`game_value5`</mark>: Race conditions (weather, time of day, difficulty)
* <mark style="color:yellow;">`game_value6`</mark>: Crashes and resets (location, cause, frequency)

Second set (`SetGameAnalyticsPrefs_2`):

* <mark style="color:yellow;">`game_value7`</mark>: Car customization (parts selected, colors, decals)
* <mark style="color:yellow;">`game_value8`</mark>: Multiplayer statistics (opponents, race type, results)
* <mark style="color:yellow;">`game_value9`</mark>: Economy data (coins earned, spent, balance)
* <mark style="color:yellow;">`game_value10`</mark>: UI interactions (menu navigation, options selected)
* <mark style="color:yellow;">`game_value11`</mark>: Session data (play duration, races per session)
* <mark style="color:yellow;">`game_value12`</mark>: FTUE data (tutorial completion, first race performance)

Implementation example for race completion tracking:

```csharp
public static void RecordRaceCompletion(int trackNumber, float completionTime, int position)
{
    // Format: trackNumber_completionTime_position
    string newEntry = $"{trackNumber}_{completionTime}_{position}";
    
    // Add delimiter if needed
    if (raceCompletionData.Length > 0)
    {
        newEntry = "||" + newEntry;
    }
    
    // Handle 256-character limit
    if (raceCompletionData.Length + newEntry.Length > 256)
    {
        // Trim older entries
        int trimIndex = raceCompletionData.IndexOf("||") + 2;
        while (raceCompletionData.Length - trimIndex + newEntry.Length > 256)
        {
            int nextDelimiter = raceCompletionData.IndexOf("||", trimIndex);
            if (nextDelimiter == -1)
            {
                raceCompletionData = newEntry.Substring(2);
                SaveAndSendRaceCompletionData();
                return;
            }
            trimIndex = nextDelimiter + 2;
        }
        
        raceCompletionData = raceCompletionData.Substring(trimIndex) + newEntry;
    }
    else
    {
        // If it wouldn't exceed, simply add the new entry
        raceCompletionData += newEntry;
    }
    
    SaveAndSendRaceCompletionData();
}

private static void SaveAndSendRaceCompletionData()
{
    // Save the updated data
    StudioPrefs.SetString("RaceCompletionData", raceCompletionData);
    
    // Send the data to your analytics service
    SendFirstSetOfGameValues();
}
```

## Managing the 256-Character Limit

With the 256-character limit for each game value, you need strategies to ensure you're capturing the most important data:

1. **Use Compact Representations**: Keep your format concise. Use numbers instead of strings where possible, and abbreviate longer identifiers.
2. **Prioritize Recent Data**: When approaching the character limit, remove older entries in favor of newer ones. Recent player behavior is typically more relevant than historical data.
3. **Aggregate Data**: Instead of recording every single event, consider aggregating data. For example, instead of recording each enemy kill separately, record the total kills per level.

```csharp
// Example of aggregating data
public static void RecordAggregatedCombatStats(int levelNumber, Dictionary<string, int> killsByType)
{
    // Convert the dictionary to a compact string format
    string aggregatedStats = $"{levelNumber}";
    
    foreach (var entry in killsByType)
    {
        aggregatedStats += $"_{entry.Key}:{entry.Value}";
    }
    
    // Check if adding this would exceed the limit and handle appropriately
    // ...
    
    combatStatisticsData = aggregatedStats;
    SaveAndSendCombatStatisticsData();
}
```

4. **Split Related Data**: If one category of data grows too large, consider splitting it across multiple game values. For example, you might separate player achievements into "combat achievements" and "exploration achievements".
5. **Periodic Sending**: Send analytics data at key points rather than after every event to avoid unnecessary network traffic and to aggregate data efficiently.
