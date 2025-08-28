---
description: Your Unity project's automation copilot
---

# ⚡ Wirepilot

{% hint style="info" %}
Type: _“Add stamina as a resource, map it to HUD, hook into player actions, and balance regen for 30-minute sessions.”_

WirePilot will scaffold the system, connect the wiring, adjust design curves, and leave you with a working feature ready to polish.
{% endhint %}

**WirePilot** is Flow's intelligent automation system that eliminates tedious Unity wiring and accelerates feature development. Think of it as your always-on assistant that watches your project and automatically connects the dots between GameObjects, scripts, and other game elements.

### Feature Overview

Wirepilot transforms Unity from manual drag-and-drop wiring into a self-connecting development environment. It continuously monitors your project and intelligently suggests connections when you add new GameObjects, UI elements, or components.

**Core Benefits:**

* **Zero Manual Wiring** - No more dragging references in the Inspector
* **Context Aware smart detection** - Automatically identifies wiring opportunities
* **Safety First** - Always asks for confirmation before making changes
* **Error Prevention** - Eliminates dangling references and missing connections
* **Designer Friendly** - Non-programmers can extend systems safely

### How Wirepilot works

{% stepper %}
{% step %}
Automatic Detection

WirePilot runs silently in the background, watching for:

* New UI buttons, sliders, and input fields
* GameObjects with incomplete component setups
* Scripts with public methods that match UI patterns
* Common Unity patterns (pickups, triggers, managers)

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 12.24.44 PM.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Smart Analysis

When WirePilot detects something new, it analyzes your existing code to find the best connections:

* Matches button names to script methods (`StartGame` button → `StartGame()` method)
* Identifies common patterns (coins → score systems, health pickups → player health)
* Validates method signatures to ensure compatibility

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 12.28.49 PM.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Safe Confirmation

Before making any changes, WirePilot:

* Shows you exactly what it wants to connect
* Explains why the connection makes sense
* Waits for your approval before proceeding
* Lets you skip suggestions that aren't right



<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 12.27.48 PM.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Intelligent Wiring

Once approved, WirePilot automatically:

* Creates the appropriate connections
* Sets up event handlers and listeners
* Adds missing components when needed
* Tests connections to ensure they work

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 12.29.53 PM.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

### Example Use Cases&#x20;

#### **UI Button Wiring**

**What you do:** Add a button to your Canvas\
**What WirePilot does:**

* Detects the new button
* Finds matching methods in your scripts (`StartGame()`, `OpenSettings()`, etc.)
* Connects the button's onClick event automatically
* No inspector dragging required

**Example:**

```
Button: "Start Game Button" 
↓ WirePilot detects
↓ Finds: GameManager.StartGame()
↓ Suggests: Connect onClick → StartGame()
↓ You approve
✅ Fully wired and ready to test
```

#### **Pickup Item Setup**

**What you do:** Drop a coin GameObject into your scene\
**What WirePilot does:**

* Adds Collider and sets isTrigger = true
* Creates or connects pickup script
* Wires to your score/currency system
* Sets up particle effects and audio

**Example:**

```
GameObject: "Gold Coin"
↓ WirePilot detects
↓ Finds: ScoreManager.AddPoints()
↓ Suggests: Setup pickup → Add 10 points
↓ You approve  
✅ Functional pickup system ready
```

#### **Feature Scaffolding**

**What you do:** Ask for a new gameplay feature\
**What WirePilot does:**

* Creates necessary scripts and components
* Wires input handling and UI elements
* Connects to existing game systems
* Balances parameters for good gameplay

**Example:**

```
Request: "Add dash ability"
↓ WirePilot analyzes
↓ Creates: DashController script
↓ Wires: Input → Dash trigger
↓ Connects: UI cooldown indicator  
↓ Balances: Distance, cooldown, stamina cost
✅ Complete dash system ready
```

