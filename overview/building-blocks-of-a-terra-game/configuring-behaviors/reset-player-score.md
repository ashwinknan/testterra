# Reset Player Score

You may often want to enhance the game-play experience by resetting the game score  to zero by  when certain conditions are met in the game play. For instance, you may want to reset score when the player starts a new game or progresses to a new level

In such cases, you use the `Reset Player Score` Behavior Template.&#x20;

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize how the player score is to be updated

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for resetting the score. There are four triggers allowed:<br><mark style="color:purple;"><code>Player Touches</code></mark>- Resets the score when the player touches the selected object<br><mark style="color:purple;"><code>Other Object Touches</code></mark> - Resets the score when another object touches the selected object<br><mark style="color:purple;"><code>Clicked</code></mark> - Resets the score when you click the selected object<br><mark style="color:purple;"><code>Broadcast Listened</code></mark> - Resets the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be reset based on the trigger event happening</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

