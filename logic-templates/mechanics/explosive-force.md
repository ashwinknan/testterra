# Explosive Force

The Explosive Force Logic Template allows the attached object to exert a sudden explosive force or impulse on nearby objects within a certain radius.

To add the Explosive Force logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Explosive Force under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Explode When`</mark> | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Force`</mark>        | Specify the value of the force to be applied                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <mark style="color:blue;">`Radius`</mark>       | Specify the radius where the force is felt                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Explode SFX`</mark>  | Choose a short chime to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <mark style="color:blue;">`Explode VFX`</mark>  | Choose a small visual effect to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Broadcast`</mark>    | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after execution</p>                                                                                                                                                                                                                                                                                                                                                             |

### Accessing the Explosive Template using T\#

There are currently no available T# wrappers for this logic template&#x20;

