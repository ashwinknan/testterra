# Start Player Movement

When the player interacts with this behavior, their movement is no longer blocked and they are <mark style="color:purple;">`allowed to move in the environment`</mark>.

By default, the player is allowed to move. In cases where you want the player to start moving again after restricting the movement, this template comes in handy!

You can customize these parameters:

<table><thead><tr><th width="265">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start When</td><td><p>You can choose the trigger to activate the template</p><p>- When the game starts<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark><br>- When a different object touches the <mark style="color:yellow;">object</mark><br>- When you click on the <mark style="color:yellow;">object</mark></p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the player starts moving.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the player starts moving.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player starts moving again.</code></td></tr></tbody></table>

