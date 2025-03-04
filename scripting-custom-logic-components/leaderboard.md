# Leaderboard

This guide will show you how to implement a leaderboard system in your Terra  game using the Studio API. We'll use code examples from an actual shooter game implementation to demonstrate practical applications.

### Understanding the Basics

The Terra platform provides built-in leaderboard functionality through the `StudioLeaderboard` class. This allows you to track player performance metrics and display rankings without building your own backend system.

### Step-by-Step Implementation Guide

#### 1. Determine Your Ranking Metrics

Before implementing code, decide what player actions or achievements you want to track:

```csharp
// In our shooter example, enemy kills are the primary metric
// This could be score, time, collectibles, or any other measurable achievement
```

#### 2. Set Up Data Tracking

Create methods to update your leaderboard metrics when relevant events occur:

```csharp
// Example from a shooter game. Assume that the base class is Leaderboard
public static void SetKillCount()
{
    // Increment the kill counter
    float kills = StudioPrefs.GetFloat("Kills") + 1;
    
    // Update the leaderboard with the new value
    StudioLeaderboard.Set("KillCount", kills);
    
    // Store the value locally for persistence between sessions
    StudioPrefs.SetFloat("Kills", kills);
}
```

This method does three important things:

* Retrieves the current value from local storage
* Updates the leaderboard using `StudioLeaderboard.Set()`
* Saves the updated value locally for future reference

#### 3. Reading Leaderboard Values

Create methods to retrieve current leaderboard values:

```csharp
public static float GetKillCount()
{
    float kills = 0;
    // TryGet returns the current value from the leaderboard
    StudioLeaderboard.TryGet("KillCount", out kills);
    return kills;
}
```

#### 4. Add UI Access to the Leaderboard

Implement a method to display the leaderboard interface:

```csharp
public void ShowLeaderBoard()
{
    // Optional: Play sound or haptic feedback
    StudioHaptics.PlayHapticMediumImpact();
    
    // Show the leaderboard UI with a callback for when it's closed
    StudioLeaderboard.ShowLeaderboard(LeaderBoardClosed);
}

// Callback handler for when the leaderboard is closed
public void LeaderBoardClosed()
{
    // Handle post-leaderboard actions here
    // Example: Resume game, update UI, etc.
}
```

#### 5. Create UI Button to Access Leaderboard

Add a button to your game's UI that calls the `ShowLeaderBoard()` method:

```csharp
private void Start()
{
    // Find and set up the leaderboard button
    m_Leaderboard = GetGameObjectVariable("Leaderboard").GetComponent(typeof(Button)) as Button;
    
    // Add click listener that calls the ShowLeaderBoard method
    m_Leaderboard.onClick.AddListener(ShowLeaderBoard);
}
```

#### 6. Update the Leaderboard During Gameplay

Call your tracking methods when relevant gameplay events occur:

```csharp
// Example from GameManager.cs
public void IncrementEnemyCount()
{
    // Update the leaderboard with the new kill count
    Leaderboard.SetKillCount();
    
    // Rest of the enemy elimination logic...
    m_CurrentKills++;
    // ...
}
```

#### 7. Check Leaderboard Data for Game Logic (Optional)

You can use leaderboard data to trigger game events:

```csharp
// Example: Special message on first kill
float kills = 0;
StudioLeaderboard.TryGet("KillCount", out kills);
if (kills == 1)
{
    // Player got their first kill, trigger special message
    if (Level == 1)
    {
        Broadcast("M0");
    }
}
```

### Working Example: Integrating a Leaderboard Button

Here's a complete example from the `Main_Menu_UI` class showing a full implementation:

```csharp
// Class member variable
Button m_Leaderboard;

private void Start()
{
    // Find and initialize the leaderboard button
    m_Leaderboard = GetGameObjectVariable("Leaderboard").GetComponent(typeof(Button)) as Button;
    m_Leaderboard.onClick.AddListener(ShowLeaderBoard);
    
    // Other initialization code...
}

public void ShowLeaderBoard()
{
    // Optional: Trigger sound or broadcast event
    Broadcast("Button");
    StudioHaptics.PlayHapticMediumImpact();

    // Show the leaderboard with callback
    StudioLeaderboard.ShowLeaderboard(LeaderBoardClosed);
}

public void LeaderBoardClosed()
{
    // This method is called when the leaderboard is closed
    // You can add game-resuming logic here if needed
}
```

## API Reference

The key methods available in the `StudioLeaderboard` class are:

1. <mark style="color:green;">`StudioLeaderboard.Set(string`</mark><mark style="color:green;">` `</mark>_<mark style="color:green;">`key`</mark>_<mark style="color:green;">`, float`</mark><mark style="color:green;">` `</mark>_<mark style="color:green;">`value`</mark>_<mark style="color:green;">`)`</mark>
   * Updates a leaderboard entry
   * `key`: The metric name (e.g., "KillCount")
   * `value`: The numeric value to set
2. <mark style="color:green;">`StudioLeaderboard.TryGet(string`</mark><mark style="color:green;">` `</mark>_<mark style="color:green;">`key`</mark>_<mark style="color:green;">`, out float`</mark><mark style="color:green;">` `</mark>_<mark style="color:green;">`value`</mark>_<mark style="color:green;">`)`</mark>
   * Retrieves the current value for a leaderboard metric
   * Returns `true` if successful, `false` otherwise
   * `key`: The metric name to retrieve
   * `value`: Output parameter that will contain the retrieved value
3. <mark style="color:green;">`StudioLeaderboard.ShowLeaderboard(Action`</mark><mark style="color:green;">` `</mark>_<mark style="color:green;">`callback`</mark>_<mark style="color:green;">`)`</mark>
   * Displays the leaderboard UI
   * `callback`: Method to call when the leaderboard is closed

## Best Practices

1. **Choose meaningful metrics** that reflect player skill or achievement
2. **Update the leaderboard immediately** after relevant events
3. **Store values locally** with `StudioPrefs` for persistence
4. **Provide clear UI access** to the leaderboard
