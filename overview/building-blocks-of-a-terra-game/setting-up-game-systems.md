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
