# Carryable

A carriable is a logic template that, when attached to a game asset, enables the player to carry it.&#x20;

To add the Carryable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Carryable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

To add the Carryable behavior to an asset, follow these steps:

{% embed url="https://www.loom.com/share/f67cf9873a584bebae54cf5c94e1ffda?sid=f7158aca-4596-4c1d-b54d-f1bd5877fddb" %}
Carriable and deposit
{% endembed %}

1. Select the asset you wish to apply the Carriable behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose Carriable.

You can customize the below-mentioned parameters according to your requirements:

| Parameter          | Description                                                                                                                                                                                                                             |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Group              | You can group the carryables in different categories using this dropdown.                                                                                                                                                               |
| Carry on           | <p></p><p>Choose when the item is “carried”, using the dropdown:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Play SFX           | Choose a short chime to play when item is collected                                                                                                                                                                                     |
| Play VFX           | Choose a small visual effect to play when item is collected                                                                                                                                                                             |
| Size of carriable  |                                                                                                                                                                                                                                         |
| Score Group        | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                                            |
| Lerp               |                                                                                                                                                                                                                                         |
| Lerp Time          |                                                                                                                                                                                                                                         |
| Score              | Enter a numerical score value to update when collected.                                                                                                                                                                                 |
| IsMultiLevel       | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                                       |
| Broadcast          | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                           |

Configure the player setting for the carryable behaviour:

1. Navigate to the essentials tab from the builder menu.
2. Select the PlayerControllerDrawer from the builder panel. this would open the inspector panel
3. Navigate to carryable properties section in the inspector pannel.

| Parameter             | Description                                                                  |
| --------------------- | ---------------------------------------------------------------------------- |
| Locator for cariable  | set the position of the carryable on the player using the record button      |
| Limit                 | the number of carryables can be limited using this field                     |
| Stack offset          | Using this option you can set the position of the carrible around the player |

### Accessing the Carryable Template using T\#

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.
