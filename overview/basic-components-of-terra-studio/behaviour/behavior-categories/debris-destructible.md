# Debris Destructible

The Debris Destructible Behavior template is used to destroy objects within the game environment. Upon destruction, this template generates `debris` or `remains associated` with the destroyed object.&#x20;

You can customize the destruction process by specifying various parameters, such as <mark style="color:purple;">the force with which the debris will be propelled in the opposite direction</mark>, the <mark style="color:purple;">amount of delay</mark> before the debris is generated, and other relevant factors.

The debris produced by the destruction is defined using the Debris Behavior Template. So both the templates, Debris Destructible and Debris go together.

This creates a dynamic and immersive destruction sequence adding a layer of realism and immersion to the game world.

To add this behavior template:

<mark style="color:yellow;">Step 1</mark>: Select the object that will be destroyed.

<mark style="color:yellow;">Step 2</mark>: Click Add Behavior in the Inspector Panel and Choose Debris Destructible.

<mark style="color:yellow;">Step 3</mark>: You can customize the behaviour according to your requirements:

<table><thead><tr><th width="291">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the object.</p><p>- When a different object touches the object having the template<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player collides with the <mark style="color:yellow;">object</mark><br>- When the object is <mark style="color:yellow;">clicked</mark></p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the object is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the object is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the object is destroyed.</code></td></tr><tr><td>Add Delay</td><td>This adds a delay between the destruction and the trigger action in seconds.</td></tr><tr><td>Debris Group</td><td>This defines the debris that is the aftermath of destruction. The group is defined in the Debris behavior template.</td></tr><tr><td>Debris Radius</td><td></td></tr><tr><td>Debris Quantity</td><td>This is the total number of debris objects that will appear after destruction.</td></tr><tr><td>User Physics</td><td>When the "User Physics" property is unchecked, debris flies and disappears, but when checked, debris rolls around its edges before disappearing.</td></tr><tr><td>Force</td><td>Define the force by which the debris will scatter on the plane</td></tr><tr><td>Destroy Time</td><td>The total duration for which the debris will be present on the scene</td></tr></tbody></table>

