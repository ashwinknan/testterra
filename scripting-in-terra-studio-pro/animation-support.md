---
icon: compass
---

# Animation Support



Terra Studio Pro provides complete support for Unity's animation system, including its most advanced runtime features. All built-in Unity animation functionalities are available without modification, empowering developers to integrate high-quality character and object animations using familiar tools and workflows. The only restrictions that apply are those defined by the T# scripting language.

***

## 🔄 What Animation Systems Are Supported?

Terra Studio supports **Unity's Mecanim animation system**, which includes:

* The Animator component
* Animation Clips (imported or created within Unity)
* Animator Controllers
* State Machines
* Blend Trees
* Avatars for humanoid rig retargeting
* Animation Events
* Animation Layers and Masks
* Root Motion
* Animation Curves
* Preview and Record Modes

Additionally, the **Legacy Animation system** is also supported for simpler use cases such as UI animations or lightweight scripted motion.

***

## 🔹 Key Features Available in Terra Studio

### ✅ Animator Controller

Organize animation clips into a state machine. Define transitions and parameters that control when and how animations play.

### ✅ Blend Trees

Blend between multiple animations based on input parameters. Ideal for walking/running/sprinting, directional movement, or character gestures.

### ✅ Humanoid Rig Retargeting

Use the Avatar system to retarget animations between different humanoid characters. Enables reuse of motion capture and third-party animation assets.

### ✅ Imported Animation Clips

Import animations from external tools such as:

* Autodesk Maya, 3ds Max
* Blender
* FBX and .anim files

Animations can be created from scratch or sliced from existing files.

### ✅ Animation Window

Use the built-in Animation window to:

* Record or preview keyframes
* Animate properties like transform, materials, colors, script variables
* Create new clips and edit them directly in the timeline

### ✅ State Machines

Design animation logic visually:

* Define states for idle, walk, run, jump, etc.
* Add transitions with conditions (e.g., speed > 0.5)
* Organize complex logic using sub-state machines

### ✅ Scriptable Animation Control

Control animations using C# or T# via APIs:

* Set parameters
* Trigger transitions
* Play/stop clips
* Evaluate normalized time, blending, etc.

### ✅ Root Motion Support

Optionally drive GameObject movement directly from animation motion curves.

### ✅ Rotation Interpolation

Use Euler, Quaternion, or Quaternion Euler (baked) interpolation for smooth transitions.

### ✅ Animation Layers & Masks

Separate upper/lower body animations or isolate limb movement using layer masks.

***

## 🪡 Usage Recommendations

* Use Mecanim for all new animation logic.
* Import FBX files from external  tools to speed up asset production.
* For humanoid rigs, always assign and configure an Avatar for optimal performance and retargeting.
* Use Blend Trees when animation variation depends on one or more continuous parameters.
* Manage multiple animation clips via Animator Controllers.
* Use the Animation window to keyframe motion and properties in-editor.

***

### 📌 Reminder

All Unity animation functionalities described above are fully available in Terra Studio Pro. Developers are encouraged to refer to Unity's official documentation for detailed usage patterns and editor workflows. Terra Studio ensures full runtime compatibility across the Animator pipeline.

{% hint style="warning" %}
For scripting and runtime control in animation, always consider the [Key Differences between T# & C#](key-differences-t-versus-c.md) to ensure that animation calls are T#-safe.
{% endhint %}





