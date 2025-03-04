# First-Time User Experience (FTUE) Tracking

## Overview

First-Time User Experience (FTUE) tracking helps you understand how new players interact with your game during their initial sessions. By monitoring key milestones, you can identify pain points, optimize onboarding, and improve player retention.

## Core Concept: Binary Milestone Tracking

The foundation of effective FTUE tracking is a milestone-based system that records whether players have completed specific key actions or stages:

* `1` indicates the player has completed a milestone
* `0` indicates the player has not yet completed the milestone

## Implementation Steps

### 1. Create a Central Data Structure

Use an array to store the completion status of each milestone:

```csharp
// In a central manager (e.g., LevelManager)
public int[] ftueData;

private void InitializeFtueData() {
    int totalFtueData = 20; // Total number of milestones
    ftueData = new int[totalFtueData];
    
    // Load existing data if available
    if (StudioPrefs.HasKey("fTUEData")) {
        ftueData = JsonConvert.DeserializeObject<int[]>(StudioPrefs.GetString("fTUEData"));
        
        // Handle version changes
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

### 2. Implement Persistence and Analytics Reporting

Create a method to save progress and send to analytics. Remember that the sixth and the last game\_value of <mark style="color:green;">`StudioAnalytics.SetGameAnalyticsPrefs_2`</mark> is reserved exclusively for FTUE Data

```csharp
public void LogFtueAnalytics() {
    // Convert array to JSON for storage
    string ftueString = JsonConvert.SerializeObject(ftueData);
    StudioPrefs.SetString("fTUEData", ftueString);
    
    // Format data for analytics
    string analyticsFormat = ftueString.Remove(0, 1); // Remove opening bracket
    analyticsFormat = analyticsFormat.Remove(analyticsFormat.Length - 1, 1); // Remove closing bracket
    
    // Send to analytics system
    StudioAnalytics.SetGameAnalyticsPrefs_2(
        StudioPrefs.GetString("value6"),
        StudioPrefs.GetString("value7"),
        StudioPrefs.GetString("value8"),
        StudioPrefs.GetString("value9"),
        "",
        analyticsFormat // FTUE always gets tracked in the last game value of this method
    );
}
```

### 3. Optionally Add a Convenience Method

If needed, create a helper method to simplify setting milestone flags:

```csharp
public void SetFtueTrue(int index) {
    if (index >= 0 && index < ftueData.Length) {
        ftueData[index] = 1;
        LogFtueAnalytics();
    }
}
```

### Recording FTUE Milestones

There are two main approaches to tracking FTUE milestones:

#### Option 1: Direct Array Assignment

```csharp
// When player completes their first level
if (currentLevelIndex == 1 && isLevelCompleted) {
    LevelManager._Instance.ftueData[6] = 1; // Index 6 = "Level 1 Completed"
    LevelManager._Instance.LogFtueAnalytics();
}
```

#### Option 2: Using the Helper Method

```csharp
// When player collects their first coin
if (currentCoin == 1 && !coin1st) {
    LevelManager._Instance.SetFtueTrue(4); // Index 4 = "First Coin Collected"
    coin1st = true;
}
```

## Example: Tracking First Weapon Upgrade

Here's a practical example of FTUE tracking when a player first upgrades a weapon:

```csharp
public void PurchaseWeaponUpgrade() {
    // Regular purchase logic
    if (coins >= upgradeCost) {
        coins -= upgradeCost;
        weaponLevel++;
        UpdateWeaponVisuals();
        
        // FTUE tracking: First weapon upgrade
        if (weaponLevel == 2 && GameplayScreen._Instance.uiLevelIndex == 2) {
            // Index 10 represents "Machine Gun Upgrade Done"
            LevelManager._Instance.ftueData[10] = 1;
            LevelManager._Instance.LogFtueAnalytics();
        }
        
        // Continue with other code
    }
}
```

## Best Practices

1. **Define Constants**: Use clear constants for milestone indices
2. **Track Contextually**: Only mark milestones in the correct context (e.g., collecting a coin specifically in Level 1)
3. **Log After Every Update**: Call `LogFtueAnalytics()` after every milestone to prevent data loss
4. **Handle Version Changes**: Ensure your code can handle adding new milestones between game versions
5. **Keep Analytics Separate**: Use separate analytics for quantitative metrics (time spent, attempts, etc.)
