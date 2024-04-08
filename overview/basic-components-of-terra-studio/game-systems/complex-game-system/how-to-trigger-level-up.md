# How To Trigger Level Up

This section explains how you can trigger any update in the game that could affect player attributes, the game's environment, or the functionality of other assets.

Broadcast is the primary element that will assist you in accomplishing the level up. It is an event that can be recognized by the assets. When this event occurs, the assets that need to be updated will pay close attention to it and take the appropriate action. You will understand this with the help of an example below.

The example describes an update in the assets score after the main score reaches 200.

* Add all the assets onto the plane that you wish to contribute to the main score. Cube has been utilized, and the Collectable behavior has been implemented. Every time the player collides with the`Collectable`, the primary score will rise by 50.&#x20;

<figure><img src="../../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

*

    * Now you will see a `Main Score_GameScore group` in the essentials panel which keeps track of the **Main score** of the game.
    * Using the Main Toolbar, add the `Level Upgrader`. The Level Upgrader is a highly useful tool that helps in tracking parameters and allows you to specify what will happen when a level is advanced. In the essentials panel, `Level Upgrader` is displayed as `Level Mapper.`
    * A Level Mapper Inspector Panel will appear on the right side of the scene when you click on Level Mapper in the essentials panel. Define each parameter in the inspector panel. These features are described here.
    * To give you a brief overview of these parameters

    <table><thead><tr><th width="304">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Group</code></mark></td><td>Group acts as a tracker of the parameter that will change after the level-up.</td></tr><tr><td><mark style="color:blue;"><code>Cost Type</code></mark></td><td>This defines what will act as a source of cost for the player to attain level up. It can either be a Resource or carryable</td></tr><tr><td><mark style="color:blue;"><code>Resource Tag</code></mark></td><td>This defines which group of the above-mentioned cost type will be used to attain level up. </td></tr></tbody></table>

<figure><img src="../../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* Define `update_score` (Custom) as G**roup**, `Resource` as **Cost Type**, and `Main Score`(Ref to Main Score\_GameScore group) as the **Resource Tag**.
* Navigate back to the Collectable template of Cube in the Inspector Panel. Choose the `IsMultiLevel` checkbox. As a result, the property can advance to a higher level. Following this, a Group drop-down menu will appear beneath IsMultiLevel. From the selection menu choose the update\_score (you created this in Level Mapper) group.

<figure><img src="../../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

* Now back to **Level Mapper** and define value and currency. You can read about these parameters here. To give you a brief overview of what these parameters do:&#x20;

| Property                                    | Description                                                                                                                                                                                                  |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <mark style="color:blue;">`Value`</mark>    | The number present in value acts as the upgraded value to the property (here value of each cube) after level up. **Eg: As we have mentioned 100 in value, thecube value will update to 100 after level up.** |
| <mark style="color:blue;">`Currency`</mark> | The amount mentioned in currency is deducted from the resource tag upon achieving level-up. **Eg: Here 50 will be deducted from the main score after level up**.                                             |

<figure><img src="../../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

* For the cubes to update their value when the main score reaches 200, you have to use the [`Broadcast feature`](broken-reference). As the cubes have to keep track of the main score, you have to add `Special Broadcast` to the Main Score group.
* Click on the Main Score Group in the Essential Builder Panel, this will open up the properties in the Inspector Panel. Now go to Special Broadcasts and define the parameters. You can read about the properties here.

<figure><img src="../../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

* We have used `At` as **Broadcast Type**, `200` as **Value** and `new_score(custom)` as **Broadcast**.
* Navigate back to any of the cube Collectables. Add a `Level Up` template to any one of the Collectables. Define the parameters. Use the `Broadcast Listened` option in `LevelUp When` to upgrade after a broadcast event.

<figure><img src="../../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* Here `Start On` has the **new\_score group** that was created in the Main Score group and the `Manager group` contains the **update\_score** group which was created in Level Mapper.
