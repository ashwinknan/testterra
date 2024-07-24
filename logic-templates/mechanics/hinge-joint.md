# Hinge Joint

The Hinge Joint Logic Template allows you to make an asset rotate around a hinge joint to mimic the movement of a door.  &#x20;

To add the Hinge Joint logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Hinge Joint under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                        | Description                                                                            |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Axis`</mark>          | Helps specify the axis of rotation                                                     |
| <mark style="color:blue;">`Anchor`</mark>        | Specify the anchor point around which hinge movement must happen                       |
| <mark style="color:blue;">`Can Spin Back`</mark> | Toggle to specify if the object can spin back to original position after the rotation. |

### Accessing the Hinge JointTemplate using T\#

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

