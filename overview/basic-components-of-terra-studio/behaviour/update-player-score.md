# Update Player Score

You may often want to enhance the game-play experience by updating the game score by  when certain conditions are met in the game play. For instance, you may want to:&#x20;

* Update the score when the player collects certain items, like coins, gems, or power-ups. This encourages exploration and rewards players for their curiosity.
* Increase the player's score upon completing a level or achieving a milestone within the game. For example, finishing a race track or solving a puzzle.
* Award points for unique or challenging achievements that are outside the normal gameplay loop, such as discovering hidden areas

In such cases, you use the `Update Player Score` Behavior Template.&#x20;

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize how the player score is to be updated

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for updating the score. There are four triggers allowed:<br><mark style="color:purple;"><code>Player Touches</code></mark>- Updates the score when the player touches the selected object<br><mark style="color:purple;"><code>Other Object Touches</code></mark> - Updates the score when another object touches the selected object<br><mark style="color:purple;"><code>Clicked</code></mark> - Updates the score when you click the selected object<br><mark style="color:purple;"><code>Broadcast Listened</code></mark> - Updates the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be updated based on the trigger event happening</td></tr><tr><td>Operator </td><td>Define the operator to multiply by. Four operators are allowed - <mark style="color:purple;"><code>Add,</code></mark> <mark style="color:purple;"><code>Subtract</code></mark>, <mark style="color:purple;"><code>Multiply</code></mark> and <mark style="color:purple;"><code>Divide</code></mark></td></tr><tr><td>Update By</td><td>Define an integer (positive or negative) to change the score by. For instance, if the operator is <mark style="color:purple;"><code>Add</code></mark> and Update By is given the value 10, then the score is increased by 10 every time the trigger event defined in Update When happens</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

