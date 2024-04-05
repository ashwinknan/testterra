# How to Upgrade Using An Asset

This section describes how you can level up a player's property by upgrading it when he collects a specific `collectable`.

At the moment, only Magnetic Property's magnetic range can be enhanced. More properties that can be upgraded are being added by our team.

We will be discussing how to increase the magnetic range of the player with level up.

* First, we'll add items on the plane that the player can gather by applying magnetic force. Cube has been utilized, and the Collectable behavior has been implemented. Every time the player collides with the`Collectable`, the primary score will rise by 50. However, we want the player to use **magnetic force to retrieve it from a distance**. We'll address this again later.

<figure><img src="../../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

* Now you will see a `Main Score_GameScore group` in the essentials panel which keeps track of the **Main score** of the game.
* Using the Main Toolbar, add the `Level Upgrader`. The Level Upgrader is a highly useful tool that helps in tracking parameters and allows us to specify what will happen when a level is advanced. In the essentials panel, `Level Upgrader` is displayed as `Level Mapper.`
* A Level Mapper Inspector Panel will appear on the right side of the scene when you click on Level Mapper in the essentials panel. Define each parameter in the inspector panel. These features are described here.
* To give you a brief overview of these parameters

<table><thead><tr><th width="428">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Group</code></mark></td><td>Group acts as a tracker of the parameter that will change after the level-up.</td></tr><tr><td><mark style="color:blue;"><code>Cost Type</code></mark></td><td>This defines what will act as a source of cost for the player to attain level up. It can either be a Resource or carryable</td></tr><tr><td><mark style="color:blue;"><code>Resource Tag</code></mark></td><td>This defines which group of the above-mentioned cost type will be used to attain level up. </td></tr></tbody></table>

* Here we have mentioned `magnet_level` as **group**, `Resource` as **Cost Type**, and `Main Score`(Ref to Main Score\_GameScore group) as the **Resource Tag**.

<figure><img src="../../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

* Navigate to `Magnetic Properties` by selecting the Player Controller Drawer in Essentials. Establish the Magnets Range's initial value and choose the `IsMultiLevel` checkbox. As a result, the property can advance to a higher level. Following this, a Group drop-down menu will appear beneath IsMultiLevel. From the selection menu choose the `magnet_level` (we created this in Level Mapper) group.

<figure><img src="../../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

* Now back to **Level Mapper** and define value and currency. You can read about these parameters here. To give you a brief overview of what these parameters do:&#x20;

| Property                                    | Description                                                                                                                                                                                               |
| ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Value`</mark>    | The number present in value acts as the upgraded value to the property (here magnetic range) after level up. **Eg: As we have mentioned 5 in value, the magnetic range will update to 5 after level up.** |
| <mark style="color:blue;">`Currency`</mark> | The amount mentioned in currency is deducted from the resource tag upon achieving level-up. **Eg: Here 50 will be deducted from the main score after level up**.                                          |

<figure><img src="../../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

* Now create an **object that will help in leveling up the player**; that is, a level-up will occur when the player interacts with this object. We have used Prism.
* Attach the object with the `level-up template`. This template explains how the player will advance in level. A player has multiple options for leveling up. Define when there will be a level-up from the available options in the inspector panel for the level-up tag, we have kept it as `when the player touches`. Include the `manager group` as well which is `magnet_level`.

<figure><img src="../../../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

* For the magnetic force to collect cube Collectables. Set the attribute `Collect When` to `InMagnetRange`.

<figure><img src="../../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

* We have completed setting up the level-up. The player will collide with the prism to **update** the magnetic range.

