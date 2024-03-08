# Stop Player movement

Coming in contact with the StopPlayerMovement behavior will <mark style="color:purple;">`not allow the player to move`</mark> in the game environment. It locks the player in the current position.&#x20;

You can customize these parameters:

<table><thead><tr><th width="246">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start When</td><td><p>You can choose the trigger to activate the template</p><p>- When the game starts<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark><br>- When a different object touches the <mark style="color:yellow;">object</mark><br>- When you click on the <mark style="color:yellow;">object</mark></p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the player stops moving.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the player stops moving.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player stops moving again.</code></td></tr></tbody></table>



