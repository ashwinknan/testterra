# Adding Global Logic Components

Global Logic Components affect the overall game and not just individual GameObjects. These components run in the background but significantly influence the entire gameplay experience. All these components are accessible by clicking on the Essentials button in the Quick Access Menu. The Builder Panel then shows a list of all Game systems.&#x20;

Some global logic components that are present in Terra Studio are listed below:&#x20;

## Game Timer

The Game Timer component is a critical system that manages time-related aspects within the game. It functions as a timer that integrates with game logic.This component is particularly useful in games involving countdowns or time-limited challenges, ensuring precise control over gameplay duration.

### Adding a Game Timer

To add a game timer, follow these steps:&#x20;

* Select the joystick icon in the Main Tool bar&#x20;
* Click on Game Timer

You can now see the Game Timer's properties in the Inspector Panel on the right. The game timer also shows up on the Essentials Tab in the Quick Access Menu

### Configuring the Game Timer

You can configure the following properties of the game timer in the Inspector Panel:&#x20;

| Parameter                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Duration Input`                   | Enter the time in seconds for how long the timer should run.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `Timer Type`                       | Choose between counting up towards a target time (Count Up) or counting down from a set time (Count Down).                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `Generate Broadcast on Completion` | Generate either a Game Win signal, a Game Lose signal, or a Custom Broadcast Signal once the timer is complete.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `Advanced`                         | <p>Configure a broadcast signal based on either a specific time or a repeat interval:</p><ul><li>Under Advanced Options, choose "Broadcast Type" and select either "At" for a specific time or "Every" for a repeat interval. </li><li>If you select "At," input the time in seconds for when the signal should occur (e.g., "35" for the 35th second). </li><li>If you select "Every," enter the interval in seconds for the repeat (e.g., "5" for a signal every 5 seconds). </li><li>Choose your broadcast "Game Win," "Game Lose," or a Custom signal.</li></ul> |
| `Show UI Toggle`                   | Choose to display the timer on-screen or keep it running silently in the background.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

### Customizing Game Timer Behavior using T\#

You can also customize the game timer by accessing it's T# wrapper - InGameTimerTemplate This template manages in-game timer functionality.&#x20;

#### Properties and Methods in InGameTimerTemplate

<table data-header-hidden><thead><tr><th width="148"></th><th width="166"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>TimerType</td><td>Get the type of timer.</td></tr><tr><td><strong>Property</strong></td><td>CurrentTime</td><td>Get the current time from the in-game timer handler.</td></tr><tr><td><strong>Property</strong></td><td>IsUIShown</td><td>Check if the UI associated with the timer is currently shown.</td></tr><tr><td><strong>Event</strong></td><td>OnTimerUpdated</td><td>Event triggered when the timer is updated.</td></tr></tbody></table>

#### Usage Example for InGameTimerTemplate

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

You can also use the UpdateTimer which  manages the timer component, handling modifiers, update intervals, and current time. It integrates with the `InGameTimeHandler` to get and set in-game time.&#x20;

#### Properties and Methods in UpdateTimerTemplate

<table data-header-hidden><thead><tr><th width="136"></th><th width="137"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>Modifier</td><td>Get or set the modifier for timer updates.</td></tr><tr><td><strong>Property</strong></td><td>UpdateBy</td><td>Get or set the update interval.</td></tr><tr><td><strong>Property</strong></td><td>CurrentTime</td><td>Get or set the current time.</td></tr><tr><td><strong>Method</strong></td><td>GetTime</td><td>Retrieve the current time from the <code>InGameTimeHandler</code>.</td></tr><tr><td><strong>Method</strong></td><td>SetTime</td><td>Set a new time using the <code>InGameTimeHandler</code>.</td></tr></tbody></table>

#### Usage Example for UpdateTimerTemplate

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

## Score

The Score system tracks how players perform in a game, showing their competition level and progress. Every game automatically includes a primary score group called the Main Score\_GameScore. This group becomes active when you use certain game logic templates to change scores.

### **Score Groups**

A score group is a system used to track various scores within a game, allowing you to monitor multiple achievements or performance metrics independently. For example, a game might have separate score groups for different objectives, such as collecting different types of items or completing various tasks. Score Groups helps in tracking specific areas of a player's performance and progress. Each metric you want to track will have a separate score group associated with it.&#x20;

Every game automatically includes a primary score group called **Main Score\_GameScore**. This group becomes active when certain game logic templates are used to modify scores. The value within a score group can only be altered by specific logic components:

* **Collectable Logic Components**: Changes the score when items are picked up.
* **Update Score Logic Components**: Directly modifies the score.
* **Reset Score Logic Component**: Resets the score to zero.
* **Carriable Logic Component**: Uses the score as currency for carrying certain objects.
* **Deposit Logic Component**: Uses the score to place items in a designated location.

### Creating & Updating Score Groups

You can create a new score group only when you add one of the five mentioned logic components. In the editable properties of the behavior, you'll find a "Score Group" option. Here, you can choose to update the existing "Main Score\_GameScore" or create a new custom score group by selecting Custom. If you select Custom Score Group, a new score group will be created, and it will appear under Essentials alongside the "Main Score\_GameScore."

After this you must also decide how much to change the score when the event starts. You can pick any integer for the change.&#x20;

### Configuring Score Groups

You can further configure Score Groups by selecting Essentials from the Quick Access Menu and clicking on the relevant score group you want to customize. Here are the options available

* **ShowUI Toggle Button**: Shows the score on the game screen when this is turned on.
* **UI Prefab Dropdown**: This option lets you choose from a dropdown menu the UI templates where ShowUI will display the score. These templates are predetermined.
* **Persistent Toggle**: Allows you to keep the same score group total when moving from one level to the next. If not chosen, the score group starts over at zero with each new level.
* **Save Best Score Toggle**: When selected, this saves the player's highest score.
* **Show Best ScoreUI Toggle**: When you turn on the "Save Best Score" option, it displays your highest score on the game screen.
* **BestScore UI PreFab Dropdown**: This lets you choose the UI templates that should display the highest score in ShowUI.

Scores can also be configured using T# wrappers - , GetScoreTemplate, UpdateScoreTemplate and ResetScore Template.&#x20;

The GetScore template manages in-game scoring functionality.&#x20;

Properties and Methods in GameScoreTemplate&#x20;

<table data-header-hidden><thead><tr><th width="137"></th><th width="207"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>CurrentScore</td><td>Get or set the current score.</td></tr><tr><td><strong>Property</strong></td><td>BestScore</td><td>Get or set the best score achieved.</td></tr><tr><td><strong>Property</strong></td><td>IsScoreUIShown</td><td>Check if the score UI is currently displayed.</td></tr><tr><td><strong>Property</strong></td><td>IsBestScoreCalculated</td><td>Check if the best score calculation is enabled.</td></tr><tr><td><strong>Event</strong></td><td>OnScoreModified</td><td>Event triggered when the score is modified.</td></tr></tbody></table>

Usage Example in GameScoreTemplate

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

The UpdateScore template manages the score component, handling score groups, modifiers, and score values. It integrates with the `ScoreHandler` to get and set scores. Access it as follows:

#### Properties and Methods in UpdateScoreTemplate

<table data-header-hidden><thead><tr><th width="138"></th><th width="138"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>ScoreGroup</td><td>Get or set the score group.</td></tr><tr><td><strong>Property</strong></td><td>Modifier</td><td>Get or set the modifier for score updates.</td></tr><tr><td><strong>Property</strong></td><td>Score</td><td>Get or set the score value.</td></tr><tr><td><strong>Method</strong></td><td>GetScore</td><td>Retrieve the current score from the <code>ScoreHandler</code>.</td></tr><tr><td><strong>Method</strong></td><td>SetScore</td><td>Set a new score using the <code>ScoreHandler</code>.</td></tr></tbody></table>

#### Usage Example for UpdateScoreTemplate

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

The ResetScoreTemplate manages the resetting of scores within the game, utilizing specified parameters to handle score groups and reset them. Access it as follows:

#### Properties in ResetScoreTemplate

<table data-header-hidden><thead><tr><th width="129"></th><th width="138"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>ScoreGroup</td><td>Get or set the score group.</td></tr></tbody></table>

#### Usage Example for ResetScoreTemplate

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

## Health

The Health system is a background system that tracks the player health. There are only three behavior blocks that can affect player health - the Increase Player HP, the Decrease Player HP and the Reset Player Health logic components. By default, the player health is set to a value of 100. When the player health becomes zero, the player is respawned to the last checkpoint in the game, unless configured otherwise.

To configure the Health System, click on Essentials in the Quick Access Menu and select PlayerHealth. You can then configure the following properties of the Health system:

* **Auto Heal Rate**: Turn on Auto Heal and choose how fast the Health should go up every second.
* **Generate a Broadcast when Player Health becomes zero**: You can create a broadcast for winning a game, losing a game, or a custom message.

## Game Progress

The Game Progress System tracks the player's advancement in the game according to predefined progress points. It provides players with a sense of achievement and progression as they play. Multiple progress points can be added through the inspector panel, allowing for greater customization and flexibility in the game's structure.

#### To add a game progress system,

1. From the main toolbar at the top of the editor screen, select "GameProgress" to add the game system to the Essentials tab.
2. In the builder menu on the left side of the screen, navigate to the "Essential" tab.
3. Find the "GameProgress" system in the builder panel.
4. Click on "GameProgress" to open the inspector panel.
5. In the inspector panel, you can customize the parameters according to your needs and preferences.

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Progress start</td><td>This parameter helps you define the point the game progress will be tracked.<br>Game starts - At the start of the game<br>Broadcast Listened -Starts tracking the progress when it listens to a broadcast from another object </td></tr><tr><td>Progress points </td><td>List of diffrent milestones in the game</td></tr><tr><td>Persistent</td><td>Game progress came be made persistent by checking the checkbox </td></tr><tr><td>BroadCast at points </td><td>Broadcast can be trigger when player reaches a paticular milestone </td></tr><tr><td>BroadCast On Completion </td><td>Broadcast can be triggered when player reaches the fine milestone.</td></tr></tbody></table>

## Level Mapper

In game development, leveling up is a core feature that not only marks progression but also enriches the player's experience by offering tangible rewards and new challenges. The Level Mapper game system is designed for customizing the upgrade paths of objects within a game. This can include example use-cases like:

* **Weapon evolution**: Weapons can evolve or be upgraded as players collect certain materials or reach particular benchmarks&#x20;
* **Building upgrades**:  to unlock new features or improve their efficiency (upgrading a farm may increase food production rates or a barracks might allow for the training of more advanced units.)
* **Character Progression:** Accumulating enough XP results in the character gaining a level, which might increase the character's stats (like health, strength, agility) and unlock new abilities or skills.

By utilizing the Level Mapper, developers can set clear, trackable goals for players, encouraging engagement and offering rewarding gameplay experiences as they watch their in-game assets grow and evolve.\
The [level-up](https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/\~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/level-up) behavior can be utilized to adjust the progression paths of objects based on the Level Mapper system.

#### How to add Level mapper?

1. From the main toolbar at the top of the editor screen, select "LevelUpgrader" to add the game system to the Essentials tab.
2. In the builder menu on the left side of the screen, navigate to the "Essential" tab.
3. Find the "LevelMapper" system in the builder panel.
4. Click on "LevelMapper" to open the inspector panel.
5. In the inspector panel, you can customize the parameters according to your needs and preferences.

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Group</td><td>custom name allows the game to keep track of the variables that helps level up the game.<br>steps:<br>1. Click on custom option<br>2. Name the variable in the field added below.</td></tr><tr><td>Cost Type</td><td>The parameter that helps achieve the next level <br>There are two options available:<br>1. Resource (Game Score)<br>2. Carryable <br>select any one based on the game requirement.</td></tr><tr><td>Resource Tag</td><td>This is the parameter whose value will be affected once we achieve level up.</td></tr><tr><td>Value</td><td>Update in the property of the group name after you achieve level upgrade</td></tr><tr><td>Currency</td><td>Cost of upgrading to a new level</td></tr></tbody></table>

6. By following these steps, you will have successfully designed upgrade paths for objects within the game.
7. To use this system to upgrade different in-game objects, utilize the Level Up behavior. Refer to the provided link to learn how to add the "[Level Up](https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/\~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/level-up)" behavior.

## Customer Manger

Customer manager is a game system used to spawn and manage the customer. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Customer Manager When</td><td>This dropdown list allows to specify when new customers will be spawned. It can be triggered either on game start or on any broadcast.</td></tr><tr><td>Broadcast data</td><td>This dropdown can be used to add any broadcast at every customer being spawned.</td></tr><tr><td>Delay between</td><td>This Field can be used to add a delay between spawning of each round of customer.</td></tr><tr><td>Level </td><td>This section is used to adjust the rate at which customers are spawned in progressive manner. you can create multiples levels and define the range of customer spawned for each level.</td></tr><tr><td>Defficulty</td><td>You need to define "X" and "Y' values. the number of customer spawned will lie between these values. once the number of customer spawned reaches the "Max spawn" value, the level will get upgraded and next level block will get executed</td></tr><tr><td>Max spawn</td><td>You can specify here the max number of customer that can be spawned in each level</td></tr></tbody></table>

## Order Generator

Order Generator is a game system responsible for generating order for each customer based on the availabilty of items in the store. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type </td><td>This dropdown list is used to specify the type of order. It can either be a storage or a service.</td></tr><tr><td>Maximum number in an order</td><td>This field can be used to specify the maximum number of items that an order can have.</td></tr><tr><td>Items </td><td></td></tr><tr><td>Group</td><td></td></tr><tr><td>Cost </td><td></td></tr><tr><td>Data </td><td>This section is used to adjust the number of item per order at each specific level. you can create multiples levels and define the range of items that each order should contain at any specific level.</td></tr><tr><td>Difficulty</td><td>You need to define "X" and "Y' values. the number of items in the order will lie between these values. once the number of items reaches the "Threshold" value, the level will get upgraded and next level block will get executed</td></tr><tr><td>Max spawn</td><td>You can specify here the max number of items that can be added in order at each level.</td></tr></tbody></table>

## Path finder

Path finder is a game system that is used to define the area in which the customer can move. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Path finder UI initializes when</td><td></td></tr><tr><td>Lowest point </td><td>This coordinate is used to define the one of cordinate of the diganol of the rectangular area in which the customers can move.</td></tr><tr><td>Highest point</td><td>This coordinate is used to define the other coordinate of the diganol of the rectangular area in which the customers can move.</td></tr><tr><td> Navmesh accur </td><td></td></tr><tr><td>Obstacle avoiding distance offset </td><td>This field can be used to define the distance that the player would maintain from the obstacle </td></tr><tr><td>Minimum height</td><td>This field is used to define the minimum height below which any structure in the player's path would be considered as obstacle </td></tr><tr><td>Maximum height</td><td>This field is used to define the maximum height below which any structure in the player's path would be considered as obstacle and player needs to avoid. </td></tr><tr><td>POI distance offset </td><td>This field is used to define the distance that player need to maintain from POI in the game.</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. </td></tr></tbody></table>
