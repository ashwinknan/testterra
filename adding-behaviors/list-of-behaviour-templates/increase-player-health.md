# Increase Player Health

The Increase Player Health behavior when triggered <mark style="color:purple;">`increases the health of the player`</mark>. The template can be triggered on various events. These events could be:

* The player collects coins, or other assets which contribute to increasing the health. These collectibles might be <mark style="color:purple;">`healing potions`</mark>, <mark style="color:purple;">`food`</mark> etc.

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize the behavior:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the template<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark></td></tr><tr><td>By Point</td><td>The player's health will increase by the defined amount when the template is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health increases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health increases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent everytime the player health increases.</code></td></tr></tbody></table>
