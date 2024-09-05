# Editor UI

Once you [create a new project](dashboard.md#create-a-new-game) or [open an existing project](dashboard.md#continue-editing-an-existing-game), you will be taken to the editor for the game.&#x20;

## Overview of Editor UI &#x20;

<figure><img src="../.gitbook/assets/Screenshot 2024-07-05 at 6.23.27 PM.png" alt=""><figcaption><p>This is the screen you'll see when you first enter Terra Studio</p></figcaption></figure>

<table><thead><tr><th width="243">Editor UI Feature</th><th>Description</th></tr></thead><tbody><tr><td><a href="editor-ui.md#quick-access-menu">Quick Access Menu</a></td><td>Located at the top of the workspace, the Main Toolbar helps you transition between edit and play modes.</td></tr><tr><td><a href="editor-ui.md#inspector-panel">Inspector Panel</a></td><td>Located on the right, the Inspector Panel is hidden by default. It opens up a customization panel for any item selected in Layers, Essentials, SFX or Particles</td></tr><tr><td><a href="editor-ui.md#main-toolbar">Main Toolbar</a></td><td>Located at the top of the editor interface, the Main Toolbar helps you transition between edit and play modes.</td></tr><tr><td><p></p><p><a href="editor-ui.md#camera-toolbar">Camera Toolbar</a></p></td><td>Located in the bottom of the screen, it allows you to view your game from multiple angles. </td></tr><tr><td><a href="editor-ui.md#support-chatbot">Support Chatbot</a></td><td>Located in the bottom right, you get direct access to the Terra Team is available via the Support Chat. </td></tr><tr><td><a href="editor-ui.md#asset-gizmo">Asset Gizmo</a></td><td>Gizmo next to any selected asset that helps you move rotate and scale assets</td></tr></tbody></table>

## Quick Access Menu

The Quick Access Menu is  equipped with all the necessary elements for game creation. Once you select any category from the Quick Access Menu, an expanded panel displays details and actions relevant to the selected item.&#x20;

The Quick Access Menu features eight tabs:

<table><thead><tr><th width="239">Quick Access Menu Tab</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:green;"><code>Assets</code></mark></td><td>This tab is used for adding and managing game assets. It opens the Terra Asset Library with over 150,000 3D assets. You can hover over an asset to see its name and polygon count. A search bar at the top allows you to find specific assets by name.</td></tr><tr><td><mark style="color:green;"><code>Layers</code></mark></td><td>Lists all Assets, Particles, and SFX added to the scene in a hierarchical format. Includes default items like Player, Ground, and Light. This tab allows you to organize and duplicate assets across different layers.</td></tr><tr><td><mark style="color:green;"><code>Essentials</code></mark></td><td>Displays characteristics of the game environment, such as the game timer, health, Game Main Score Tracker</td></tr><tr><td><mark style="color:green;"><code>Particles</code></mark></td><td>Offers special effects like smoke, fire, or sparkles. Clicking this tab shows a library of available Particle Effects (VFX), which you can preview and search.</td></tr><tr><td><mark style="color:green;"><code>SFX</code></mark></td><td>Provides a selection of sound effects to enhance the game's auditory experience. You can preview sounds by clicking the play button and search for specific SFX using the search bar.</td></tr><tr><td><mark style="color:green;"><code>Scenes</code></mark></td><td>Enables setting up and customizing the game's environments and levels. Shows a list of available scenes and environments. You can add a new scene by clicking the + button, entering a name, and clicking OK.</td></tr><tr><td><mark style="color:green;"><code>Logic</code></mark></td><td>Displays a list of pre-built logic templates that can be dragged and dropped onto an asset.</td></tr><tr><td><mark style="color:green;"><code>Scripts</code></mark></td><td>Displays a list of all scripts added to objects in the scene. Use the + button in this tab to add a new script.</td></tr></tbody></table>

## Inspector Panel&#x20;

The Inspector Panel is available only in Advanced Mode. Enable the Advanced Mode toggle located at the top right of the editor to access it. Once enabled, the right hand side of the editor interface houses the inspector panel for any feature whose properties can be customized.&#x20;

Some features whose properties are customizable and appear in the inspector panel are as follows:&#x20;

* Any component added to the Essentials tab in the Quick Access Menu.
* Sound Effect and Particle game objects.
* Transform, Rotate, and Scale fields of asset game objects.
* Material Properties of asset game objects.
* Logic Components attached to asset game objects.
* Scripts & Object Variables attached to asset game objects.

## Main Toolbar

This is the `Main Toolbar` that has various functionalities to it. These functionalities range from system properties to publishing the game on Studio. All these have been explained below:

<table><thead><tr><th width="220">Main Toolbar Feature</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>File Import</code></mark></td><td>Helps you import custom packages directly into your project. Primarily used to import readymade script packages for your game.</td></tr><tr><td><mark style="color:blue;"><code>Primitives</code></mark></td><td>Contains a collection of primitive elements that can be used to customize an asset according to your needs. Some of these elements include: Cube, Cylinder, Sphere, and Light. This feature also includes the EditUI feature, which allows you to add Custom UI elements to your game.</td></tr><tr><td><mark style="color:blue;"><code>System Properties</code></mark></td><td>Provides various system properties for game customization. These include:<br>- <strong>Game Timer</strong>: Adds a timer to the game.<br>- <strong>Checkpoint</strong>: Adds a checkpoint in the game.<br>- <strong>Game Progress</strong><br>- <strong>Fake Player</strong><br>- <strong>Level Upgrader</strong>: Makes your game multilevel.<br>- <strong>Delete Game Prefs</strong></td></tr><tr><td><mark style="color:blue;"><code>Save</code></mark></td><td>Although the Studio autosaves your work locally, this feature allows you to save your progress on the cloud. Simply click on the Save icon to save your project to the cloud.</td></tr><tr><td><mark style="color:blue;"><code>Play</code></mark></td><td>Switches the scene to the gameplay mode of your project. Use this to check if everything is working as per your vision. Remember to save your game before entering the gameplay mode.</td></tr><tr><td><mark style="color:blue;"><code>Publish</code></mark></td><td>Sends your project for review. After passing standard procedures, your project will be live on the app within 2-4 days.</td></tr><tr><td><mark style="color:blue;"><code>Debug Panel</code></mark></td><td>Contains tools for accessing scripts and debugging errors in your code.</td></tr></tbody></table>

## Camera Toolbar

You can achieve different views of the scene using the camera control.

There are 6 different orientations provided to the user:

* **`Top`** - This allows you to view and edit the scene from the **top view** of the camera.
* **`Bottom`** - This allows you to view and edit the scene from the **bottom view** of the camera.
* **`Left`** - This allows you to view and edit the scene from the **left view** of the camera.
* **`Right`** - This allows you to view and edit the scene from the **right view** of the camera.
* **`Front`** - This allows you to view and edit the scene from the **front view** of the camera.
* **`Back`** - This allows you to view and edit the scene from the **back view** of the camera.

You have access to two different projections of the scene:

* **`Perspective Projection`**: This will help you to feel the depth of the elements while considering the distance with respect to the viewer.
* **`Orthographic Projection`**: This maintains the uniform scaling of the elements irrespective of the distance.

To achieve a custom orientation of the camera, you can right-press on your mouse, and move the cursor adjusting to your preferred orientation.

## Asset Gizmo

The Asset Gizmo is a small tool that appears next to any asset when you select it. This gizmo includes three icons: the `Move` icon, the `Rotate` icon, and the `Scale` icon.\
\
Selecting any of the three icons displays the X, Y, and Z axes. You can choose any axis to perform operations along it. Alternatively, click the center where all axes intersect to apply the operation uniformly along all axes.

## Support Chatbot

Here, you can ask technical questions and receive guidance, ensuring smooth progress in your game development journey. Simply type your query into the chat, and a Terra Team member will provide you with the assistance you need.

You can attach images in png format or  type responses as threads. &#x20;

## Keyboard Shortcuts

#### Keyboard Shortcuts for Mac

<table><thead><tr><th width="253">Mac Shortcut</th><th>Description</th></tr></thead><tbody><tr><td>Right Click + W</td><td>Pans the camera forward</td></tr><tr><td>Right Click + A</td><td>Pans the camera to the left</td></tr><tr><td>Right Click + S</td><td>Pans the camera backward</td></tr><tr><td>Right Click + D</td><td>Pans the camera to the right</td></tr><tr><td>Right Click + Q</td><td>Pans the camera downward</td></tr><tr><td>Right Click + E</td><td>Pans the camera upward</td></tr><tr><td>Right Click + Mouse</td><td>Hold down right mouse button while moving the mouse to change the camera orientation.</td></tr><tr><td>Mouse Wheel Scroll Up</td><td>Scroll the mouse wheel up to zoom in.</td></tr><tr><td>Mouse Wheel Scroll Down</td><td><p></p><p>Scroll the mouse wheel down to zoom out.</p></td></tr><tr><td>⌘ + D</td><td>Duplicates an object.</td></tr><tr><td>⌘ + Del</td><td>Deletes an object.</td></tr><tr><td>⇧</td><td>Hold down left shift to add or remove objects from selection.</td></tr><tr><td>⌘ + Z</td><td>Undoes the last editing step.</td></tr><tr><td>⇧ or ⌘ + Y</td><td>Redoes the last editing step.</td></tr><tr><td>⇧ or ⌘ + 5</td><td>Enable or disable snapping an object to another objects surface</td></tr></tbody></table>

#### Keyboard Shortcuts for Windows

<table><thead><tr><th width="253">Windows Shortcut</th><th>Description</th></tr></thead><tbody><tr><td>Right Click + W</td><td>Pans the camera forward</td></tr><tr><td>Right Click + A</td><td>Pans the camera to the left</td></tr><tr><td>Right Click + S</td><td>Pans the camera backward</td></tr><tr><td>Right Click + D</td><td>Pans the camera to the right</td></tr><tr><td>Right Click + Q</td><td>Pans the camera downward</td></tr><tr><td>Right Click + E</td><td>Pans the camera upward</td></tr><tr><td>Right Click + Mouse</td><td>Change camera orientation</td></tr><tr><td>Mouse Wheel Scroll Up</td><td>Zoom in.</td></tr><tr><td>Mouse Wheel Scroll Down</td><td><p></p><p>Zoom out.</p></td></tr><tr><td>Ctrl + D</td><td>Duplicates an object.</td></tr><tr><td>Ctrl + Del</td><td>Deletes an object.</td></tr><tr><td>Left Shift</td><td>Add or remove objects from selection.</td></tr><tr><td>Ctrl + Z</td><td>Undoes the last editing step.</td></tr><tr><td>Ctrl + Y</td><td>Redoes the last editing step.</td></tr><tr><td>Ctrl + 5</td><td>Enable or disable snapping an object to another objects surface</td></tr></tbody></table>
