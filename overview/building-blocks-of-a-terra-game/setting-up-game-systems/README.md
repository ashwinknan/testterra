# Setting up Game Systems

Game System blocks are systems which affect the overall game and not just individual Assets. Unlike Assets , SFX, Behaviors and Particles which are clearly visible or perceivable, Game systems run in the background but significantly influence the entire gameplay experience. All Game Systems are accessible by clicking on the Essentials button in the Quick Access Menu. The Builder Panel then shows a list of all Game systems.&#x20;

Some game systems that are present in Terra Studio are listed below:&#x20;

## Game Timer

The timer is a critical system that manages the time-related aspects within the game - particular useful in games involving countdowns or time-limited challenges.&#x20;

### Adding a Game Timer

To add a game timer, follow these steps:&#x20;

* Select the joystick icon in the Main Tool bar&#x20;
* Click on Game Timer

You can now see the Game Timer's properties in the Inspector Panel on the right.&#x20;

### Configuring the Game Timer

You can configure the following properties of the game timer in the Inspector Panel:&#x20;

* **Duration Input:** Enter the time in seconds for how long the timer should run.
* **Timer Type Dropdown:** Choose between counting up towards a target time (Count Up) or counting down from a set time (Count Down)
* **Generate Game Signal on Completion:** Generate either a Game Win signal, a Game Lose signal or a Custom Broadcast Signal once the timer is complete.&#x20;
* **Generate Game Signal at a pre-set time:** You need to do the following :
  1. Choose the "Broadcast Type" under Advanced Options and select "At."
  2. To generate the Game Signal, please input the time in seconds. For example, input "35" for the signal to occur at the 35th second.
  3. Choose your broadcast signal: "Game Win," "Game Lose," or a Custom signal.
* **Generate Game Signal at a pre-set frequency:** You need to do the following :
  1. Choose the "Broadcast Type" under Advanced Options and select "Every."
  2. Enter the number of seconds for the repeat interval of the broadcast in the Value Field. For example, for a repeat every 5 seconds, enter 5
  3. Choose your broadcast signal: "Game Win," "Game Lose," or a Custom signal.
* **Show UI Toggle:** Choose to display the timer on-screen or keep it running silently in the background.

## Score

The Score system tracks how players perform in a game, showing their competition level and progress. Every game automatically includes a primary score group called the Main Score\_GameScore. This group becomes active when you use certain game behaviors to change scores.

### Behavior blocks that enable you to update scores

The value of scores in score groups can be altered only by using these these behaviors:

* **Collectable Behavior**: Changing score on picking up items.
* **Update Score Behavior**: To change the score.
* **Reset Score Behavior**: Resets the score to zero.
* **Carriable Behavior**: Using score as a currency for carrying a certain object
* **Deposit Behavior**: Using score to place items in a specified location.

### Creating New Score Groups

You can create extra score groups to track different achievements. For example, if your game includes two types of items to collect, you can set up a separate score group for each type for independent tracking.

### Updating Score Groups

Once you have added one of the five mentioned behaviors, you'll find a "Group" option in the editable properties of the behavior. Here, you can either select Main to update the "Main Score\_GameScore" or create a new custom score group by selecting Custom.

After this you must also decide how much to change the score when the event starts. You can pick any integer for the change.&#x20;

### Configuring Score Groups

You can further configure Score Groups by selecting Essentials from the Quick Access Menu and clicking on the relevant score group you want to customize. Here are the options available

* **ShowUI Toggle Button**: Shows the score on the game screen when this is turned on.
* **UI Prefab Dropdown**: This option lets you choose from a dropdown menu the UI templates where ShowUI will display the score. These templates are predetermined.
* **Persistent Toggle**: Allows you to keep the same score group total when moving from one level to the next. If not chosen, the score group starts over at zero with each new level.
* **Save Best Score Toggle**: When selected, this saves the player's highest score.
* **Show Best ScoreUI Toggle**: When you turn on the "Save Best Score" option, it displays your highest score on the game screen.
* **BestScore UI PreFab Dropdown**: This lets you choose the UI templates that should display the highest score in ShowUI.

## Health

The Health system is a background system that tracks the player health. There are only three behavior blocks that can affect player health - the Increase Player Health, the Decrease Player Health Block and the Reset Player Health Block. By default, the player health is set to a value of 100. When the player health becomes zero, the player is respawned to the last checkpoint in the game.&#x20;

### Configuring the Health System

To configure the Health System, click on Essentials in the Quick Access Menu and select PlayerHealth. You can then configure the following properties of the Health system:

* **Auto Heal Rate**: Turn on Auto Heal and choose how fast the Health should go up every second.
* **Generate a Signal when Player Health becomes zero**: You can create a signal for winning a game, losing a game, or a custom message.

### Game Progress

The Game Progress System tracks the player's advancement in the game according to predefined progress points. It provides players with a sense of achievement and progression as they play. Multiple progress points can be added through the inspector panel, allowing for greater customization and flexibility in the game's structure.

#### How to add game progress system?

1. From the main toolbar at the top of the editor screen, select "GameProgress" to add the game system to the Essentials tab.
2. In the builder menu on the left side of the screen, navigate to the "Essential" tab.
3. Find the "GameProgress" system in the builder panel.
4. Click on "GameProgress" to open the inspector panel.
5. In the inspector panel, you can customize the parameters according to your needs and preferences.

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Progress start</td><td>This parameter helps you define the point the game progress will be tracked.<br>Game starts - At the start of the game<br>Broadcast Listened -Starts tracking the progress when it listens to a broadcast from another object </td></tr><tr><td>Progress points </td><td>List of diffrent milestones in the game</td></tr><tr><td>Persistent</td><td>Game progress came be made persistent by checking the checkbox </td></tr><tr><td>BroadCast at points </td><td>Broadcast can be trigger when player reaches a paticular milestone </td></tr><tr><td>BroadCast On Completion </td><td>Broadcast can be triggered when player reaches the fine milestone.</td></tr></tbody></table>

### Level Mapper

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

### Customer Manger

Customer manager is a game system used to spawn and manage the customer. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Customer Manager When</td><td>This dropdown list allows to specify when new customers will be spawned. It can be triggered either on game start or on any broadcast.</td></tr><tr><td>Broadcast data</td><td>This dropdown can be used to add any broadcast at every customer being spawned.</td></tr><tr><td>Delay between</td><td>This Field can be used to add a delay between spawning of each customer.</td></tr><tr><td>Level </td><td>This section is used to adjust the rate at which customers are spawned in progressive manner. you can create multiples levels and define the range of customer spawned for each level.</td></tr><tr><td>Defficulty</td><td>You need to deffine "X" and "Y' values. the number of customer spawned will lie between these values. once the number of customer spawned reaches the "Max spawn" value, the level will get upgraded and next level block will get executed</td></tr><tr><td>Max spawn</td><td>You can specify here the max number of customer that can be spawned in each level</td></tr></tbody></table>

### Order Generator

&#x20;Order Generator is a game system responsible for generating order for each customer based on the availabilty of items in the store. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type </td><td>This dropdown list is used to specify the type of order. It can either be a storage or a service.</td></tr><tr><td>Maximum number in an order</td><td>This field can be used to specify the maximum number of items that an order can have.</td></tr><tr><td>Items </td><td></td></tr><tr><td>Group</td><td></td></tr><tr><td>Cost </td><td></td></tr><tr><td>Data </td><td>This section is used to adjust the number of item per order at each specific level. you can create multiples levels and define the range of items that each order should contain at any specific level.</td></tr><tr><td>Defficulty</td><td>You need to deffine "X" and "Y' values. the number of items in the order will lie between these values. once the number of items reaches the "Threshold" value, the level will get upgraded and next level block will get executed</td></tr><tr><td>Max spawn</td><td>You can specify here the max number of items that can be added in order at each level.</td></tr></tbody></table>

### Path finder

Path finder is a game system that is used to define the area in which the customer can move. This is a game system mostly used in the tycoon games.

To add this game system, follow these steps:

1. Navigate to the essentials tab from the builder menu.
2. Click on "Customer Manager".
3. In the Inspector panel, you can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Path finder UI initializes when</td><td></td></tr><tr><td>Lowest point </td><td>This coordinate is used to define the one of cordinate of the diganol of the rectangular area in which the customers can move.</td></tr><tr><td>Highest point</td><td>This coordinate is used to define the other coordinate of the diganol of the rectangular area in which the customers can move.</td></tr><tr><td> Navmesh accur </td><td></td></tr><tr><td>Obstacle avoiding distance offset </td><td>This field can be used to define the distance that the player would maintain from the obstacle </td></tr><tr><td>Minimum height</td><td>This field is used to define the minimum height below which any structure in the player's path would be considered as obstacle </td></tr><tr><td>Maximum height</td><td>This field is used to define the maximum height below which any structure in the player's path would be considered as obstacle and player needs to avoid. </td></tr><tr><td>POI distance offset </td><td>This field is used to define the distance that player need to maintain from POI in the game.</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. </td></tr></tbody></table>
