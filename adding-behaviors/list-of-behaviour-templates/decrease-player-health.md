# Decrease Player Health

Decreasing the player's health on a particular interaction is common in games. The Decrease Player Health template triggers a <mark style="color:purple;">`decrease in player health`</mark> when certain events occur.

These events can be:

* When a player collides with a <mark style="color:purple;">`dangerous object`</mark>.
* An indirect event such as a <mark style="color:purple;">`game timer crossing a limit`</mark>, requiring the player to <mark style="color:purple;">`complete objectives quickly`</mark> or find ways to <mark style="color:purple;">`restore their health.`</mark>

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize the behavior:

<table><thead><tr><th width="291">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the template<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark></td></tr><tr><td>By Point</td><td>The player's health will decrease by the defined amount when the template is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health decreases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health decreases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent everytime the player health decreases.</code></td></tr></tbody></table>
