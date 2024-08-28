---
description: >-
  List of the properties, events and methods wrappers available for each logic
  template
---

# T# Logic Template Wrappers

## Accessing Logic Template Components

Terra provides a range of logic templates that can be utilized and customized in your project.&#x20;

We first declare a variable to access the specific template you want to modify:

```csharp
//TemplateType template = (GetTemplate(typeof(TemplateType)) as TemplateType);
TemplateType template = (GetTemplate(typeof(TemplateType)) as TemplateType);
```

This variable allows you to access and modify the template's properties. We then use the variable to update the properties of the template:

```csharp
//Replace PropertyName with the property you want to change and newValue with the value you want to set.
template.PropertyName = newValue;
```

#### Specific Example

The code below illustrates how to do this using the CollectableTemplate Wrapper, where we the `Score` property of the `collectable` is set to `10`.

* ```csharp
  CollectableTemplate collect = (GetTemplate(typeof(CollectableTemplate)) as CollectableTemplate);
  collect.Score = 10; // Set the score property to 10
  ```

## List of Template Wrappers

### **AdvanceMoveTemplate**

This template manages advanced movement for GameObjects, handling speed and event management for ping-pong actions. It is designed to be integrated within a GameObject's movement logic. Below is how you can utilize the `AdvanceMoveTemplate` within a `StudioBehavior` class.&#x20;

#### Properties and Methods

| **Type**     | **Name** | **Description**                                                     |
| ------------ | -------- | ------------------------------------------------------------------- |
| **Property** | Speed    | Used for getting and setting the movement speed.                    |
| **Method**   | Bla      | Manages the Ping-Pong event. Allows subscription or unsubscription. |

#### Usage Example

```csharp
public class MovementManager : StudioBehavior
{
    void ManageMovementAndEvents()
    {
        // Accessing the wrapper
        AdvanceMoveTemplate template = (GetTemplate(typeof(AdvanceMoveTemplate)) as AdvanceMoveTemplate);

        // Managing the Ping-Pong event
        template.Bla += OnPingPongAction; // Subscribe to the event
        template.Bla -= OnPingPongAction; // Unsubscribe from the event

        // Accessing and setting the Speed property
        float speed = template.Speed; // Getting the speed
        template.Speed = 5.0f;        // Setting the speed
    }

}
```

### ChangeMagnetTemplate

This template manages the magnet range for GameObjects using the `ChangeMagnetComponent`, allowing customization of magnet range behavior within your game.&#x20;

#### Properties and Methods

| **Type**     | **Name**    | **Description**                                |
| ------------ | ----------- | ---------------------------------------------- |
| **Property** | MagnetRange | Used for getting and setting the magnet range. |

#### Usage Example

```csharp

public class MagnetManager : StudioBehavior
{
    void ManageMagnetRange()
    {
        // Accessing the wrapper
        ChangeMagnetTemplate template = (GetTemplate(typeof(ChangeMagnetTemplate)) as ChangeMagnetTemplate);

        // Accessing and setting the MagnetRange property
        float magnetRange = template.MagnetRange; // Getting the magnet range
        template.MagnetRange = 10.0f;             // Setting the magnet range
    }
}
```

### ChangeMaterialPropertyTemplate

This template provides functionality to change material properties on a GameObject. It can be accessed and utilized as follows:

#### Properties and Methods

| **Type**     | **Name**          | **Description**                                         |
| ------------ | ----------------- | ------------------------------------------------------- |
| **Property** | Channels          | Access the changed material channels array.             |
| **Property** | Length            | Get the number of channels.                             |
| **Property** | Indexer           | Get or set a channel by index.                          |
| **Event**    | OnMaterialChanged | Event triggered when material properties change.        |
| **Method**   | CheckIndex        | Ensure the index is within the valid range of channels. |
| **Method**   | GetEnumerator     | Get an enumerator for iterating through the channels.   |

#### Usage Example

```csharp
public class MaterialManager : StudioBehavior
{
    void ManageMaterialProperties()
    {
        // Accessing the wrapper
        ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);

        // Accessing and setting the Channels property
        ChangedMaterialChannel[] channels = template.Channels; // Gets the changed material channels array

        // Accessing the Length property
        int length = template.Length; // Gets the number of channels

        // Getting a Channel by Index
        ChangedMaterialChannel channel = template[0]; // Gets the first channel

        // Setting a Channel by Index
        template[0] = new ChangedMaterialChannel(); // Sets the first channel

        // Subscribing to the OnMaterialChanged event
        template.OnMaterialChanged += HandleMaterialChanged;

        // Ensure the index is within the valid range
        template.CheckIndex(0);

        // Iterating through channels
        IEnumerator enumerator = template.GetEnumerator();
        while (enumerator.MoveNext())
        {
            ChangedMaterialChannel currentChannel = (ChangedMaterialChannel)enumerator.Current;
            // Process the channel
        }
    }
}
```

### ChangePlayerSpeedTemplate

This template provides functionality to change the player speed on a GameObject. It can be accessed and utilized as follows:

#### Properties and Methods

| **Type**     | **Name**             | **Description**                                       |
| ------------ | -------------------- | ----------------------------------------------------- |
| **Property** | Modifier             | Get or set the speed modifier (increase or decrease). |
| **Property** | PlayerSpeed          | Get or set the player speed.                          |
| **Event**    | OnPlayerSpeedChanged | Event triggered when the player speed changes.        |

#### Usage Example

```csharp
public class SpeedManager : StudioBehavior
{
    void ManagePlayerSpeed()
    {
        // Accessing the wrapper
        ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);

        // Accessing and setting the Modifier property
        ChangePlayerSpeed.Modifier modifier = template.Modifier; // Gets the modifier
        template.Modifier = ChangePlayerSpeed.Modifier.Increase; // Sets the modifier

        // Accessing and setting the PlayerSpeed property
        float playerSpeed = template.PlayerSpeed; // Gets the player speed
        template.PlayerSpeed = 10.0f;              // Sets the player speed

        // Subscribing to the OnPlayerSpeedChanged event
        template.OnPlayerSpeedChanged += HandlePlayerSpeedChanged;

        // Unsubscribing from the OnPlayerSpeedChanged event
        template.OnPlayerSpeedChanged -= HandlePlayerSpeedChanged;
    }

    void HandlePlayerSpeedChanged(float newSpeed)
    {
        // Handle the player speed change
    }
}
```

### CheckpointTemplate

This template provides functionality to manage checkpoint events in the game. Access it as follows:

#### Properties and Methods

| **Type**  | **Name**            | **Description**                               |
| --------- | ------------------- | --------------------------------------------- |
| **Event** | OnCheckpointTouched | Event triggered when a checkpoint is touched. |

#### Usage Example

```csharp
public class CheckpointManager : StudioBehavior
{
    void ManageCheckpointEvents()
    {
        // Accessing the wrapper
        CheckpointTemplate template = (GetTemplate(typeof(CheckpointTemplate)) as CheckpointTemplate);

        // Subscribing to the OnCheckpointTouched event
        template.OnCheckpointTouched += MyMethod; // Subscribe MyMethod to the event

        // Unsubscribing from the OnCheckpointTouched event
        template.OnCheckpointTouched -= MyMethod; // Unsubscribe MyMethod from the event
    }

    void MyMethod()
    {
        // Handle the checkpoint touch event
    }
}
```

### CollectableTemplate

This template provides functionality to manage collectable items in the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**    | **Description**                                                  |
| ------------ | ----------- | ---------------------------------------------------------------- |
| **Property** | ScoreGroup  | Get or set the score group associated with the collectable item. |
| **Property** | Score       | Get or set the score value of the collectable item.              |
| **Event**    | OnCollected | Event triggered when the collectable item is collected.          |

#### Usage Example

```csharp
public class CollectableManager : StudioBehavior
{
    void ManageCollectableItem()
    {
        // Accessing the wrapper
        CollectableTemplate template = (GetTemplate(typeof(CollectableTemplate)) as CollectableTemplate);

        // Accessing and setting the ScoreGroup property
        string scoreGroup = template.ScoreGroup; // Getting the score group
        template.ScoreGroup = "NewScoreGroup";   // Setting the score group

        // Accessing and setting the Score property
        int score = template.Score; // Getting the score value
        template.Score = 100;       // Setting the score value

        // Subscribing to the OnCollected event
        template.OnCollected += MyMethod; // Subscribe MyMethod to the event

        // Unsubscribing from the OnCollected event
        template.OnCollected -= MyMethod; // Unsubscribe MyMethod from the event
    }

    void MyMethod()
    {
        // Handle the collectable item collection
    }
}
```

### DelayBroadcastTemplate

This template manages delayed broadcast functionality in the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name** | **Description**                              |
| ------------ | -------- | -------------------------------------------- |
| **Property** | Delay    | Get or set the delay time for the broadcast. |

#### Usage Example

```csharp
public class BroadcastManager : StudioBehavior
{
    void ManageDelayBroadcast()
    {
        // Accessing the wrapper
        DelayBroadcastTemplate template = (GetTemplate(typeof(DelayBroadcastTemplate)) as DelayBroadcastTemplate);

        // Accessing and setting the Delay property
        float delayTime = template.Delay; // Getting the delay time
        template.Delay = 2.5f;            // Setting the delay time to 2.5 seconds
    }
}
```

### DestroyOnTemplate

This template manages the behavior of objects that are destroyed after a specified delay. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**     | **Description**                                           |
| ------------ | ------------ | --------------------------------------------------------- |
| **Property** | DestroyAfter | Get or set the delay after which the object is destroyed. |

#### Usage Example

```csharp
public class DestructionManager : StudioBehavior
{
    void ManageDestructionDelay()
    {
        // Accessing the wrapper
        DestroyOnTemplate template = (GetTemplate(typeof(DestroyOnTemplate)) as DestroyOnTemplate);

        // Accessing and setting the DestroyAfter property
        float destroyAfter = template.DestroyAfter; // Getting the destruction delay
        template.DestroyAfter = 5.0f;               // Setting the destruction delay to 5 seconds
    }
}
```

### DestroyTemplate

This template manages the behavior of objects that are destroyed after a specified delay. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**     | **Description**                                           |
| ------------ | ------------ | --------------------------------------------------------- |
| **Property** | DestroyAfter | Get or set the delay after which the object is destroyed. |

#### Usage Example

```csharp
public class DestructionManager : StudioBehavior
{
    void ManageDestructionDelay()
    {
        // Accessing the wrapper
        DestroyTemplate template = (GetTemplate(typeof(DestroyTemplate)) as DestroyTemplate);

        // Accessing and setting the DestroyAfter property
        float destroyAfter = template.DestroyAfter; // Getting the destruction delay
        template.DestroyAfter = 5.0f;               // Setting the destruction delay to 5 seconds
    }
}
```

### GameProgressTemplate

This template manages game progress functionality in the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                 | **Description**                                            |
| ------------ | ------------------------ | ---------------------------------------------------------- |
| **Property** | CurrentProgress          | Get or set the current progress value.                     |
| **Property** | LerpSpeed                | Get or set the lerp speed configured for the progress bar. |
| **Property** | BroadcastOnEveryProgress | Get or set the broadcast trigger for each progress point.  |
| **Property** | BroadcastOnComplete      | Get or set the broadcast trigger for completion.           |

#### Usage Example

```csharp
csharpCopy codeusing UnityEngine;

public class ProgressManager : StudioBehavior
{
    void ManageGameProgress()
    {
        // Accessing the wrapper
        GameProgressTemplate template = (GetTemplate(typeof(GameProgressTemplate)) as GameProgressTemplate);

        // Accessing and setting the CurrentProgress property
        int currentProgress = template.CurrentProgress; // Getting the current progress

        // Accessing and setting the LerpSpeed property
        float lerpSpeed = template.LerpSpeed; // Getting the lerp speed
        template.LerpSpeed = 1.0f;            // Setting the lerp speed to 1.0

        // Accessing and setting the BroadcastOnEveryProgress property
        string broadcastOnEveryProgress = template.BroadcastOnEveryProgress; // Getting the broadcast trigger
        template.BroadcastOnEveryProgress = "progress_event";              // Setting the broadcast trigger

        // Accessing and setting the BroadcastOnComplete property
        string broadcastOnComplete = template.BroadcastOnComplete; // Getting the broadcast trigger
        template.BroadcastOnComplete = "completion_event";        // Setting the broadcast trigger
    }
}
```

### GameScoreTemplate

This template manages in-game scoring functionality. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**              | **Description**                                 |
| ------------ | --------------------- | ----------------------------------------------- |
| **Property** | CurrentScore          | Get or set the current score.                   |
| **Property** | BestScore             | Get or set the best score achieved.             |
| **Property** | IsScoreUIShown        | Check if the score UI is currently displayed.   |
| **Property** | IsBestScoreCalculated | Check if the best score calculation is enabled. |
| **Event**    | OnScoreModified       | Event triggered when the score is modified.     |

#### Usage Example

```csharp
public class ScoreManager : StudioBehavior
{
    void ManageScore()
    {
        // Accessing the wrapper
        GameScoreTemplate template = (GetTemplate(typeof(GameScoreTemplate)) as GameScoreTemplate);

        // Accessing and setting the CurrentScore property
        int currentScore = template.CurrentScore; // Getting the current score

        // Accessing and setting the BestScore property
        int bestScore = template.BestScore; // Getting the best score

        // Checking if the score UI is shown
        bool isScoreUIShown = template.IsScoreUIShown; // Checking if the score UI is currently displayed

        // Checking if the best score calculation is enabled
        bool isBestScoreCalculated = template.IsBestScoreCalculated; // Checking if best score calculation is enabled

        // Subscribing to the OnScoreModified event
        template.OnScoreModified += OnScoreModifiedHandler; // Subscribe to the score modification event

        // Unsubscribing from the OnScoreModified event
        template.OnScoreModified -= OnScoreModifiedHandler; // Unsubscribe from the score modification event
    }

    void OnScoreModifiedHandler(int modifiedScore)
    {
        // Handle score modification
    }
}
```

### GrowTemplate

This template manages the growth and scale behavior of GameObjects.

#### Properties and Methods

| **Type**     | **Name**         | **Description**                                                               |
| ------------ | ---------------- | ----------------------------------------------------------------------------- |
| **Property** | ScaleTo          | Get or set the scale to which the object grows.                               |
| **Property** | Speed            | Get or set the speed at which the object grows.                               |
| **Property** | ShouldPingPong   | Check or set whether the growth should alternate between scaling up and down. |
| **Property** | RepeatForever    | Check or set whether the growth should repeat indefinitely.                   |
| **Property** | RepeatFor        | Get or set the duration for which the growth should repeat.                   |
| **Event**    | OnRepetationOver | Event triggered when the repetition is over.                                  |
| **Event**    | OnGrowFinished   | Event triggered when the growth is finished.                                  |

#### Usage Example

```csharp
public class GrowthManager : StudioBehavior
{
    void ManageGrowth()
    {
        // Accessing the wrapper
        GrowTemplate template = (GetTemplate(typeof(GrowTemplate)) as GrowTemplate);

        // Accessing and setting the ScaleTo property
        Vector3 scaleTo = template.ScaleTo; // Getting the target scale
        template.ScaleTo = new Vector3(2f, 2f, 2f); // Setting the target scale

        // Accessing and setting the Speed property
        float speed = template.Speed; // Getting the growth speed
        template.Speed = 1.5f;        // Setting the growth speed

        // Accessing and setting the ShouldPingPong property
        bool shouldPingPong = template.ShouldPingPong; // Checking if ping pong behavior is enabled
        template.ShouldPingPong = true;                // Enabling ping pong behavior

        // Accessing and setting the RepeatForever property
        bool repeatForever = template.RepeatForever; // Checking if growth repeats indefinitely
        template.RepeatForever = true;              // Enabling repeat forever

        // Accessing and setting the RepeatFor property
        int repeatFor = template.RepeatFor; // Getting the repeat duration
        template.RepeatFor = 10;           // Setting the repeat duration to 10 seconds

        // Subscribing to the OnRepetationOver event
        template.OnRepetationOver += OnRepetationOverHandler; // Subscribe to the event

        // Unsubscribing from the OnRepetationOver event
        template.OnRepetationOver -= OnRepetationOverHandler; // Unsubscribe from the event

        // Subscribing to the OnGrowFinished event
        template.OnGrowFinished += OnGrowFinishedHandler; // Subscribe to the event

        // Unsubscribing from the OnGrowFinished event
        template.OnGrowFinished -= OnGrowFinishedHandler; // Unsubscribe from the event
    }

    void OnRepetationOverHandler()
    {
        // Handle repetition over event
    }

    void OnGrowFinishedHandler()
    {
        // Handle growth finished event
    }
}
```

### InGameTimerTemplate

This template manages in-game timer functionality. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**       | **Description**                                               |
| ------------ | -------------- | ------------------------------------------------------------- |
| **Property** | TimerType      | Get the type of timer.                                        |
| **Property** | CurrentTime    | Get the current time from the in-game timer handler.          |
| **Property** | IsUIShown      | Check if the UI associated with the timer is currently shown. |
| **Event**    | OnTimerUpdated | Event triggered when the timer is updated.                    |

#### Usage Example

```csharp
public class TimerManager : StudioBehavior
{
    void ManageTimer()
    {
        // Accessing the wrapper
        InGameTimerTemplate template = (GetTemplate(typeof(InGameTimerTemplate)) as InGameTimerTemplate);

        // Accessing the TimerType property
        TimerType timerType = template.TimerType; // Getting the type of timer

        // Accessing the CurrentTime property
        float currentTime = template.CurrentTime; // Getting the current time

        // Checking if the UI is shown
        bool isUIShown = template.IsUIShown; // Checking if the UI associated with the timer is currently shown

        // Subscribing to the OnTimerUpdated event
        template.OnTimerUpdated += OnTimerUpdatedHandler; // Subscribe to the event

        // Unsubscribing from the OnTimerUpdated event
        template.OnTimerUpdated -= OnTimerUpdatedHandler; // Unsubscribe from the event
    }

    void OnTimerUpdatedHandler(float updatedTime)
    {
        // Handle timer updated event
    }
}
```

### **JumpPadTemplate**

This template manages jump pad functionality within the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**  | **Description**                            |
| ------------ | --------- | ------------------------------------------ |
| **Property** | JumpForce | Get or set the jump force of the jump pad. |

#### Usage Example

```csharp
public class JumpPadManager : StudioBehavior
{
    void ConfigureJumpPad()
    {
        // Accessing the wrapper
        JumpPadTemplate template = (GetTemplate(typeof(JumpPadTemplate)) as JumpPadTemplate);

        // Accessing and setting the JumpForce property
        float jumpForce = template.JumpForce; // Getting the jump force
        template.JumpForce = 10.0f;           // Setting the jump force
    }
}
```

***

### **KillPlayerTemplate**

This template manages the behavior related to killing the player in the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**               | **Description**                                        |
| ------------ | ---------------------- | ------------------------------------------------------ |
| **Property** | AnimationToPlayOnDeath | Get or set the animation to play when the player dies. |
| **Property** | Delay                  | Get or set the delay before respawning the player.     |
| **Property** | RespawnType            | Get or set the respawn type (snap or lerp).            |
| **Property** | LerpTime               | Get or set the lerp time for respawn.                  |
| **Event**    | OnAnimationEnded       | Event triggered when the animation ends.               |
| **Event**    | OnRespawned            | Event triggered when the player respawns.              |

#### Usage Example

```csharp
public class PlayerManager : StudioBehavior
{
    void ConfigurePlayerBehavior()
    {
        // Accessing the wrapper
        KillPlayerTemplate template = (GetTemplate(typeof(KillPlayerTemplate)) as KillPlayerTemplate);

        // Accessing and setting the AnimationToPlayOnDeath property
        string animation = template.AnimationToPlayOnDeath; // Getting the death animation
        template.AnimationToPlayOnDeath = "death_animation"; // Setting the death animation

        // Accessing and setting the Delay property
        float delay = template.Delay; // Getting the respawn delay
        template.Delay = 3.0f;       // Setting the respawn delay

        // Accessing and setting the RespawnType property
        RespawnV2.RespawnType respawnType = template.RespawnType; // Getting the respawn type
        template.RespawnType = RespawnV2.RespawnType.Lerp;       // Setting the respawn type

        // Accessing and setting the LerpTime property
        float lerpTime = template.LerpTime; // Getting the lerp time
        template.LerpTime = 2.0f;           // Setting the lerp time

        // Subscribing to the OnAnimationEnded event
        template.OnAnimationEnded += HandleAnimationEnd; // Subscribe to the event

        // Subscribing to the OnRespawned event
        template.OnRespawned += HandlePlayerRespawn; // Subscribe to the event

        // Unsubscribing from the OnAnimationEnded event
        template.OnAnimationEnded -= HandleAnimationEnd; // Unsubscribe from the event

        // Unsubscribing from the OnRespawned event
        template.OnRespawned -= HandlePlayerRespawn; // Unsubscribe from the event
    }

    void HandleAnimationEnd()
    {
        // Handle animation end logic here
    }

    void HandlePlayerRespawn()
    {
        // Handle player respawn logic here
    }
}
```

### **LightTemplate**

This template manages the behavior related to controlling a light component in the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                  | **Description**                                         |
| ------------ | ------------------------- | ------------------------------------------------------- |
| **Property** | Color                     | Get or set the color of the light.                      |
| **Property** | Intensity                 | Get or set the intensity of the light.                  |
| **Event**    | OnLightPropertiesModified | Event triggered when the light properties are modified. |

#### Usage Example

```csharp
public class LightController : StudioBehavior
{
    void ConfigureLight()
    {
        // Accessing the wrapper
        LightTemplate template = (GetTemplate(typeof(LightTemplate)) as LightTemplate);

        // Accessing and setting the Color property
        Color color = template.Color; // Getting the light color
        template.Color = Color.red;   // Setting the light color

        // Accessing and setting the Intensity property
        float intensity = template.Intensity; // Getting the light intensity
        template.Intensity = 2.0f;           // Setting the light intensity

        // Subscribing to the OnLightPropertiesModified event
        template.OnLightPropertiesModified += HandleLightPropertiesModified;
        
        // Unsubscribing from the OnLightPropertiesModified event
        template.OnLightPropertiesModified -= HandleLightPropertiesModified;
    }

    void HandleLightPropertiesModified()
    {
        // Handle light properties modified logic here
    }
}
```

***

### **MoveBetweenPointsTemplate**

This template facilitates movement between specified points in the game, utilizing interpolation techniques for smooth transitions. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**          | **Description**                                           |
| ------------ | ----------------- | --------------------------------------------------------- |
| **Property** | Points            | Access or modify the points defining the movement path.   |
| **Property** | Speed             | Get or set the speed of movement between points.          |
| **Property** | TurnToPoints      | Enable or disable rotation towards movement points.       |
| **Property** | DelayAtPoint      | Specify a delay upon reaching each movement point.        |
| **Property** | Loop              | Enable or disable looping of the movement path.           |
| **Property** | DoCurve           | Activate or deactivate curve interpolation for movement.  |
| **Property** | LoopType          | Specify the interpolation type used for movement looping. |
| **Event**    | OnIntervalReached | Event triggered when an interval is reached.              |
| **Event**    | OnReachedEnd      | Event triggered when the movement ends.                   |
| **Event**    | OnLoopFinished    | Event triggered when the movement loop is finished.       |

#### Usage Example

```csharp
public class MovementController : StudioBehavior
{
    void ConfigureMovement()
    {
        // Accessing the wrapper
        MoveBetweenPointsTemplate template = (GetTemplate(typeof(MoveBetweenPointsTemplate)) as MoveBetweenPointsTemplate);

        // Accessing and setting the Points property
        List<Vector3> points = template.Points; // Getting the movement points
        template.Points = new List<Vector3> { /* Define new points here */ }; // Setting new movement points

        // Accessing and setting the Speed property
        float speed = template.Speed; // Getting the movement speed
        template.Speed = 5.0f;        // Setting the movement speed

        // Accessing and setting the TurnToPoints property
        bool turnToPoints = template.TurnToPoints; // Getting rotation towards points
        template.TurnToPoints = true; // Enabling rotation towards points

        // Accessing and setting the DelayAtPoint property
        float delay = template.DelayAtPoint; // Getting delay at points
        template.DelayAtPoint = 1.5f; // Setting delay at points

        // Accessing and setting the Loop property
        bool loop = template.Loop; // Getting loop status
        template.Loop = true; // Enabling loop

        // Accessing and setting the DoCurve property
        bool doCurve = template.DoCurve; // Getting curve interpolation status
        template.DoCurve = true; // Enabling curve interpolation

        // Accessing and setting the LoopType property
        InterpolateType loopType = template.LoopType; // Getting loop interpolation type
        template.LoopType = InterpolateType.Linear; // Setting loop interpolation type

        // Subscribing to events
        template.OnIntervalReached += HandleIntervalReached;
        template.OnReachedEnd += HandleMovementEnd;
        template.OnLoopFinished += HandleLoopFinished;

        // Unsubscribing from events
        template.OnIntervalReached -= HandleIntervalReached;
        template.OnReachedEnd -= HandleMovementEnd;
        template.OnLoopFinished -= HandleLoopFinished;
    }

    void HandleIntervalReached()
    {
        // Handle interval reached logic here
    }

    void HandleMovementEnd()
    {
        // Handle movement end logic here
    }

    void HandleLoopFinished()
    {
        // Handle loop finished logic here
    }
}
```



### **MoveTemplate**

This template facilitates movement functionality within the game, focusing on translating entities using specified parameters. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**  | **Description**                                |
| ------------ | --------- | ---------------------------------------------- |
| **Property** | Speed     | Get or set the speed of movement.              |
| **Property** | Loop      | Get or set whether the movement should loop.   |
| **Property** | Interval  | Get or set the pause interval during movement. |
| **Property** | Point     | Get or set the target position for movement.   |
| **Event**    | OnStopped | Event triggered when the movement is stopped.  |
| **Event**    | OnResumed | Event triggered when the movement is resumed.  |

#### Usage Example

```csharp
public class MovementController : StudioBehavior
{
    void ConfigureMovement()
    {
        // Accessing the wrapper
        MoveTemplate template = (GetTemplate(typeof(MoveTemplate)) as MoveTemplate);

        // Accessing and setting the Speed property
        float speed = template.Speed; // Getting the movement speed
        template.Speed = 5.0f;        // Setting the movement speed

        // Accessing and setting the Loop property
        bool loop = template.Loop; // Getting loop status
        template.Loop = true;     // Enabling looping movement

        // Accessing and setting the Interval property
        float interval = template.Interval; // Getting pause interval
        template.Interval = 1.5f; // Setting pause interval

        // Accessing and setting the Point property
        Vector3 point = template.Point; // Getting target position
        template.Point = new Vector3(10f, 0f, 5f); // Setting target position

        // Subscribing to events
        template.OnStopped += HandleStopped;
        template.OnResumed += HandleResumed;

        // Unsubscribing from events
        template.OnStopped -= HandleStopped;
        template.OnResumed -= HandleResumed;
    }

    void HandleStopped()
    {
        // Handle stopped logic here
    }

    void HandleResumed()
    {
        // Handle resumed logic here
    }
}
```

***

### **MoveToPlayerTemplate**

This template facilitates movement towards a player entity within the game, utilizing specified parameters. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                 | **Description**                                        |
| ------------ | ------------------------ | ------------------------------------------------------ |
| **Property** | Speed                    | Get or set the speed of movement towards the player.   |
| **Property** | Offset                   | Get or set the offset relative to the player position. |
| **Property** | CancelType               | Get or set the type of cancellation for movement.      |
| **Event**    | OnCancelled              | Event triggered when the movement is canceled.         |
| **Event**    | OnReachedDestination     | Event triggered when the destination is reached.       |
| **Event**    | OnReachedInitialPosition | Event triggered when the initial position is reached.  |

#### Usage Example

```csharp
public class PlayerMovementController : StudioBehavior
{
    void ConfigurePlayerMovement()
    {
        // Accessing the wrapper
        MoveToPlayerTemplate template = (GetTemplate(typeof(MoveToPlayerTemplate)) as MoveToPlayerTemplate);

        // Accessing and setting the Speed property
        float speed = template.Speed; // Getting movement speed towards player
        template.Speed = 7.0f;       // Setting movement speed towards player

        // Accessing and setting the Offset property
        Vector3 offset = template.Offset; // Getting movement offset
        template.Offset = new Vector3(0f, 1f, 0f); // Setting movement offset

        // Accessing and setting the CancelType property
        MoveToPlayer.CancelType cancelType = template.CancelType; // Getting cancellation type
        template.CancelType = MoveToPlayer.CancelType.Immediate; // Setting cancellation type

        // Subscribing to events
        template.OnCancelled += HandleCancelled;
        template.OnReachedDestination += HandleReachedDestination;
        template.OnReachedInitialPosition += HandleReachedInitialPosition;

        // Unsubscribing from events
        template.OnCancelled -= HandleCancelled;
        template.OnReachedDestination -= HandleReachedDestination;
        template.OnReachedInitialPosition -= HandleReachedInitialPosition;
    }

    void HandleCancelled()
    {
        // Handle cancellation logic here
    }

    void HandleReachedDestination()
    {
        // Handle logic when reaching the player destination here
    }

    void HandleReachedInitialPosition()
    {
        // Handle logic when reaching initial position here
    }
}
```

***

### **ParticleEffectTemplate**

This template manages particle effects within the game, offering flexibility in configuration and event handling. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                   | **Description**                                              |
| ------------ | -------------------------- | ------------------------------------------------------------ |
| **Property** | RepeatCount                | Get or set the number of times the particle effect repeats.  |
| **Property** | PlayForever                | Get or set whether continuous playback is enabled.           |
| **Property** | Duration                   | Get or set the duration of the particle effect.              |
| **Property** | Delay                      | Get or set the delay between repetitions of the effect.      |
| **Event**    | OnParticlePlayingCompleted | Event triggered when the particle effect playback completes. |

#### Usage Example

```csharp
public class ParticleEffectController : StudioBehavior
{
    void ConfigureParticleEffect()
    {
        // Accessing the wrapper
        ParticleEffectTemplate template = (GetTemplate(typeof(ParticleEffectTemplate)) as ParticleEffectTemplate);

        // Accessing and setting the RepeatCount property
        int repeatCount = template.RepeatCount; // Getting repeat count
        template.RepeatCount = 3; // Setting repeat count

        // Accessing and setting the PlayForever property
        bool playForever = template.PlayForever; // Getting continuous playback status
        template.PlayForever = true; // Enabling continuous playback

        // Accessing and setting the Duration property
        float duration = template.Duration; // Getting effect duration
        template.Duration = 5.0f; // Setting effect duration

        // Accessing and setting the Delay property
        int delay = template.Delay; // Getting delay value
        template.Delay = 2; // Setting delay between repetitions

        // Subscribing to events
        template.OnParticlePlayingCompleted += HandleParticlePlayingCompleted;

        // Unsubscribing from events
        template.OnParticlePlayingCompleted -= HandleParticlePlayingCompleted;
    }

    void HandleParticlePlayingCompleted()
    {
        // Handle logic when particle effect playback completes here
    }
}
```

### **PlayAnimationTemplate**

This template facilitates the management and execution of animations within the game environment, offering seamless integration and customization options. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**              | **Description**                                   |
| ------------ | --------------------- | ------------------------------------------------- |
| **Property** | CurrentAnimation      | Retrieve the currently playing animation.         |
| **Property** | DefaultAnimation      | Set the default animation for the component.      |
| **Property** | AvailableAnimations   | Access the list of available animations.          |
| **Method**   | PlayAnimationOverride | Play a specified animation with optional looping. |
| **Method**   | StopAnimationOverride | Stop the currently playing animation.             |
| **Event**    | OnAnimationCompleted  | Event triggered when an animation completes.      |

#### Usage Example

```csharp
public class AnimationController : StudioBehavior
{
    void ConfigureAnimation()
    {
        // Accessing the wrapper
        PlayAnimationTemplate template = (GetTemplate(typeof(PlayAnimationTemplate)) as PlayAnimationTemplate);

        // Accessing and setting the DefaultAnimation property
        string defaultAnimation = template.DefaultAnimation; // Getting default animation
        template.DefaultAnimation = "Idle"; // Setting default animation

        // Accessing AvailableAnimations property
        TerraList availableAnimations = template.AvailableAnimations; // Getting available animations

        // Controlling animation playback
        template.PlayAnimationOverride("Run", true); // Playing animation with looping
        template.StopAnimationOverride(); // Stopping the current animation

        // Subscribing to events
        template.OnAnimationCompleted += HandleAnimationCompleted;

        // Unsubscribing from events
        template.OnAnimationCompleted -= HandleAnimationCompleted;
    }

    void HandleAnimationCompleted(string animationName)
    {
        // Handle logic when animation completes here
    }
}
```

***

### **PlayerAnimationControlTemplate**

The PlayerAnimationControlTemplate class facilitates the control and management of player animations within the game environment. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                    | **Description**                              |
| ------------ | --------------------------- | -------------------------------------------- |
| **Property** | AnimationName               | Get or set the current animation name.       |
| **Property** | ResetAnimationAutomatically | Enable or disable automatic animation reset. |
| **Event**    | OnAnimationCompleted        | Event triggered when an animation completes. |

#### Usage Example

```csharp
public class PlayerAnimationController : StudioBehavior
{
    void ConfigurePlayerAnimation()
    {
        // Accessing the wrapper
        PlayerAnimationControlTemplate template = (GetTemplate(typeof(PlayerAnimationControlTemplate)) as PlayerAnimationControlTemplate);

        // Accessing and setting the AnimationName property
        string animationName = template.AnimationName; // Getting current animation name
        template.AnimationName = "Run"; // Setting animation name

        // Accessing and setting the ResetAnimationAutomatically property
        bool resetAutomatically = template.ResetAnimationAutomatically; // Getting auto-reset status
        template.ResetAnimationAutomatically = true; // Enabling automatic reset

        // Subscribing to events
        template.OnAnimationCompleted += HandleAnimationCompleted;

        // Unsubscribing from events
        template.OnAnimationCompleted -= HandleAnimationCompleted;
    }

    void HandleAnimationCompleted(bool success, string animationName)
    {
        // Handle logic when animation completes here
    }
}
```

***

### **PlayPlayersAnimationTemplate**

The PlayPlayersAnimationTemplate class is designed to manage and control player animations within your game environment. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**                    | **Description**                              |
| ------------ | --------------------------- | -------------------------------------------- |
| **Property** | AnimationName               | Get or set the current animation name.       |
| **Property** | ResetAnimationAutomatically | Enable or disable automatic animation reset. |

#### Usage Example

```csharp
public class PlayerAnimationController : StudioBehavior
{
    void ConfigurePlayerAnimation()
    {
        // Accessing the wrapper
        PlayPlayersAnimationTemplate template = (GetTemplate(typeof(PlayPlayersAnimationTemplate)) as PlayPlayersAnimationTemplate);

        // Accessing and setting the AnimationName property
        string animationName = template.AnimationName; // Getting current animation name
        template.AnimationName = "Jump"; // Setting animation name

        // Accessing and setting the ResetAnimationAutomatically property
        bool resetAutomatically = template.ResetAnimationAutomatically; // Getting auto-reset status
        template.ResetAnimationAutomatically = true; // Enabling automatic reset
    }
}
```

***

### **PushTemplate**

The PushTemplate class facilitates control over push components within your game, offering methods to manage resistance properties effectively. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**   | **Description**                                  |
| ------------ | ---------- | ------------------------------------------------ |
| **Property** | Resistance | Get or set the resistance of the push component. |

#### Usage Example

```csharp
public class PushController : StudioBehavior
{
    void ConfigurePush()
    {
        // Accessing the wrapper
        PushTemplate template = (GetTemplate(typeof(PushTemplate)) as PushTemplate);

        // Accessing and setting the Resistance property
        float resistance = template.Resistance; // Getting resistance value
        template.Resistance = 2.5f; // Setting resistance value
    }
}
```

***

### **RandomBroadcastTemplate**

This template manages random broadcasting functionality within the game, utilizing specified parameters to handle broadcast strings. Access it as follows:

#### Properties, Methods, and Indexer

| **Type**     | **Name**                  | **Description**                                                       |
| ------------ | ------------------------- | --------------------------------------------------------------------- |
| **Property** | GetAllBroadcastingStrings | Retrieve all broadcasting strings.                                    |
| **Indexer**  | \[index]                  | Access or modify a specific broadcasting string by index.             |
| **Method**   | GetEnumerator             | Iterate through all broadcasting strings.                             |
| **Method**   | CheckIndex                | Validate an index before accessing or modifying broadcasting strings. |
| **Method**   | UpdateConditionBroadcasts | Update a specific broadcasting string.                                |

#### Usage Example

```csharp
public class BroadcastController : StudioBehavior
{
    void ConfigureBroadcast()
    {
        // Accessing the wrapper
        RandomBroadcastTemplate template = (GetTemplate(typeof(RandomBroadcastTemplate)) as RandomBroadcastTemplate);

        // Accessing all broadcasting strings
        List<string> broadcastingStrings = template.GetAllBroadcastingStrings; // Retrieving all strings

        // Accessing a specific broadcasting string
        string broadcast = template[0]; // Getting broadcast at index 0
        template[0] = "New Broadcast"; // Updating broadcast at index 0

        // Enumerating through broadcasting strings
        IEnumerator enumerator = template.GetEnumerator();
        while (enumerator.MoveNext())
        {
            string broadcastItem = (string)enumerator.Current;
            // Process each broadcast here
        }

        // Validating index
        try
        {
            template.CheckIndex(1);
            // Proceed with index-valid operations
        }
        catch (ArgumentOutOfRangeException ex)
        {
            // Handle index out of range exception
        }

        // Updating a broadcasting string
        template.UpdateConditionBroadcasts(1, "Updated Broadcast");
    }
}
```

### **ResetScoreTemplate**

This template manages the resetting of scores within the game, utilizing specified parameters to handle score groups. Access it as follows:

#### Properties

| **Type**     | **Name**   | **Description**             |
| ------------ | ---------- | --------------------------- |
| **Property** | ScoreGroup | Get or set the score group. |

#### Usage Example

```csharp
public class ScoreManager : StudioBehavior
{
    void ConfigureScore()
    {
        // Accessing the wrapper
        ResetScoreTemplate template = (GetTemplate(typeof(ResetScoreTemplate)) as ResetScoreTemplate);

        // Accessing and setting the ScoreGroup property
        string scoreGroup = template.ScoreGroup; // Getting score group
        template.ScoreGroup = "NewScoreGroup"; // Updating score group
    }
}
```

***

### **RotateOscillateTemplate**

This template manages the rotation oscillation behavior within the game. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**              | **Description**                                  |
| ------------ | --------------------- | ------------------------------------------------ |
| **Property** | RotationAxis          | Get or set the rotation axis.                    |
| **Property** | Degrees               | Get or set the degrees of rotation.              |
| **Property** | Direction             | Get or set the rotation direction.               |
| **Property** | RepeatCount           | Get or set the repeat count for the rotation.    |
| **Property** | Loop                  | Check if the rotation is looping.                |
| **Property** | StopOn                | Get or set the condition to stop the rotation.   |
| **Property** | ResumeOn              | Get or set the condition to resume the rotation. |
| **Event**    | OnRepetitionCompleted | Event triggered when a repetition completes.     |
| **Event**    | OnRotationCompleted   | Event triggered when rotation completes.         |
| **Event**    | OnRotationPaused      | Event triggered when rotation is paused.         |
| **Event**    | OnRotationResumed     | Event triggered when rotation resumes.           |

#### Usage Example

```csharp
public class RotationController : StudioBehavior
{
    void ConfigureRotation()
    {
        // Accessing the wrapper
        RotateOscillateTemplate template = (GetTemplate(typeof(RotateOscillateTemplate)) as RotateOscillateTemplate);

        // Accessing and setting properties
        Axis rotationAxis = template.RotationAxis; // Getting rotation axis
        template.RotationAxis = Axis.Y; // Setting rotation axis

        int degrees = template.Degrees; // Getting degrees
        template.Degrees = 90; // Setting degrees

        Direction direction = template.Direction; // Getting direction
        template.Direction = Direction.Clockwise; // Setting direction

        int repeatCount = template.RepeatCount; // Getting repeat count
        template.RepeatCount = 5; // Setting repeat count

        bool isLooping = template.Loop; // Checking if looping
        template.StopOn = "SomeCondition"; // Setting stop condition
        template.ResumeOn = "SomeOtherCondition"; // Setting resume condition

        // Subscribing to events
        template.OnRepetitionCompleted += HandleRepetitionCompleted;
        template.OnRotationCompleted += HandleRotationCompleted;
        template.OnRotationPaused += HandleRotationPaused;
        template.OnRotationResumed += HandleRotationResumed;

        // Unsubscribing from events
        template.OnRepetitionCompleted -= HandleRepetitionCompleted;
        template.OnRotationCompleted -= HandleRotationCompleted;
        template.OnRotationPaused -= HandleRotationPaused;
        template.OnRotationResumed -= HandleRotationResumed;
    }

    void HandleRepetitionCompleted()
    {
        // Handle repetition completed logic here
    }

    void HandleRotationCompleted()
    {
        // Handle rotation completed logic here
    }

    void HandleRotationPaused()
    {
        // Handle rotation paused logic here
    }

    void HandleRotationResumed()
    {
        // Handle rotation resumed logic here
    }
}
```

***

### **RotateTemplate**

This template manages rotation behavior within the game. Access it as follows:

#### Properties

| **Type**     | **Name**     | **Description**                    |
| ------------ | ------------ | ---------------------------------- |
| **Property** | RotationAxis | Get or set the rotation axis.      |
| **Property** | Speed        | Get or set the speed of rotation.  |
| **Property** | Direction    | Get or set the rotation direction. |

#### Usage Example

```csharp
public class RotationController : StudioBehavior
{
    void ConfigureRotation()
    {
        // Accessing the wrapper
        RotateTemplate template = (GetTemplate(typeof(RotateTemplate)) as RotateTemplate);

        // Accessing and setting properties
        Axis rotationAxis = template.RotationAxis; // Getting rotation axis
        template.RotationAxis = Axis.Y; // Setting rotation axis

        float speed = template.Speed; // Getting speed
        template.Speed = 5.0f; // Setting speed

        Direction direction = template.Direction; // Getting direction
        template.Direction = Direction.Clockwise; // Setting direction
    }
}
```

***

### **SetPositionTemplate**

This template is used to set the position of an object within the game engine. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**          | **Description**                               |
| ------------ | ----------------- | --------------------------------------------- |
| **Property** | TargetPosition    | Get or set the target position of the object. |
| **Event**    | OnPositionUpdated | Event triggered when the position is updated. |

#### Usage Example

```csharp
public class PositionController : StudioBehavior
{
    void ConfigurePosition()
    {
        // Accessing the wrapper
        SetPositionTemplate positionTemplate = (GetTemplate(typeof(SetPositionTemplate)) as SetPositionTemplate);

        // Accessing and setting TargetPosition property
        Vector3 targetPosition = positionTemplate.TargetPosition; // Getting target position
        positionTemplate.TargetPosition = new Vector3(10, 20, 30); // Setting target position

        // Subscribing to events
        positionTemplate.OnPositionUpdated += HandlePositionUpdated;

        // Unsubscribing from events
        positionTemplate.OnPositionUpdated -= HandlePositionUpdated;
    }

    void HandlePositionUpdated()
    {
        // Custom logic to execute when the position is updated
        Debug.Log("Position updated");
    }
}
```

***

### **ShowUITemplate**

This template manages the display of UI elements within the game. Access it as follows:

#### Properties

| **Type**     | **Name**          | **Description**                         |
| ------------ | ----------------- | --------------------------------------- |
| **Property** | AnimationType     | Get or set the UI animation type.       |
| **Property** | ScreenPosition    | Get or set the screen position.         |
| **Property** | UIToShow          | Get or set the UI element to show.      |
| **Property** | Icon1Name         | Get or set the name of the first icon.  |
| **Property** | Icon2Name         | Get or set the name of the second icon. |
| **Property** | Text1             | Get or set the first text.              |
| **Property** | Text2             | Get or set the second text.             |
| **Property** | Text3             | Get or set the third text.              |
| **Property** | AnimationDuration | Get or set the animation duration.      |
| **Property** | UIDuration        | Get or set the UI display duration.     |

#### Usage Example

```csharp
public class UIController : StudioBehavior
{
    void ConfigureUI()
    {
        // Accessing the wrapper
        ShowUITemplate template = (GetTemplate(typeof(ShowUITemplate)) as ShowUITemplate);

        // Accessing and setting properties
        UIAnimation animationType = template.AnimationType; // Getting UI animation type
        template.AnimationType = UIAnimation.FadeIn; // Setting UI animation type

        UIPoint screenPosition = template.ScreenPosition; // Getting screen position
        template.ScreenPosition = new UIPoint(100, 200); // Setting screen position

        string uiToShow = template.UIToShow; // Getting UI element to show
        template.UIToShow = "MainMenu"; // Setting UI element to show

        string icon1Name = template.Icon1Name; // Getting first icon name
        template.Icon1Name = "Icon1"; // Setting first icon name

        string icon2Name = template.Icon2Name; // Getting second icon name
        template.Icon2Name = "Icon2"; // Setting second icon name

        string text1 = template.Text1; // Getting first text
        template.Text1 = "Welcome"; // Setting first text

        string text2 = template.Text2; // Getting second text
        template.Text2 = "Start Game"; // Setting second text

        string text3 = template.Text3; // Getting third text
        template.Text3 = "Options"; // Setting third text

        float animationDuration = template.AnimationDuration; // Getting animation duration
        template.AnimationDuration = 1.5f; // Setting animation duration

        float uiDuration = template.UIDuration; // Getting UI display duration
        template.UIDuration = 5.0f; // Setting UI display duration
    }
}
```



### **SoundFxTemplate**

This template manages sound effects within the game, allowing customization of volume, pitch, 3D audio settings, distance ranges, looping capabilities, and pause/resume events. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**    | **Description**                                  |
| ------------ | ----------- | ------------------------------------------------ |
| **Property** | Volume      | Get or set the volume.                           |
| **Property** | Pitch       | Get or set the pitch.                            |
| **Property** | Is3DAudio   | Get or set whether the sound is 3D audio.        |
| **Property** | MinDistance | Get or set the minimum distance for 3D audio.    |
| **Property** | MaxDistance | Get or set the maximum distance for 3D audio.    |
| **Property** | CanLoop     | Get or set whether the sound can loop.           |
| **Property** | PauseOn     | Get or set the event on which the sound pauses.  |
| **Property** | ResumeOn    | Get or set the event on which the sound resumes. |
| **Event**    | OnPaused    | Event triggered when the sound is paused.        |
| **Event**    | OnResumed   | Event triggered when the sound is resumed.       |

#### Usage Example

```csharp
public class SoundManager : StudioBehavior
{
    void ConfigureSound()
    {
        // Accessing the wrapper
        SoundFxTemplate template = (GetTemplate(typeof(SoundFxTemplate)) as SoundFxTemplate);

        // Accessing and setting properties
        float volume = template.Volume; // Getting volume
        template.Volume = 0.5f; // Setting volume

        float pitch = template.Pitch; // Getting pitch
        template.Pitch = 1.0f; // Setting pitch

        bool is3DAudio = template.Is3DAudio; // Checking if 3D audio
        template.Is3DAudio = true; // Enabling 3D audio

        float minDistance = template.MinDistance; // Getting minimum distance
        template.MinDistance = 1.0f; // Setting minimum distance

        float maxDistance = template.MaxDistance; // Getting maximum distance
        template.MaxDistance = 50.0f; // Setting maximum distance

        bool canLoop = template.CanLoop; // Checking if looping
        template.CanLoop = true; // Enabling looping

        string pauseOn = template.PauseOn; // Getting pause event
        template.PauseOn = "PlayerDeath"; // Setting pause event

        string resumeOn = template.ResumeOn; // Getting resume event
        template.ResumeOn = "PlayerRespawn"; // Setting resume event

        // Subscribing to events
        template.OnPaused += OnSoundPaused;
        template.OnResumed += OnSoundResumed;

        // Unsubscribing from events
        template.OnPaused -= OnSoundPaused;
        template.OnResumed -= OnSoundResumed;
    }

    void OnSoundPaused()
    {
        // Your code here
    }

    void OnSoundResumed()
    {
        // Your code here
    }
}
```

***

### **SwitchTemplate**

This template manages the switch component within the game, allowing custom actions when toggled on or off. Access it as follows:

#### Events

| **Type**  | **Name**     | **Description**                                 |
| --------- | ------------ | ----------------------------------------------- |
| **Event** | OnToggledOn  | Event triggered when the switch is toggled on.  |
| **Event** | OnToggledOff | Event triggered when the switch is toggled off. |

#### Usage Example

```csharp
public class SwitchController : StudioBehavior
{
    void ConfigureSwitch()
    {
        // Accessing the wrapper
        SwitchTemplate template = (GetTemplate(typeof(SwitchTemplate)) as SwitchTemplate);

        // Subscribing to events
        template.OnToggledOn += OnSwitchToggledOn;
        template.OnToggledOff += OnSwitchToggledOff;

        // Unsubscribing from events
        template.OnToggledOn -= OnSwitchToggledOn;
        template.OnToggledOff -= OnSwitchToggledOff;
    }

    void OnSwitchToggledOn()
    {
        // Your code here
    }

    void OnSwitchToggledOff()
    {
        // Your code here
    }
}
```

***

### **TeleportTemplate**

This template manages the teleport component within the game, allowing custom actions when teleportation occurs. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**      | **Description**                            |
| ------------ | ------------- | ------------------------------------------ |
| **Property** | TeleportPoint | Get or set the teleport destination point. |
| **Event**    | OnTeleported  | Event triggered when teleportation occurs. |

#### Usage Example

```csharp
public class TeleportController : StudioBehavior
{
    void ConfigureTeleport()
    {
        // Accessing the wrapper
        TeleportTemplate template = (GetTemplate(typeof(TeleportTemplate)) as TeleportTemplate);

        // Accessing and setting TeleportPoint property
        Vector3 currentPoint = template.TeleportPoint; // Getting teleport point
        template.TeleportPoint = new Vector3(10, 20, 30); // Setting teleport point

        // Subscribing to events
        template.OnTeleported += OnTeleport;

        // Unsubscribing from events
        template.OnTeleported -= OnTeleport;
    }

    void OnTeleport()
    {
        // Your code here
    }
}
```

***

### **TickTemplate**

This template manages the tick component within the game, providing access to conditions and events related to tick operations. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**  | **Description**                           |
| ------------ | --------- | ----------------------------------------- |
| **Indexer**  | \[index]  | Get or set values by index.               |
| **Property** | Length    | Get the number of condition broadcasts.   |
| **Property** | StartOn   | Get or set the start condition.           |
| **Property** | StopOn    | Get or set the stop condition.            |
| **Property** | ResumeOn  | Get or set the resume condition.          |
| **Event**    | OnStarted | Event triggered when the tick starts.     |
| **Event**    | OnPaused  | Event triggered when the tick is paused.  |
| **Event**    | OnResumed | Event triggered when the tick is resumed. |
| **Event**    | OnTick    | Event triggered for each tick.            |

#### Usage Example

```csharp
public class TickController : StudioBehavior
{
    void ConfigureTick()
    {
        // Accessing the wrapper
        TickTemplate template = (GetTemplate(typeof(TickTemplate)) as TickTemplate);

        // Accessing and setting properties
        int length = template.Length; // Getting length
        template.StartOn = "StartCondition"; // Setting start condition
        template.StopOn = "StopCondition"; // Setting stop condition
        template.ResumeOn = "ResumeCondition"; // Setting resume condition

        // Subscribing to events
        template.OnStarted += OnTickStarted;
        template.OnPaused += OnTickPaused;
        template.OnResumed += OnTickResumed;
        template.OnTick += OnTickAction;

        // Unsubscribing from events
        template.OnStarted -= OnTickStarted;
        template.OnPaused -= OnTickPaused;
        template.OnResumed -= OnTickResumed;
        template.OnTick -= OnTickAction;
    }

    string this[int index]
    {
        get { return template[index]; } // Getting value by index
        set { template[index] = value; } // Setting value by index
    }

    void OnTickStarted()
    {
        // Your code here
    }

    void OnTickPaused()
    {
        // Your code here
    }

    void OnTickResumed()
    {
        // Your code here
    }

    void OnTickAction()
    {
        // Your code here
    }
}
```

### **TogglePlayerMovementTemplate**

This template manages the player movement component, specifically handling stun animation and shader effects, and provides events for pause and resume actions. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**           | **Description**                                      |
| ------------ | ------------------ | ---------------------------------------------------- |
| **Property** | PlayStunAnimation  | Get or set the stun animation state.                 |
| **Property** | ChangeToStunShader | Get or set the stun shader state.                    |
| **Property** | ResumeOn           | Get or set the resume condition.                     |
| **Event**    | OnPaused           | Event triggered when the player movement is paused.  |
| **Event**    | OnResumed          | Event triggered when the player movement is resumed. |

#### Usage Example

```csharp
public class PlayerMovementController : StudioBehavior
{
    void ConfigureMovement()
    {
        // Accessing the wrapper
        TogglePlayerMovementTemplate template = (GetTemplate(typeof(TogglePlayerMovementTemplate)) as TogglePlayerMovementTemplate);

        // Accessing and setting properties
        bool isStunAnimationOn = template.PlayStunAnimation; // Getting stun animation state
        template.PlayStunAnimation = true; // Setting stun animation state

        bool isStunShaderOn = template.ChangeToStunShader; // Getting stun shader state
        template.ChangeToStunShader = true; // Setting stun shader state

        string resumeCondition = template.ResumeOn; // Getting resume condition
        template.ResumeOn = "newResumeCondition"; // Setting resume condition

        // Subscribing to events
        template.OnPaused += OnMovementPaused;
        template.OnResumed += OnMovementResumed;

        // Unsubscribing from events
        template.OnPaused -= OnMovementPaused;
        template.OnResumed -= OnMovementResumed;
    }

    void OnMovementPaused()
    {
        // Your code here
    }

    void OnMovementResumed()
    {
        // Your code here
    }
}
```

***

### **UpdateScoreTemplate**

This template manages the score component, handling score groups, modifiers, and score values. It integrates with the `ScoreHandler` to get and set scores. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**   | **Description**                                     |
| ------------ | ---------- | --------------------------------------------------- |
| **Property** | ScoreGroup | Get or set the score group.                         |
| **Property** | Modifier   | Get or set the modifier for score updates.          |
| **Property** | Score      | Get or set the score value.                         |
| **Method**   | GetScore   | Retrieve the current score from the `ScoreHandler`. |
| **Method**   | SetScore   | Set a new score using the `ScoreHandler`.           |

#### Usage Example

```csharp
public class ScoreManager : StudioBehavior
{
    void ConfigureScore()
    {
        // Accessing the wrapper
        UpdateScoreTemplate template = (GetTemplate(typeof(UpdateScoreTemplate)) as UpdateScoreTemplate);

        // Accessing and setting properties
        string scoreGroup = template.ScoreGroup; // Getting score group
        template.ScoreGroup = "newScoreGroup"; // Setting score group

        Modifier modifier = template.Modifier; // Getting modifier
        template.Modifier = Modifier.Add; // Setting modifier

        int score = template.Score; // Getting score
        template.Score = 100; // Setting score

        // Using methods
        int currentScore = template.GetScore(); // Getting current score
        template.SetScore(150); // Setting a new score
    }
}
```

***

### **UpdateTimerTemplate**

This template manages the timer component, handling modifiers, update intervals, and current time. It integrates with the `InGameTimeHandler` to get and set in-game time. Access it as follows:

#### Properties and Methods

| **Type**     | **Name**    | **Description**                                         |
| ------------ | ----------- | ------------------------------------------------------- |
| **Property** | Modifier    | Get or set the modifier for timer updates.              |
| **Property** | UpdateBy    | Get or set the update interval.                         |
| **Property** | CurrentTime | Get or set the current time.                            |
| **Method**   | GetTime     | Retrieve the current time from the `InGameTimeHandler`. |
| **Method**   | SetTime     | Set a new time using the `InGameTimeHandler`.           |

#### Usage Example

```csharp
public class TimerManager : StudioBehavior
{
    void ConfigureTimer()
    {
        // Accessing the wrapper
        UpdateTimerTemplate template = (GetTemplate(typeof(UpdateTimerTemplate)) as UpdateTimerTemplate);

        // Accessing and setting properties
        Modifier modifier = template.Modifier; // Getting modifier
        template.Modifier = Modifier.Add; // Setting modifier

        int updateBy = template.UpdateBy; // Getting update interval
        template.UpdateBy = 5; // Setting update interval

        float currentTime = template.CurrentTime; // Getting current time
        template.CurrentTime = 10.5f; // Setting current time

        // Using methods
        float time = template.GetTime(); // Getting current time
        template.SetTime(12.0f); // Setting a new time
    }
}
```
