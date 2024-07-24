# Multi-Point Move

{% embed url="https://www.loom.com/share/23fb779803cd444d98f47df7d8fbebee?sid=1c587de4-6710-40e9-b0fb-a7fad42e52b4" %}
Interpolate Points&#x20;
{% endembed %}



Multi-Point Move is a logic template that allows you to instruct an Asset to follow a path made up of several points once its Start Event occurs. This path can be straight lines or curves between the points, giving you many choices for how the Asset moves.

The Asset can automatically turn to make sure a specific side always points towards the path, just like how our face turns to the direction we are moving.

To add the Multi-Point Move logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Multi-Point Move under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="204">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Move On</td><td>This is a dropdown from where you need select any one of the following Start Events for Interpolate Points to begin executing: <br> <br>1. When the behavior  when the game starts: Select "Game Start"<br>2. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>3. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>4. When the player touches the currently selected Asset: Select "Player Touchers"<br>5. When the Asset is clicked: Select "On Click" </td></tr><tr><td>Points</td><td>This helps you specify the coordinates of the multiple points through which the Asset will move in a path. Click the + button to add points and - button to remove an existing point</td></tr><tr><td>Speed</td><td>This is an input field where you can enter a number that represents the speed of Asset movement</td></tr><tr><td>Turn To Points</td><td>This toggle button ensures that only one side of the Asset always faces forward. When activated, it adjusts the Asset's orientation to maintain this specific direction during movement.</td></tr><tr><td>Delay at Point</td><td>This field lets you set a delay in seconds. During this delay, the Asset will not move. After the time passes, it will start moving again.</td></tr><tr><td>Loop</td><td>This toggle button, when activated, enables the movement to repeat continuously</td></tr><tr><td>Is Curve</td><td>This toggle button alters the Asset's trajectory between points to follow a curved path instead of a linear one.</td></tr><tr><td>Interpolate Types</td><td><p></p><p>This dropdown lets you pick how the object moves:</p><ul><li>For forward movement only, select <strong>One Direction</strong></li><li>For back-and-forth movement, select <strong>Ping Pong</strong></li></ul></td></tr><tr><td>Broadcast Type &#x26; Broadcast Signal</td><td><p>The Broadcast Signal option allows you to create a game signal that other can act as the Start Event for other behavior blocks to execute. You can choose "Game Win", "Game Lose", or create your own custom signal. For a custom signal, you must select "Custom" from the dropdown and enter a name in the input field.<br><br>The Broadcast Type dropdown lets you specify when the broadcast signal will be sent. There are three options to choose from:</p><ul><li>If you want no broadcast to be sent, Select Never</li><li>If you want to send a broadcast after finishing one whole movement from start to end, select End </li><li>If you want to send the broadcast signal every time the object pauses , select At Every Pause</li></ul></td></tr></tbody></table>

### Accessing the Multi Point Move Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper- [MoveBetweenPointsTemplate ](../../coding-using-t/t-logic-template-wrappers.md#movebetweenpointstemplate)
