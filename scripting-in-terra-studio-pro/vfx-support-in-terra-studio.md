# 🔥 VFX Support in Terra Studio

Terra Studio Pro offers full compatibility with Unity's built-in Visual Effects (VFX) systems. Developers can use Unity's Particle System and Visual Effect Graph directly, with no changes required. This allows you to create everything from simple sparkles and smoke trails to complex GPU-accelerated visual simulations — just like in any standard Unity project.

The only restrictions are those related to T# scripting — all visual workflows and native components function as expected.

***

## 🚀 Supported VFX Systems

### ✅ Particle System (Shuriken)

Unity's classic and widely used particle system.

* Use for fire, smoke, sparks, dust, magic effects, trails, etc.
* Fully configurable in the Inspector
* Supports sub-emitters, color over lifetime, velocity over time, and more
* Burst emission, looping, and playback control
* Can be triggered via scripting or animation events

### ✅ Visual Effect Graph

For GPU-powered, node-based visual effects.

* Use for high-performance effects like lightning, explosions, volumetric fog, portals
* Supports custom attributes, events, and complex simulations
* Fully supported in Terra Studio Pro for advanced real-time visuals

***

## 🔹 Key Features Available

* **Play On Awake / Looping / One-Shot Effects**
* **World vs Local Simulation Space**
* **Collision & Triggering Events**
* **Material and Shader Integration (URP/HDRP Supported)**
* **VFX Event System (for Visual Effect Graph)**
* **Trails, Lights, Mesh Particles, and Custom Modules**
* **Scriptable Control of FX via Play(), Stop(), and SetFloat/Int/Vector methods**
* **Animator Integration** (trigger FX from keyframes)

***

## 🪡 Best Practices

* Use Particle System for simpler or mobile-friendly effects.
* Use Visual Effect Graph for GPU-powered, high-end effects.
* Organize FX into prefabs for reuse and easy reference.
* Control VFX dynamically with parameters exposed in scripts or VFX Graph Events.
* Use sub-emitters for chained effects (explosion -> smoke -> debris).

***

## 🔊 Triggering VFX via Scripts

VFX components like `ParticleSystem` and `VisualEffect` can be controlled via scripts:

* Start and stop effects manually
* Set visual parameters at runtime
* Use animation or input-driven triggers

{% hint style="warning" %}
In T#, make sure to use non-generic `GetComponent(typeof(...))` and avoid lambda expressions or unsupported C# constructs.
{% endhint %}

```
// Example: Trigger a particle system (T#-friendly)
ParticleSystem ps = gameObject.GetComponent(typeof(ParticleSystem)) as ParticleSystem;
if (ps != null) ps.Play();
```

***

{% hint style="info" %}
Use Unity's official workflows, tools, and assets without restriction. For ensure scripting integrations are compatible with T#, refer to the [Key Differences - T# Versus C#](key-differences-t-versus-c/).
{% endhint %}

