# Modify Carryable

The Modify Carryable Logic Template allows you to modify the number of carryables carried. &#x20;

To add the Modify Carryable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Modify Carryable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Modify When`</mark>    | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br><br>1. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Play VFX`</mark>       | Choose a small visual effect to play on the execution                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Play SFX`</mark>       | Choose a sound effect to play on the execution                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Haptics`</mark>        | Select Haptics from a dropdown                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Modifier Group`</mark> | Select a which carryable needs to be modified                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <mark style="color:blue;">`Execute Always`</mark> | Toggle to Specify if this always needs to be executed                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Modifier`</mark>       | Select a modifier to the carriable - Add, Subtract, Multiply                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| <mark style="color:blue;">`Modify By`</mark>      | Amount / Value to be modified by                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Accessing the Modify Carryable Template using T\#

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.
