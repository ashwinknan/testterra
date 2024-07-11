---
description: >-
  List of the properties, events and methods wrappers available for each
  behavior template
---

# Behavior Template Wrappers

{% hint style="info" %}
Currently, [behavior templates](../overview/building-blocks-of-a-terra-game/configuring-behaviors/) doesn't work with objects instantiated using T#. However, behaviors can be directly coded.
{% endhint %}

## AdvanceMoveTemplate

This template manages advanced movement for entities using the `TranslateComponent`, handling speed and event management for ping-pong actions. To integrate the `AdvanceMoveTemplate`, follow the usage instructions below:

```csharp
AdvanceMoveTemplate template = (GetTemplate(typeof(AdvanceMoveTemplate)) as AdvanceMoveTemplate);
```

### Property: <mark style="color:yellow;">`Speed`</mark>

Used for Getting and Setting the Movement Speed

```csharp
float speed = template.Speed; // Getting the speed
template.Speed = 5.0; // Setting the speed
```

### Event: <mark style="color:yellow;">`Bla`</mark>

Used to Managing the Ping-Pong Event. To subscribe or unsubscribe from the ping-pong event:

```csharp
template.Bla += OnPingPongAction; // Subscribe to the event
template.Bla -= OnPingPongAction; // Unsubscribe from the event

void OnPingPongAction()
{
    // Handle ping-pong action here
}
```

## ChangeMagnetTemplate

This template manages the magnet range for entities using the `ChangeMagnetComponent`, allowing customization of magnet range behavior within your game. Integrate `ChangeMagnetTemplate` as follows:

```csharp
ChangeMagnetTemplate template = (GetTemplate(typeof(ChangeMagnetTemplate)) as ChangeMagnetTemplate);
```

### Property: <mark style="color:yellow;">`MagnetRange`</mark>

To get or set the magnet range:

```csharp
float magnetRange = template.MagnetRange; // Getting the magnet range
template.MagnetRange = 10.0; // Setting the magnet range
```

## ChangeMaterialPropertyTemplate

This template provides functionality to change material properties on a game object. It can be accessed and utilized as follows:

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
```

### Property: <mark style="color:yellow;">`Channels`</mark>

Access the changed material channels array.

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
ChangedMaterialChannel[] channels = template.Channels; // Gets the changed material channels array
```

### Property: <mark style="color:yellow;">`Length`</mark>

Get the number of channels.

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
int length = template.Length; // Gets the number of channels
```

### Property: <mark style="color:yellow;">`Indexer`</mark>

**Getting a Channel by Index**

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
ChangedMaterialChannel channel = template[0]; // Gets the first channel
```

**Setting a Channel by Index**

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
template[0] = new ChangedMaterialChannel(); // Sets the first channel
```

### Event: <mark style="color:yellow;">`OnMaterialChanged`</mark>

**Subscribing to the Event**

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
template.OnMaterialChanged += HandleMaterialChanged;

void HandleMaterialChanged(int index)
{
    // Handle the material change
}
```

**Unsubscribing from the Event**

```csharp
ChangeMaterialPropertyTemplate template = (GetTemplate(typeof(ChangeMaterialPropertyTemplate)) as ChangeMaterialPropertyTemplate);
template.OnMaterialChanged -= HandleMaterialChanged;
```

### Method: <mark style="color:yellow;">`CheckIndex`</mark>

Ensure the index is within the valid range of channels.

```csharp
template.CheckIndex(index);
```

### Method: <mark style="color:yellow;">`GetEnumerator`</mark>

Get an enumerator for iterating through the channels.

```csharp
IEnumerator enumerator = template.GetEnumerator();
while (enumerator.MoveNext())
{
    ChangedMaterialChannel channel = (ChangedMaterialChannel)enumerator.Current;
    // Process the channel
}
```

## ChangePlayerSpeedTemplate

This template provides functionality to change the player speed on a game object. It can be accessed and utilized as follows:

```csharp
ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);
```

### **Property: **<mark style="color:yellow;">**`Modifier`**</mark>

Get or set the speed modifier (increase or decrease)

```csharp
ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);
ChangePlayerSpeed.Modifier modifier = template.Modifier; // Gets the modifier
template.Modifier = ChangePlayerSpeed.Modifier.Increase; // Sets the modifier
```

### **Property: **<mark style="color:yellow;">**`PlayerSpeed`**</mark>

Get or set the player speed.

```csharp
ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);
float playerSpeed = template.PlayerSpeed; // Gets the player speed
template.PlayerSpeed = 10.0f; // Sets the player speed
```

### **Event: **<mark style="color:yellow;">**`OnPlayerSpeedChanged`**</mark>

**Subscribing to the Event**

```csharp
ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);
template.OnPlayerSpeedChanged += HandlePlayerSpeedChanged;

void HandlePlayerSpeedChanged(float newSpeed)
{
    // Handle the player speed change
}
```

**Unsubscribing from the Event**

```csharp
ChangePlayerSpeedTemplate template = (GetTemplate(typeof(ChangePlayerSpeedTemplate)) as ChangePlayerSpeedTemplate);
template.OnPlayerSpeedChanged -= HandlePlayerSpeedChanged;
```

## CheckpointTemplate

This template provides functionality to manage checkpoint events in the game. You access it by&#x20;

```csharp
CheckpointTemplate template = (GetTemplate(typeof(CheckpointTemplate)) as CheckpointTemplate);
```

### Event: <mark style="color:yellow;">`OnCheckpointTouched`</mark>

#### Subscribing to the Event

To subscribe to the `OnCheckPointTouched` event:

```csharp
CheckpointTemplate template = (GetTemplate(typeof(CheckpointTemplate)) as CheckpointTemplate);
template.OnCheckPointTouched += MyMethod; // Subscribe MyMethod to the event
```

#### Unsubscribing from the Event

To unsubscribe from the `OnCheckPointTouched` event:

```csharp
CheckpointTemplate template = (GetTemplate(typeof(CheckpointTemplate)) as CheckpointTemplate);
template.OnCheckPointTouched -= MyMethod; // Unsubscribe MyMethod from the event
```

## CollectableTemplate

This template provides functionality to manage collectable items in the game. To access the `CollectableTemplate`, use the following code:

```csharp
CollectableTemplate template = (GetTemplate(typeof(CollectableTemplate)) as CollectableTemplate);
```

### Property: <mark style="color:yellow;">`ScoreGroup`</mark>

#### Getting the Score Group

To get the score group associated with the collectable item:

```csharp
string scoreGroup = template.ScoreGroup;
```

#### Setting the Score Group

To set the score group for the collectable item:

```csharp
template.ScoreGroup = "NewScoreGroup";
```

### Property: <mark style="color:yellow;">`Score Property`</mark>

#### Getting the Score Value

To get the score value of the collectable item:

```csharp
int score = template.Score;
```

#### Setting the Score Value

To set the score value for the collectable item:

```csharp
template.Score = 100;
```

### Event: <mark style="color:yellow;">`OnCollected`</mark>

#### Subscribing to the Event

To subscribe to the `OnCollected` event:

```csharp
template.OnCollected += MyMethod; // Subscribe MyMethod to the event
```

#### Unsubscribing from the Event

To unsubscribe from the `OnCollected` event:

```csharp
template.OnCollected -= MyMethod; // Unsubscribe MyMethod from the event
```

## DelayBroadcastTemplate

This template manages delayed broadcast functionality in the game. To access the `DelayBroadcastTemplate`, use the following code:

```csharp
DelayBroadcastTemplate template = (GetTemplate(typeof(DelayBroadcastTemplate)) as DelayBroadcastTemplate);
```

### Property: <mark style="color:yellow;">`Delay`</mark>

#### Getting the Delay Time

To get the delay time configured for the broadcast:

```csharp
float delayTime = template.Delay;
```

#### Setting the Delay Time

To set the delay time for the broadcast:

```csharp
template.Delay = 2.5; // Example: set delay time to 2.5 seconds
```

## DestroyOnTemplate

This template manages the behavior of objects that are destroyed after a specified delay. To access the `DestroyOnTemplate`, use the following code:

```csharp
DestroyOnTemplate template = (GetTemplate(typeof(DestroyOnTemplate)) as DestroyOnTemplate);
```

### Property: <mark style="color:yellow;">`DestroyAfter`</mark>

#### Getting the Destruction Delay

To get the delay after which the object is destroyed:

```csharp
float destroyAfter = template.DestroyAfter;
```

#### Setting the Destruction Delay

To set the delay after which the object should be destroyed:

```csharp
template.DestroyAfter = 5.0; // Example: set destruction delay to 5 seconds
```

## DestroyTemplate

This template manages the behavior of objects that are destroyed after a specified delay.  To access the `DestroyTemplate`, use the following code:

```csharp
DestroyTemplate template = (GetTemplate(typeof(DestroyTemplate)) as DestroyTemplate);
```

### Property: <mark style="color:yellow;">`DestroyAfter`</mark>

#### Getting the Destruction Delay

To get the delay after which the object is destroyed:

```csharp
float destroyAfter = template.DestroyAfter;
```

#### Setting the Destruction Delay

To set the delay after which the object should be destroyed:

```csharp
template.DestroyAfter = 5.0; // Example: set destruction delay to 5 seconds
```

## GameProgressTemplate

This template manages game progress functionality in the game. To access the GameProgressTemplate, use the following code:

```csharp
GameProgressTemplate template = (GetTemplate(typeof(GameProgressTemplate)) as GameProgressTemplate);
```

### Property: <mark style="color:yellow;">`CurrentProgress`</mark>

**Getting Current Progress**

To get the current progress:

```csharp
int currentProgress = template.CurrentProgress;
```

### Property: <mark style="color:yellow;">`LerpSpeed`</mark>

**Getting the Lerp Speed**

To get the lerp speed configured for the progress bar:

```csharp
float lerpSpeed = template.LerpSpeed;
```

**Setting the Lerp Speed**

To set the lerp speed for the progress bar:

```csharp
template.LerpSpeed = 1.0f; // Example: set lerp speed to 1.0
```

### Property: <mark style="color:yellow;">`BroadcastOnEveryProgress`</mark>

**Getting the Broadcast On Every Progress**

To get the broadcast trigger configured for each progress point:

```csharp
string broadcastOnEveryProgress = template.BroadcastOnEveryProgress;
```

**Setting the Broadcast On Every Progress**

To set the broadcast trigger for each progress point:

```csharp
template.BroadcastOnEveryProgress = "progress_event"; // Example: set broadcast trigger
```

### Property: <mark style="color:yellow;">`BroadcastOnComplete`</mark>

**Getting the BroadcastOnComplete**

To get the broadcast trigger configured for completion:

```csharp
string broadcastOnComplete = template.BroadcastOnComplete;
```

**Setting the BroadcastOnComplete**

To set the broadcast trigger for completion:

```csharp
template.BroadcastOnComplete = "completion_event"; // Example: set broadcast trigger
```

## GameScoreTemplate

This template manages in-game scoring functionality. To access the GameScoreTemplate, use the following code:

```csharp
GameScoreTemplate template = (GetTemplate(typeof(GameScoreTemplate)) as GameScoreTemplate);
```

### Property: <mark style="color:yellow;">`CurrentScore`</mark>

**Getting Current Score**

To get the current score:

```csharp
int currentScore = template.CurrentScore;
```

### Property: <mark style="color:yellow;">`BestScore`</mark>

**Getting Best Score**

To get the best score achieved:

```csharp
int bestScore = template.BestScore;
```

### Property: <mark style="color:yellow;">`IsScoreUIShown`</mark>

To check if the score UI is currently displayed:

```csharp
bool isScoreUIShown = template.IsScoreUIShown;
```

### Property: <mark style="color:yellow;">`IsBestScoreCalculated`</mark>

**Checking if Best Score Calculation is Enabled**

To check if the best score calculation is enabled:

```csharp
bool isBestScoreCalculated = template.IsBestScoreCalculated;
```

### Event: <mark style="color:yellow;">`OnScoreModified`</mark>

**Subscribing to OnScoreModified Event**

To subscribe to the score modification event:

```csharp
template.OnScoreModified += OnScoreModifiedHandler;
```

**Unsubscribing from OnScoreModified Event**

To unsubscribe from the score modification event:

<pre class="language-csharp"><code class="lang-csharp">template.OnScoreModified -= OnScoreModifiedHandler;
void OnScoreModifiedHandler(int modifiedScore)
        {
                // Handle score modification
<strong>        }
</strong></code></pre>

## GrowTemplate

This template manages growth and scale behavior of objects n the game. To access the GrowTemplate, use the following code:

```csharp
GrowTemplate template = (GetTemplate(typeof(GrowTemplate)) as GrowTemplate);
```

### Property: <mark style="color:yellow;">`ScaleTo`</mark>

**Getting and Setting Scale To**

To get or set the scale to which the object grows:

```csharp
Vector3 scaleTo = template.ScaleTo;
template.ScaleTo = new Vector3(2f, 2f, 2f); // Example of setting scale
```

### Property: <mark style="color:yellow;">`Speed`</mark>

**Getting and Setting Growth Speed**

To get or set the speed at which the object grows:

```csharp
float speed = template.Speed;
template.Speed = 1.5f; // Example of setting speed
```

### Property: <mark style="color:yellow;">`ShouldPingPong`</mark>

**Checking and Setting Ping Pong Behavior**

To check or set whether the growth should ping pong (alternate between scaling up and scaling down):

```csharp
bool shouldPingPong = template.ShouldPingPong;
template.ShouldPingPong = true; // Example of enabling ping pong behavior
```

### Property: <mark style="color:yellow;">`RepeatForever`</mark>

**Checking and Setting RepeatForever**

To check or set whether the growth should repeat indefinitely:

```csharp
bool repeatForever = template.RepeatForever;
template.RepeatForever = true; // Example of enabling repeat forever
```

### Property: <mark style="color:yellow;">`RepeatFor`</mark>

**Getting and Setting Repeat Duration**

To get or set the duration for which the growth should repeat:

```csharp
int repeatFor = template.RepeatFor;
template.RepeatFor = 10; // Example of setting repeat duration
```

### Event: <mark style="color:yellow;">`OnRepetationOver`</mark>

**Subscribing to OnRepetationOver Event**

To subscribe to the event triggered when the repetition is over:

```csharp
template.OnRepetationOver += OnRepetationOverHandler;
```

**Unsubscribing from OnRepetationOver Event**

To unsubscribe from the event triggered when the repetition is over:

```csharp
template.OnRepetationOver -= OnRepetationOverHandler;
void OnRepetationOverHandler()
{
    // Handle repetition over event
}
```

### Event: <mark style="color:yellow;">`OnGrowFinished`</mark>

**Subscribing to OnGrowFinished Event**

To subscribe to the event triggered when the growth is finished:

```csharp
template.OnGrowFinished += OnGrowFinishedHandler;
```

**Unsubscribing from OnGrowFinished Event**

To unsubscribe from the event triggered when the growth is finished:

```csharp
template.OnGrowFinished -= OnGrowFinishedHandler;
```

```csharp
void OnGrowFinishedHandler()
{
    // Handle growth finished event
}
```

## InGameTimerTemplate

This template manages in-game timer functionality. To access the InGameTimerTemplate, use the following code:

```csharp
InGameTimerTemplate template = (GetTemplate(typeof(InGameTimerTemplate)) as InGameTimerTemplate);
```

### Property: <mark style="color:yellow;">`TimerType`</mark>

**Getting Timer Type**

To get the type of timer:

```csharp
TimerType timerType = template.TimerType;
```

### Property: <mark style="color:yellow;">`CurrentTime`</mark>

**Getting Current Time**

To get the current time from the in-game timer handler:

```csharp
float currentTime = template.CurrentTime;
```

### Property: <mark style="color:yellow;">`IsUIShown`</mark>

**Checking if UI is Shown**

To check if the UI associated with the timer is currently shown:

```csharp
bool isUIShown = template.IsUIShown;
```

### Event: <mark style="color:yellow;">`OnTimerUpdated`</mark>

**Subscribing to OnTimerUpdated Event**

To subscribe to the event triggered when the timer is updated:

```csharp
template.OnTimerUpdated += OnTimerUpdatedHandler;
```

**Unsubscribing from OnTimerUpdated Event**

To unsubscribe from the event triggered when the timer is updated:

```csharp
template.OnTimerUpdated -= OnTimerUpdatedHandler;
void OnTimerUpdatedHandler(float updatedTime){
   // Handle timer updated event
}
```

## JumpPadTemplate

This template manages jump pad functionality within the game. To access the JumpPadTemplate, use the following code:

```csharp
JumpPadTemplate template = (GetTemplate(typeof(JumpPadTemplate)) as JumpPadTemplate);
```

### Property: <mark style="color:yellow;">`JumpForce`</mark>

**Getting and Setting Jump Force**

To get or set the jump force of the jump pad:

```csharp
float jumpForce = template.JumpForce;
template.JumpForce = 10.0f; // Example of setting jump force
```

## KillPlayerTemplate

This template manages the behavior related to killing the player in the game. To access the KillPlayerTemplate, use the following code:

```csharp
KillPlayerTemplate template = (GetTemplate(typeof(KillPlayerTemplate)) as KillPlayerTemplate);
```

### Property: <mark style="color:yellow;">`AnimationToPlayOnDeath`</mark>

**Getting and Setting Animation to Play on Death**

To get or set the animation to play when the player dies:

```csharp
string animation = template.AnimationToPlayOnDeath;
template.AnimationToPlayOnDeath = "death_animation"; // Example of setting death animation
```

### Property: <mark style="color:yellow;">`Delay`</mark>&#x20;

**Getting and Setting Delay**

To get or set the delay before respawning the player:

```csharp
float delay = template.Delay;
template.Delay = 3.0f; // Example of setting respawn delay
```

### Property: <mark style="color:yellow;">`RespawnType`</mark>&#x20;

**Getting and Setting Respawn Type**

To get or set the respawn type (snap or lerp):

```csharp
RespawnV2.RespwanType respawnType = template.RespawnType;
template.RespawnType = RespawnV2.RespwanType.Lerp; // Example of setting respawn type
```

### Property: <mark style="color:yellow;">`LerpTime`</mark>

**Getting and Setting Lerp Time**

To get or set the lerp time for respawn:

```csharp
float lerpTime = template.LerpTime;
template.LerpTime = 2.0f; // Example of setting lerp time
```

### Events - <mark style="color:yellow;">`OnAnimationEnded`</mark> and <mark style="color:yellow;">`OnRespawned`</mark>

**Subscribing to Events**

You can subscribe to events that occur when animations end or when the player respawns:

```csharp
template.OnAnimationEnded += HandleAnimationEnd;
template.OnRespawned += HandlePlayerRespawn;

void HandleAnimationEnd()
{
    // Handle animation end logic here
}

void HandlePlayerRespawn()
{
    // Handle player respawn logic here
}
```

## LightTemplate

This template manages the behavior related to controlling a light component in the game. To access the LightTemplate, use the following code:

```csharp
LightTemplate template = (GetTemplate(typeof(LightTemplate)) as LightTemplate);
```

### Property: <mark style="color:yellow;">`Color`</mark>

**Getting and Setting Light Color**

To get or set the color of the light:

```csharp
Color color = template.Color;
template.Color = Color.red; // Example of setting light color
```

### Property: <mark style="color:yellow;">`Intensity`</mark>

**Getting and Setting Light Intensity**

To get or set the intensity of the light:

```csharp
float intensity = template.Intensity;
template.Intensity = 2.0; // Example of setting light intensity
```

### Event: <mark style="color:yellow;">`OnLightPropertiesModified`</mark>

**Subscribing to Events**

You can subscribe to an event that occurs when the light properties are modified:

```csharp
template.OnLightPropertiesModified += HandleLightPropertiesModified;

void HandleLightPropertiesModified()
{
    // Handle light properties modified logic here
}
```

## MoveBetweenPointsTemplate

This template facilitates movement between specified points in the game, utilizing interpolation techniques for smooth transitions. To integrate the `MoveBetweenPointsTemplate`, follow the usage instructions below:

```csharp
MoveBetweenPointsTemplate template = (GetTemplate(typeof(MoveBetweenPointsTemplate)) as MoveBetweenPointsTemplate);
```

### Property: <mark style="color:yellow;">`Points`</mark>

**Accessing Movement Points**

To access or modify the points defining the movement path:

```csharp
List<Vector3> points = template.Points;
template.Points = new List<Vector3> { /* Define new points here */ };
```

### Property: <mark style="color:yellow;">`Speed`</mark>

**Controlling Movement Speed**

To adjust the speed of movement between points:

```csharp
float speed = template.Speed;
template.Speed = 5.0f; // Example of setting movement speed
```

### Property:  <mark style="color:yellow;">`TurnToPoints`</mark>

**Aligning to Movement Points**

To enable or disable the rotation towards movement points:

```csharp
bool turnToPoints = template.TurnToPoints;
template.TurnToPoints = true; // Example of enabling rotation towards points
```

### Property: <mark style="color:yellow;">`DelayAtPoint`</mark>

**Introducing Delay at Points**

To specify a delay upon reaching each movement point:

```csharp
float delay = template.DelayAtPoint;
template.DelayAtPoint = 1.5f; // Example of setting delay at points
```

### Property: <mark style="color:yellow;">`Loop`</mark>

**Enabling Movement Loop**

To enable or disable looping of the movement path:

```csharp
bool loop = template.Loop;
template.Loop = true; // Example of enabling movement loop
```

### Property: <mark style="color:yellow;">`DoCurve`</mark>

**Applying Curve to Movement**

To activate or deactivate curve interpolation for movement:

```csharp
bool doCurve = template.DoCurve;
template.DoCurve = true; // Example of enabling curve interpolation
```

### Property: <mark style="color:yellow;">`LoopType`</mark>

**Defining Loop Interpolation Type**

To specify the interpolation type used for movement looping:

```csharp
InterpolateType loopType = template.LoopType;
template.LoopType = InterpolateType.Linear; // Example of setting loop interpolation type
```

### Events

**Subscribing to Movement Events**

You can subscribe to events triggered during movement:

```csharp
template.OnIntervalReached += HandleIntervalReached;
template.OnReachedEnd += HandleMovementEnd;
template.OnLoopFinished += HandleLoopFinished;

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
```



## MoveTemplate

This template facilitates movement functionality within the game, focusing on translating entities using specified parameters. To integrate the `MoveTemplate`, follow the usage instructions below:

```csharp
MoveTemplate template = (GetTemplate(typeof(MoveTemplate)) as MoveTemplate);
```

### Speed Property

**Controlling Movement Speed**

To adjust the speed of movement:

```csharp
float speed = template.Speed;
template.Speed = 5.0f; // Example of setting movement speed
```

### Loop Property

**Enabling Looping Movement**

To enable or disable looping of the movement:

```csharp
bool loop = template.Loop;
template.Loop = true; // Example of enabling looping movement
```

### Interval Property

**Setting Pause Interval**

To specify a pause interval during movement:

```csharp
float interval = template.Interval;
template.Interval = 1.5f; // Example of setting pause interval
```

### Point Property

**Defining Movement Target**

To set the target position for movement:

```csharp
Vector3 point = template.Point;
template.Point = new Vector3(10f, 0f, 5f); // Example of setting movement target position
```

### Events

**Subscribing to Movement Events**

You can subscribe to events triggered during movement:

```csharp
template.OnStopped += HandleStopped;
template.OnResumed += HandleResumed;

void HandleStopped()
{
    // Handle stopped logic here
}

void HandleResumed()
{
    // Handle resumed logic here
}
```



## MoveToPlayerTemplate

This template facilitates movement towards a player entity within the game, utilizing specified parameters. To integrate the `MoveToPlayerTemplate`, follow the usage instructions below:

```csharp
MoveToPlayerTemplate template = (GetTemplate(typeof(MoveToPlayerTemplate)) as MoveToPlayerTemplate);
```

### Speed Property

**Controlling Movement Speed**

To adjust the speed of movement towards the player:

```csharp
float speed = template.Speed;
template.Speed = 7.0f; // Example of setting movement speed towards the player
```

### Offset Property

**Setting Movement Offset**

To specify an offset relative to the player position:

```csharp
Vector3 offset = template.Offset;
template.Offset = new Vector3(0f, 1f, 0f); // Example of setting movement offset
```

### CancelType Property

**Defining Movement Cancellation Type**

To set the type of cancellation for movement:

```csharp
MoveToPlayer.CancelType cancelType = template.CancelType;
template.CancelType = MoveToPlayer.CancelType.Immediate; // Example of setting cancellation type
```

### Events

**Subscribing to Movement Events**

You can subscribe to events triggered during movement towards the player:

```csharp
template.OnCancelled += HandleCancelled;
template.OnReachedDestination += HandleReachedDestination;
template.OnReachedInitialPosition += HandleReachedInitialPosition;

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
```

## ParticleEffectTemplate

This template manages particle effects within the game, offering flexibility in configuration and event handling. Follow the usage guidelines below to integrate the `ParticleEffectTemplate` into your project:

```csharp
ParticleEffectTemplate template = (GetTemplate(typeof(ParticleEffectTemplate)) as ParticleEffectTemplate);
```

### RepeatCount Property

**Adjusting Repeat Count**

To control the number of times the particle effect repeats:

```csharp
int repeatCount = template.RepeatCount;
template.RepeatCount = 3; // Example of setting repeat count
```

### PlayForever Property

**Enabling Continuous Play**

To enable continuous playback of the particle effect:

```csharp
bool playForever = template.PlayForever; // Get whether continuous playback is enabledk
template.PlayForever = true; // Example of enabling continuous playback
```

### Duration Property

**Setting Duration**

To specify the duration of the particle effect:

```csharp
float duration = template.Duration; // Get the duration of the particle effect
template.Duration = 5.0f; // Example of setting duration
```

### Delay Property

**Configuring Delay**

To set the delay between repetitions of the particle effect:

```csharp
int delay = template.Delay; // Get the value of delay set
template.Delay = 2; // Example of setting delay
```

### Events

**Subscribing to Event Notifications**

You can subscribe to events triggered during the lifecycle of the particle effect:

```csharp
template.OnParticlePlayingCompleted += HandleParticlePlayingCompleted;

void HandleParticlePlayingCompleted()
{
    // Handle logic when particle effect playback completes here
}
```

```csharp
```

## PlayAnimationTemplate

This template facilitates the management and execution of animations within the game environment, offering seamless integration and customization options. Follow the guidelines below to effectively utilize the `PlayAnimationTemplate` class in your project:

```csharp
PlayAnimationTemplate template = (GetTemplate(typeof(PlayAnimationTemplate)) as PlayAnimationTemplate);
```

### CurrentAnimation Property

**Retrieving Current Animation**

To fetch the currently playing animation:

```csharp
string currentAnimation = template.CurrentAnimation;
```

### DefaultAnimation Property

**Setting Default Animation**

To set the default animation for the component:

```csharp
string defaultAnimation = template.DefaultAnimation;
template.DefaultAnimation = "Idle"; // Example of setting default animation
```

### AvailableAnimations Property

**Accessing Available Animations**

To retrieve a list of available animations:

```csharp
TerraList availableAnimations = template.AvailableAnimations;
```

### Events

**Handling Animation Events**

You can subscribe to animation completion events:

```csharp
template.OnAnimationCompleted += HandleAnimationCompleted;

void HandleAnimationCompleted(string animationName)
{
    // Handle logic when animation completes here
}
```

### Methods

**Controlling Animation Playback**

You can control animation playback using the following methods:

```csharp
template.PlayAnimationOverride("Run", true); // Example of playing an animation with looping
template.StopAnimationOverride(); // Example of stopping the current animation
```



## PlayerAnimationControlTemplate

The `PlayerAnimationControlTemplate` class facilitates the control and management of player animations within the game environment, offering seamless integration and customization options. Follow the guidelines below to effectively utilize this template in your project:

```csharp
PlayerAnimationControlTemplate template = (GetTemplate(typeof(PlayerAnimationControlTemplate)) as PlayerAnimationControlTemplate);
```

### AnimationName Property

**Setting and Retrieving Animation Name**

To get or set the current animation name:

```csharp
string animationName = template.AnimationName;
template.AnimationName = "Run"; // Example of setting animation name
```

### ResetAnimationAutomatically Property

**Enabling or Disabling Automatic Animation Reset**

To enable or disable automatic animation reset:

```csharp
bool resetAutomatically = template.ResetAnimationAutomatically;
template.ResetAnimationAutomatically = true; // Example of enabling automatic reset
```

### Events

**Handling Animation Completion Events**

You can subscribe to animation completion events:

```csharp
template.OnAnimationCompleted += HandleAnimationCompleted;

void HandleAnimationCompleted(bool success, string animationName)
{
    // Handle logic when animation completes here
}
```



## PlayPlayersAnimationTemplate

The `PlayPlayersAnimationTemplate` class is designed to manage and control player animations within your game environment, providing essential properties for seamless integration and customization. Here's how you can utilize this template effectively in your project:

```csharp
PlayPlayersAnimationTemplate template = (GetTemplate(typeof(PlayPlayersAnimationTemplate)) as PlayPlayersAnimationTemplate);
```

### AnimationName Property

**Setting and Retrieving Animation Name**

To get or set the current animation name:

```csharp
string animationName = template.AnimationName;
template.AnimationName = "Jump"; // Example of setting animation name
```

### ResetAnimationAutomatically Property

**Enabling or Disabling Automatic Animation Reset**

To enable or disable automatic animation reset:

```csharp
bool resetAutomatically = template.ResetAnimationAutomatically;
template.ResetAnimationAutomatically = true; // Example of enabling automatic rese
```

## PushTemplate

The `PushTemplate` class facilitates control over push components within your game, offering methods to manage resistance properties effectively. Below is a detailed overview of its usage:

```csharp
PushTemplate template = (GetTemplate(typeof(PushTemplate)) as PushTemplate);
```

### Resistance Property

**Managing Resistance**

To access or modify the resistance of the push component:

```csharp
float resistance = template.Resistance;
template.Resistance = 2.5f; // Example of setting resistance value
```

## RandomBroadcastTemplate

This template manages random broadcasting functionality within the game, utilizing specified parameters to handle broadcast strings. To integrate the `RandomBroadcastTemplate`, follow the usage instructions below:

```csharp
RandomBroadcastTemplate template = (GetTemplate(typeof(RandomBroadcastTemplate)) as RandomBroadcastTemplate);
```

### GetAllBroadcastingStrings Property

Fetching All Broadcasting Strings

To retrieve all broadcasting strings:

```csharp
List<string> broadcastingStrings = template.GetAllBroadcastingStrings;
```

### Indexer

Accessing Specific Broadcasting String by Index

To access or modify a specific broadcasting string:

```csharp
string broadcast = template[index];
template[index] = "New Broadcast"; // Example of updating a broadcasting string
```

### GetEnumerator Method

Enumerating Through Broadcasting Strings

To iterate through all broadcasting strings:

```csharp
IEnumerator enumerator = template.GetEnumerator();
while (enumerator.MoveNext())
{
    string broadcast = (string)enumerator.Current;
    // Process each broadcast here
}
```

### CheckIndex Method

Validating Index for Broadcasting Strings

To validate an index before accessing or modifying broadcasting strings:

```csharp
try
{
    template.CheckIndex(index);
    // Proceed with index-valid operations
}
catch (ArgumentOutOfRangeException ex)
{
    // Handle index out of range exception
}
```

### UpdateConditionBroadcasts Method

Updating Broadcasting Strings

To update a specific broadcasting string:

```csharp
template.UpdateConditionBroadcasts(index, "Updated Broadcast")
```

## ResetScoreTemplate

This template manages the resetting of scores within the game, utilizing specified parameters to handle score groups. To integrate the `ResetScoreTemplate`, follow the usage instructions below:

```csharp
ResetScoreTemplate template = (GetTemplate(typeof(ResetScoreTemplate)) as ResetScoreTemplate);
```

### ScoreGroup Property

Managing Score Group

To get or set the score group:

```csharp
string scoreGroup = template.ScoreGroup;
template.ScoreGroup = "NewScoreGroup"; // Example of updating the score group
```

## RotateOscillateTemplate

This template manages the rotation oscillation behavior within the game, allowing customization of the rotation parameters such as axis, degrees, direction, repeat count, and event triggers. To integrate the `RotateOscillateTemplate`, follow the usage instructions below:

```csharp
RotateOscillateTemplate template = (GetTemplate(typeof(RotateOscillateTemplate)) as RotateOscillateTemplate);
```

### RotationAxis Property

Managing Rotation Axis

To get or set the rotation axis:

```csharp
Axis rotationAxis = template.RotationAxis;
template.RotationAxis = Axis.Y; // Example of updating the rotation axis
```

### Degrees Property

Managing Rotation Degrees

To get or set the degrees of rotation:

```csharp
int degrees = template.Degrees;
template.Degrees = 90; // Example of updating the degrees
```

### Direction Property

Managing Rotation Direction

To get or set the rotation direction:

```csharp
Direction direction = template.Direction;
template.Direction = Direction.Clockwise; // Example of updating the direction
```

### RepeatCount Property

Managing Repeat Count

To get or set the repeat count for the rotation:

```csharp
int repeatCount = template.RepeatCount;
template.RepeatCount = 5; // Example of updating the repeat count
```

### Loop Property

Checking Loop Status

To check if the rotation is looping:

```csharp
bool isLooping = template.Loop;
```

### StopOn Property

Managing Stop Condition

To get or set the condition to stop the rotation:

```csharp
string stopOn = template.StopOn;
template.StopOn = "SomeCondition"; // Example of updating the stop condition
```

### ResumeOn Property

Managing Resume Condition

To get or set the condition to resume the rotation:

```csharp
string resumeOn = template.ResumeOn;
template.ResumeOn = "SomeOtherCondition"; // Example of updating the resume condition
```

### Events

Handling Rotation Events

#### OnRepetitionCompleted Event

To subscribe or unsubscribe from the repetition completed event:

```csharp
csharpCopy codetemplate.OnRepetationCompleted += YourEventHandler;
template.OnRepetationCompleted -= YourEventHandler;
```

#### OnRotationCompleted Event

To subscribe or unsubscribe from the rotation completed event:

```csharp
template.OnRotationCompleted += YourEventHandler;
template.OnRotationCompleted -= YourEventHandler;
```

#### OnRotationPaused Event

To subscribe or unsubscribe from the rotation paused event:

```csharp
template.OnRotationPaused += YourEventHandler;
template.OnRotationPaused -= YourEventHandler;
```

#### OnRotationResumed Event

To subscribe or unsubscribe from the rotation resumed event:

```csharp
template.OnRotationResumed += YourEventHandler;
template.OnRotationResumed -= YourEventHandler;
```

## RotateTemplate

This template manages the rotation behavior within the game, allowing customization of the rotation parameters such as axis, speed, and direction. To integrate the `RotateTemplate`, follow the usage instructions below:

```csharp
RotateTemplate template = (GetTemplate(typeof(RotateTemplate)) as RotateTemplate);
```

### RotationAxis Property

Managing Rotation Axis

To get or set the rotation axis:

```csharp
Axis rotationAxis = template.RotationAxis;
template.RotationAxis = Axis.Y; // Example of updating the rotation axis
```

### Speed Property

Managing Rotation Speed

To get or set the speed of rotation:

```csharp
float speed = template.Speed;
template.Speed = 5.0f; // Example of updating the speed
```

### Direction Property

Managing Rotation Direction

To get or set the rotation direction:

```csharp
Direction direction = template.Direction;
template.Direction = Direction.Clockwise; // Example of updating the direction
```

## SetPositionTemplate

This template is used to set the position of an object within the game engine and can be accessed as follows:

```csharp
SetPositionTemplate positionTemplate = GetTemplate(typeof(SetPositionTemplate)) as SetPositionTemplate;
```

### TargetPosition

You can access or set the target position for the object using the `TargetPosition` property.

```scss
positionTemplate.TargetPosition = new Vector3(10, 20, 30); // Sets the target position to (10, 20, 30)
```

### OnPositionUpdated

You can subscribe to the `OnPositionUpdated` event to execute custom logic whenever the position is updated.

```csharp
positionTemplate.OnPositionUpdated += () =>
{
    // Custom logic to execute when the position is updated
    Debug.Log("Position updated");
};
```



## ShowUITemplate

This template manages the display of UI elements within the game, allowing customization of the UI animation type, screen position, icons, texts, and durations. To integrate the `ShowUITemplate`, follow the usage instructions below:

```csharp
ShowUITemplate template = (GetTemplate(typeof(ShowUITemplate)) as ShowUITemplate);
```

### AnimationType Property

Managing UI Animation Type

To get or set the UI animation type:

```csharp
UIAnimation animationType = template.AnimationType;
template.AnimationType = UIAnimation.FadeIn; // Example of updating the animation type
```

### ScreenPosition Property

Managing Screen Position

To get or set the screen position:

```csharp
UIPoint screenPosition = template.ScreenPosition;
template.ScreenPosition = new UIPoint(100, 200); // Example of updating the screen position
```

### UIToShow Property

Managing the UI to Show

To get or set the UI element to show:

```csharp
string uiToShow = template.UIToShow;
template.UIToShow = "MainMenu"; // Example of updating the UI element to show
```

### Icon1Name Property

Managing the First Icon Name

To get or set the name of the first icon:

```csharp
string icon1Name = template.Icon1Name;
template.Icon1Name = "Icon1"; // Example of updating the first icon name
```

### Icon2Name Property

Managing the Second Icon Name

To get or set the name of the second icon:

```csharp
string icon2Name = template.Icon2Name;
template.Icon2Name = "Icon2"; // Example of updating the second icon name
```

### Text1 Property

Managing the First Text

To get or set the first text:

```csharp
string text1 = template.Text1;
template.Text1 = "Welcome"; // Example of updating the first text
```

### Text2 Property

Managing the Second Text

To get or set the second text:

```csharp
string text2 = template.Text2;
template.Text2 = "Start Game"; // Example of updating the second text
```

### Text3 Property

Managing the Third Text

To get or set the third text:

```csharp
string text3 = template.Text3;
template.Text3 = "Options"; // Example of updating the third text
```

### AnimationDuration Property

Managing Animation Duration

To get or set the animation duration:

```csharp
float animationDuration = template.AnimationDuration;
template.AnimationDuration = 1.5f; // Example of updating the animation duration
```

### UIDuration Property

Managing UI Display Duration

To get or set the duration for which the UI is displayed:

```csharp
float uiDuration = template.UIDuration;
template.UIDuration = 5.0f; // Example of updating the UI display duration
```



## SoundFxTemplate

This template manages the sound effects within the game, allowing customization of volume, pitch, 3D audio settings, distance ranges, looping capabilities, and pause/resume events. To integrate the `SoundFxTemplate`, follow the usage instructions below:

```csharp
SoundFxTemplate template = (GetTemplate(typeof(SoundFxTemplate)) as SoundFxTemplate);
```

### Volume Property

Managing Volume

To get or set the volume:

```csharp
float volume = template.Volume;
template.Volume = 0.5f; // Example of updating the volume
```

### Pitch Property

Managing Pitch

To get or set the pitch:

```csharp
float pitch = template.Pitch;
template.Pitch = 1.0f; // Example of updating the pitch
```

### Is3DAudio Property

Managing 3D Audio

To get or set whether the sound is 3D audio:

```csharp
bool is3DAudio = template.Is3DAudio;
template.Is3DAudio = true; // Example of enabling 3D audio
```

### MinDistance Property

Managing Minimum Distance

To get or set the minimum distance for 3D audio:

```csharp
float minDistance = template.MinDistance;
template.MinDistance = 1.0f; // Example of updating the minimum distance
```

### MaxDistance Property

Managing Maximum Distance

To get or set the maximum distance for 3D audio:

```csharp
float maxDistance = template.MaxDistance;
template.MaxDistance = 50.0f; // Example of updating the maximum distance
```

### CanLoop Property

Managing Looping

To get or set whether the sound can loop:

```csharp
bool canLoop = template.CanLoop;
template.CanLoop = true; // Example of enabling looping
```

### PauseOn Property

Managing Pause Event

To get or set the event on which the sound pauses:

```csharp
string pauseOn = template.PauseOn;
template.PauseOn = "PlayerDeath"; // Example of updating the pause event
```

### ResumeOn Property

Managing Resume Event

To get or set the event on which the sound resumes:

```csharp
string resumeOn = template.ResumeOn;
template.ResumeOn = "PlayerRespawn"; // Example of updating the resume event
```

### OnPaused Event

Managing OnPaused Event

To add or remove a callback for when the sound is paused:

```csharp
template.OnPaused += OnSoundPaused; // Adding a callback
template.OnPaused -= OnSoundPaused; // Removing a callback

void OnSoundPaused()
{
    // Your code here
}
```

### OnResumed Event

Managing OnResumed Event

To add or remove a callback for when the sound is resumed:

```csharp
template.OnResumed += OnSoundResumed; // Adding a callback
template.OnResumed -= OnSoundResumed; // Removing a callback

void OnSoundResumed()
{
    // Your code here
}
```



## SwitchTemplate

This template manages the switch component within the game, allowing the addition of custom actions when the switch is toggled on or off. To integrate the `SwitchTemplate`, follow the usage instructions below:

```csharp
SwitchTemplate template = (GetTemplate(typeof(SwitchTemplate)) as SwitchTemplate);
```

### OnToggledOn Event

Managing OnToggledOn Event

To add or remove a callback for when the switch is toggled on:

```csharp
template.OnToggledOn += OnSwitchToggledOn; // Adding a callback
template.OnToggledOn -= OnSwitchToggledOn; // Removing a callback

void OnSwitchToggledOn()
{
    // Your code here
}
```

### OnToggledOff Event

Managing OnToggledOff Event

To add or remove a callback for when the switch is toggled off:

```csharp
template.OnToggledOff += OnSwitchToggledOff; // Adding a callback
template.OnToggledOff -= OnSwitchToggledOff; // Removing a callback

void OnSwitchToggledOff()
{
    // Your code here
}
```

## TeleportTemplate

This template manages the teleport component within the game, allowing the addition of custom actions when teleportation occurs. To integrate the `TeleportTemplate`, follow the usage instructions below:

```csharp
TeleportTemplate template = (GetTemplate(typeof(TeleportTemplate)) as TeleportTemplate);
```

### TeleportPoint Property

Getting and Setting the TeleportPoint

To get or set the teleport destination point:

```csharp
Vector3 currentPoint = template.TeleportPoint; // Getting the teleport point
template.TeleportPoint = new Vector3(x, y, z); // Setting the teleport point
```

### OnTeleported Event

Managing OnTeleported Event

To add or remove a callback for when the teleportation occurs:

```csharp
template.OnTeleported += OnTeleport; // Adding a callback
template.OnTeleported -= OnTeleport; // Removing a callback

void OnTeleport()
{
    // Your code here
}
```



## TickTemplate

This template manages the tick component within the game, providing access to conditions and events related to tick operations. To integrate the `TickTemplate`, follow the usage instructions below:

```csharp
TickTemplate template = (GetTemplate(typeof(TickTemplate)) as TickTemplate);
```

### Indexer

Getting and Setting Values by Index

To get or set values by index:

```csharp
string value = template[index]; // Getting value by index
template[index] = "newValue"; // Setting value by index
```

### Length Property

Getting the Length of Condition Broadcasts

To get the number of condition broadcasts:

```csharp
int length = template.Length;
```

### StartOn Property

Getting and Setting the Start Condition

To get or set the start condition:

```csharp
string startCondition = template.StartOn; // Getting the start condition
template.StartOn = "newStartCondition"; // Setting the start condition
```

### StopOn Property

Getting and Setting the Stop Condition

To get or set the stop condition:

```csharp
string stopCondition = template.StopOn; // Getting the stop condition
template.StopOn = "newStopCondition"; // Setting the stop condition
```

### ResumeOn Property

Getting and Setting the Resume Condition

To get or set the resume condition:

```csharp
string resumeCondition = template.ResumeOn; // Getting the resume condition
template.ResumeOn = "newResumeCondition"; // Setting the resume condition
```

### OnStarted Event

Managing OnStarted Event

To add or remove a callback for when the tick starts:

```csharp
template.OnStarted += OnTickStarted; // Adding a callback
template.OnStarted -= OnTickStarted; // Removing a callback

void OnTickStarted()
{
    // Your code here
}
```

### OnPaused Event

Managing OnPaused Event

To add or remove a callback for when the tick is paused:

```csharp
template.OnPaused += OnTickPaused; // Adding a callback
template.OnPaused -= OnTickPaused; // Removing a callback

void OnTickPaused()
{
    // Your code here
}
```

### OnResumed Event

Managing OnResumed Event

To add or remove a callback for when the tick is resumed:

```csharp
template.OnResumed += OnTickResumed; // Adding a callback
template.OnResumed -= OnTickResumed; // Removing a callback

void OnTickResumed()
{
    // Your code here
}
```

### OnTick Event

Managing OnTick Event

To add or remove a callback for each tick:

```csharp
template.OnTick += OnTickAction; // Adding a callback
template.OnTick -= OnTickAction; // Removing a callback

void OnTickAction()
{
    // Your code here
}
```

## TogglePlayerMovementTemplate

## TogglePlayerMovementTemplate

This template manages the player movement component, specifically handling the stun animation and shader effects, and provides events for pause and resume actions. To integrate the `TogglePlayerMovementTemplate`, follow the usage instructions below:

```csharp
TogglePlayerMovementTemplate template = (GetTemplate(typeof(TogglePlayerMovementTemplate)) as TogglePlayerMovementTemplate);
```

### PlayStunAnimation Property

Getting and Setting the Stun Animation

To get or set the stun animation state:

```csharp
bool isStunAnimationOn = template.PlayStunAnimation; // Getting the stun animation state
template.PlayStunAnimation = true; // Setting the stun animation state
```

### ChangeToStunShader Property

Getting and Setting the Stun Shader

To get or set the stun shader state:

```csharp
bool isStunShaderOn = template.ChangeToStunShader; // Getting the stun shader state
template.ChangeToStunShader = true; // Setting the stun shader state
```

### ResumeOn Property

Getting and Setting the Resume Condition

To get or set the resume condition:

```csharp
string resumeCondition = template.ResumeOn; // Getting the resume condition
template.ResumeOn = "newResumeCondition"; // Setting the resume condition
```

### OnPaused Event

Managing OnPaused Event

To add or remove a callback for when the player movement is paused:

```csharp
template.OnPaused += OnMovementPaused; // Adding a callback
template.OnPaused -= OnMovementPaused; // Removing a callback

void OnMovementPaused()
{
    // Your code here
}
```

### OnResumed Event

Managing OnResumed Event

To add or remove a callback for when the player movement is resumed:

```csharp
template.OnResumed += OnMovementResumed; // Adding a callback
template.OnResumed -= OnMovementResumed; // Removing a callback

void OnMovementResumed()
{
    // Your code here
}
```

## UpdateScoreTemplate

This template manages the update score component, specifically handling score groups, modifiers, and score values. It integrates with the `ScoreHandler` to get and set scores. To integrate the `UpdateScoreTemplate`, follow the usage instructions below:

```csharp
UpdateScoreTemplate template = (GetTemplate(typeof(UpdateScoreTemplate)) as UpdateScoreTemplate);
```

### ScoreGroup Property

Getting and Setting the Score Group

To get or set the score group:

```csharp
string scoreGroup = template.ScoreGroup; // Getting the score group
template.ScoreGroup = "newScoreGroup"; // Setting the score group
```

### Modifier Property

Getting and Setting the Modifier

To get or set the modifier:

```csharp
Modifier modifier = template.Modifier; // Getting the modifier
template.Modifier = Modifier.Add; // Setting the modifier
```

### Score Property

Getting and Setting the Score

To get or set the score:

```csharp
int score = template.Score; // Getting the score
template.Score = 100; // Setting the score
```

### GetScore Method

Retrieving the Current Score

To get the current score from the `ScoreHandler`:

```csharp
int currentScore = template.GetScore();
```

### SetScore Method

Setting a New Score

To set a new score using the `ScoreHandler`:

```csharp
template.SetScore(150);
```

## UpdateTimerTemplate

This template manages the update timer component, specifically handling modifiers, update intervals, and current time. It integrates with the `InGameTimeHandler` to get and set in-game time. To integrate the `UpdateTimerTemplate`, follow the usage instructions below:

```csharp
UpdateTimerTemplate template = (GetTemplate(typeof(UpdateTimerTemplate)) as UpdateTimerTemplate);
```

### Modifier Property

Getting and Setting the Modifier

To get or set the modifier:

```csharp
Modifier modifier = template.Modifier; // Getting the modifier
template.Modifier = Modifier.Add; // Setting the modifier
```

### UpdateBy Property

Getting and Setting the Update Interval

To get or set the update interval:

```csharp
int updateBy = template.UpdateBy; // Getting the update interval
template.UpdateBy = 5; // Setting the update interval
```

### CurrentTime Property

Getting and Setting the Current Time

To get or set the current time:

```csharp
float currentTime = template.CurrentTime; // Getting the current time
template.CurrentTime = 10.5f; // Setting the current time
```

### GetTime Method

Retrieving the Current Time

To get the current time from the `InGameTimeHandler`:

```csharp
float currentTime = template.GetTime();
```

### SetTime Method

Setting a New Time

To set a new time using the `InGameTimeHandler`:

```csharp
template.SetTime(12.0f);
```
