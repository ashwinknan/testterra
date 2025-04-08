# 🎧 Audio & SFX Support in Terra Studio

Terra Studio Pro provides full support for Unity's built-in audio and sound effect (SFX) systems. Developers can use Unity's native tools and APIs without any modifications, enabling seamless integration of sound into games and experiences.

Whether you're adding ambient background audio, triggering 3D spatialized sound effects, or managing dynamic music systems, all Unity SFX capabilities are available in Terra Studio out of the box. The only caveats apply to scripting via T#, where some advanced C# constructs may be limited.

***

## 🎤 Key Audio Features Fully Supported

### ✅ AudioSource Component

Attach to any GameObject to play audio clips.

* Supports looping, volume, pitch, stereo pan
* Play on awake, play via script
* Control playback: Play, Pause, Stop, UnPause

### ✅ AudioListener

Acts as the point of reference for all 3D spatialized audio.

* Usually attached to the player or camera
* Only one active AudioListener should exist in a scene at a time

### ✅ 3D Spatial Sound

* Distance-based attenuation
* Doppler effect
* Spread and rolloff controls
* Stereo panning and spatial blend

### ✅ AudioClip Support

* Import .mp3, .wav, .ogg, and .aiff files
* Use compressed or uncompressed formats
* Load via inspector or dynamically in code

### ✅ AudioMixer

* Create snapshots and blend between them
* Control group volumes and effects
* Route audio through mixer groups for complex setups

### ✅ Reverb Zones & Effects

* Use built-in audio filters such as:
  * Low Pass
  * High Pass
  * Reverb
  * Echo
  * Distortion
  * Chorus

### ✅ Triggering Audio via Animation or Events

* Add Audio Events to Animation Clips
* Trigger sound via scripts using animation or gameplay conditions

### ✅ Audio in UI

* Easily add sound feedback to buttons, sliders, and other interactive UI elements

### ✅ Audio via Scripting

Use Unity’s audio scripting APIs to:

* Play clips dynamically with `AudioSource.PlayOneShot()`
* Change clip, volume, or pitch at runtime
* Mute or unmute
* Transition between audio states

***

## 🪡 Usage Notes for Terra Studio

* All AudioSource, AudioListener, and AudioClip functionality is supported as-is.
* Use the Unity Editor to preview and adjust sounds just like any Unity project.
* Animation + sound combinations (e.g., footsteps) are fully supported.
* For multiplayer games, network synchronization of audio events may require additional logic using TerraNetBehaviour.
* For advanced audio setups, use AudioMixer assets to manage complexity.

***

## 🔹 Audio in T# Scripts

While Unity’s audio system is fully supported, ensure your scripting logic in T# follows supported syntax:

* Avoid async/await and lambdas if not compatible
* Prefer direct `GetComponent(typeof(AudioSource))` instead of generics
* Always check for null before playing audio

***

{% hint style="warning" %}
For scripting limitations and safe patterns, refer to [Key Differences between T# & C#](key-differences-t-versus-c.md)
{% endhint %}

.
