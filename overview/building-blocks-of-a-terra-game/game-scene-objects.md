# Game Scene Objects

#### Game Scene Objects in Terra Studio

In Terra Studio, everything in the game scene that contributes to the immersive gameplay experience falls under the category of game scene objects. These are the elements that players can see, hear, or interact with during gameplay through the player's perspective. Terra Studio classifies these objects into four main categories:

* **Assets:** These are the visual elements, such as characters, items, and structures, that players can see and interact with in the game world.
* **SFX (Sound Effects):** These are the auditory elements that enhance the game's atmosphere and realism. They include sounds from characters, environments, and actions.
* **Particles:** These are small, graphical effects that simulate certain behaviors or natural elements, like smoke, fire, and magical effects, adding depth and realism to the game's visual presentation.
* **Environment:** This includes the broader setting or backdrop of the game scene, encompassing weather conditions, lighting, and landscape features, which sets the mood and context for the player's adventure.

## Assets

Assets are any 3D objects that can be added to the game scene. You can view all assets by selecting "Asset" from the Builder Menu. You will be shown a library of all assets and their preview in the Library view. You can perform the following actions with Assets:&#x20;

* **Add a Pre-made Asset**: To include a pre-made asset in your game, simply click on the desired asset, then drag and drop it into the game workspace. The In-Scene View will update to show a list of all assets you've added.
* **Search for a Pre-made Asset**: Use the Asset Search Bar to find specific assets by typing in their names.
* **Filter Assets**: Assets can be filtered by theme or category tags, making it easier to find what you need

{% hint style="info" %}
:dart:  Currently you cannot import your own assets in the game. However, in an upcoming release cycle, you'll be able to upload your assets directly into the Terra Studio environment, making it easier than ever to personalise your games and bring your unique visions to life.
{% endhint %}

The In-Scene view lists all the assets you've selected and placed in your game workspace, allowing for easy tracking and management of your game's 3D objects.

## SFX

To infuse your game with more life and interactivity, sound effects (SFX) play a crucial role. Here's how to seamlessly integrate them into your game.

### **Selecting and Adding SFX**

* **Navigate to the Builder Menu:** Start by opening the `Builder Menu` and selecting the `SFX` option. This will reveal a catalog of available sound effects suitable for your game's atmosphere and mechanics.
* **Preview SFX:** Ensure your selected SFX aligns with your vision by using the play button for a quick preview. This step is essential before setting the sound effect in stone.
* **Add Sound Effects:** Spot the `+` icon next to your chosen SFX in the list. Clicking this will automatically add the sound effect into your game's environment.

### **Configuring SFX**&#x20;

Once an SFX is added, it appears in the Layers panel. Here, you can select it to view all its configurable properties in the Inspector Panel. These are the properties you can change in the panel to get the sound effect you want :

* **SoundFx When:** Decide when the sound effect starts playing, either at the beginning of the game or after a specific event.
* **Pause on/Un-Pause on:** This dropdown helps you specify the game events (e.g., Game Start, Game Lose, Game Win) that will pause or resume the SFX playback.
* **Can Loop:** This toggle option for the sound to play continuously in a loop.
* **AudioPitch:** Alter the sound's pitch.
* **Volume of Sound:** Control the sound intensity at the source.
* **Is 3D Audio:** Toggle this to determine if the sound's properties change with distance, mimicking natural sound behavior. Disabling this makes the sound's volume and pitch uniform regardless of the listener's location relative to the source. Once this is active, you can specify
  * **Max Distance:** This helps you set the furthest distance at which the sound can be heard from its source.
  * **Minimum Distance:** Establishes the closest distance to the source needed to hear the sound, applicable when 3D audio is enabled.



## **Particles**

Particles allow you to add moving elements such as fire, beams, aurora lights etc within the game environment.&#x20;

### **Selecting and Adding Particles**

* **Selecting the Particles:** Start by opening the `Builder Menu` and selecting the Particles option. This will reveal a catalog of available particle effects with their preview suitable for your game's atmosphere and mechanics.
* **Adding Particles :**Click on the effect you want and drag and drop it to the desired location in your game.&#x20;

### Customizing Particle Properties

Once you have added a particle effect to the game, select it from the Layers Panel . You will be shown a list of customizable  properties in the Inspector Panel. &#x20;

* **Particle VFX When:** Determines the condition under which the particle effect is activated. It can be triggered by a broadcast event or at the game's start.
* **Pause/Un-Pause on:** This dropdown allows you to select specific game events that will pause or resume the Sound Effects (SFX) playback. Options include events like Game Start, Game Lose, and Game Win.
* **Duration:** Sets the duration for which the particle effect will remain visible.
* **Delay Between:** Defines the delay interval between consecutive appearances of the particle effect.
* **Repeat Forever:** This Toggle, If enabled, the particle Visual Effects (VFX) will repeat continuously throughout the game.
* **Repeat Count:** Specifies the number of times the particle VFX will repeat.

## Game Environment

This feature allows you to modify the visual aspects of the game's environment, providing tools to enhance the aesthetic and mood of your game world. You can alter the following&#x20;

<table><thead><tr><th width="271">Property</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Skybox</code></mark></td><td>Adjusts the game's backdrop to give the illusion of a more expansive space. It's like changing the scenery outside a window to make a room feel bigger.</td></tr><tr><td><mark style="color:blue;"><code>Bloom</code></mark></td><td>Creates a glow effect around bright areas in the game, simulating the way light behaves in the real world. It adds a touch of realism by making lights and reflections seem to spill over their boundaries.</td></tr><tr><td><mark style="color:blue;"><code>Vignette</code></mark></td><td>Applies a shading around the screen's edges, drawing the player's focus to the center. This effect can give your game a more dramatic and cinematic feel, as if you're peering through a lens.</td></tr><tr><td><mark style="color:blue;"><code>Fog</code></mark></td><td><p></p><p>Introduces a misty overlay that can be adjusted for depth and density, perfect for setting a mysterious or eerie atmosphere. It's like adding a thin veil over the game world that can make far-off objects seem obscured and distant.</p><p><br></p></td></tr></tbody></table>
