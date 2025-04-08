# 🎨 Terra Studio UI Systems Overview

Terra Studio Pro fully supports all of Unity’s built-in UI systems. Developers can leverage the complete power of Unity’s UI architecture for both runtime and editor interfaces, without modification. All UI workflows, controls, and toolkits are available and compatible, with the only limitations being those imposed by the T# language runtime.

***

## 🧰 Supported UI Systems

### ✅ UI Toolkit

UI Toolkit is a **modern UI framework** designed for both Editor extensions and runtime UI. It’s based on familiar web concepts like HTML and CSS, offering a retained-mode system, high performance, and flexible styling.

#### **Features of UI Toolkit:**

* **Visual Tree**: A hierarchical representation of all UI elements.
* **Controls Library**: Standard components such as labels, buttons, sliders, toggles, and dropdowns.
* **Data Binding**: Connects data properties to UI elements.
* **Flexbox Layout Engine**: CSS-like layout system for responsive design.
* **Event System**: Handles clicks, touches, drags, and other interactions.
* **UI Renderer**: Built on Unity’s low-level graphics system.
* **Editor UI Support**: For custom Inspector and window development.
* **Runtime UI Support**: Fully usable in game runtime environments.

#### **Asset Types Used:**

* **UXML**: Markup-based structure, similar to HTML/XML.
* **USS**: Style definitions similar to CSS.

#### **Tools Included:**

* **UI Builder**: Visual interface to design UXML/USS assets.
* **UI Debugger**: Inspect and debug UI like a browser dev console.
* **UI Samples**: Prebuilt controls and templates for reference.

### ✅ Unity UI (uGUI)

The classic **GameObject-based UI system** designed for runtime user interfaces. Fully compatible with Terra Studio.

#### **Key Components:**

* `Canvas`: The root of all uGUI UI.
* `Text`, `Image`: For rendering visuals and text.
* `Button`, `Toggle`, `Slider`, `Dropdown`, `InputField`: Common interactive controls.
* `Panel`, `ScrollView`: For layout and grouping.

**Highlights:**

* Visual design via the Scene view
* Dynamic layout and anchoring
* Rich text rendering
* Built-in event system

## 🧪 Creating UI in Terra Studio

You can create UI using any of the following workflows:

#### 🧱 UI Builder

* Create a new UXML asset.
* Drag and drop controls (e.g., Label, Button, Toggle).
* Style with USS files.
* Load the Visual Tree in your scripts.

#### 📜 UXML

* Define structure in an XML-like format.
* Attach UXML to components via `VisualTreeAsset`.

#### 💻 T# Script

* Use `UnityEngine.UIElements` to define UI programmatically.
* Dynamically add elements like `Label`, `Button`, `Toggle`, etc., to your visual hierarchy.

{% hint style="warning" %}
While Unity UI systems are fully supported in Terra Studio Pro, code implementations should be adapted with T# limitations in mind. Refer to these differences and limitations [here](key-differences-t-versus-c.md)
{% endhint %}

