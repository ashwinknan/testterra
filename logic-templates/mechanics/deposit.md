# Deposit

The deposit logic template when applied to an asset, allows it to collect a specified carryable. The deposit logic template cannot work independently when there is no carryable in the scene

To add the Deposit logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Deposit under the header "Mechanics".
3. Drag and drop it onto the desired asset.

{% embed url="https://www.loom.com/share/f67cf9873a584bebae54cf5c94e1ffda?sid=f7158aca-4596-4c1d-b54d-f1bd5877fddb" %}
Carriable and deposit
{% endembed %}

You can customize the below-mentioned parameters according to your requirements:

| Parameter              | Description                                                                                                                                                                                                                                                                 |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Deposit when           | <p></p><p>Choose when the item is “Deposited”, using the dropdown:</p><ul><li>when player touches</li><li>when other object touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Take Resource          | select the group which wh                                                                                                                                                                                                                                                   |
| Persistent             | checking this box                                                                                                                                                                                                                                                           |
| Play SFX               | Choose a short chime to play when item is collected                                                                                                                                                                                                                         |
| Play VFX               | Choose a small visual effect to play when item is collected                                                                                                                                                                                                                 |
| Lerp                   |                                                                                                                                                                                                                                                                             |
| Lerp Time              |                                                                                                                                                                                                                                                                             |
| Cost type              |                                                                                                                                                                                                                                                                             |
| Size of carriable      |                                                                                                                                                                                                                                                                             |
| Score Group            | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                                                                                |
| Deposit rate           | You can set the rate at which the carriable will get deposited.                                                                                                                                                                                                             |
| Of Amount              |                                                                                                                                                                                                                                                                             |
| Score                  | Enter a numerical score value to update when collected.                                                                                                                                                                                                                     |
| IsMultiLevel           | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                                                                           |
| limit                  |                                                                                                                                                                                                                                                                             |
| Show Progress          |                                                                                                                                                                                                                                                                             |
| Is Ascending           |                                                                                                                                                                                                                                                                             |
| Broadcast              | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                                                               |
| Broadcast stack empty  |                                                                                                                                                                                                                                                                             |

### Accessing the Deposit Template using T\#

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

