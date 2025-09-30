---
description: >-
  Turn design files into working pixel perfect Unity UI without manual
  reconstruction.
---

# 🖼 UI Builder

<a href="https://flow.letsterra.com/" class="button primary">Visit Website</a> <a href="https://cal.com/terra-demo/30min?overlayCalendar=true" class="button secondary">Schedule a demo</a>

UI Builder is a feature in Flow that eliminates the traditional friction between design and implementation. Instead of exporting assets, hand‑creating hierarchies, and re‑anchoring layouts, developers can paste a Figma share URL and within minutes receive a fully structured Unity Canvas with prefabs, anchors, and components. This saves hours of repetitive work and ensures design fidelity, making iteration cycles dramatically faster.

{% hint style="success" %}
**Powered by Hot Deploy:** Once generated, deploy your UI changes to 100% of players without them downloading an app update. Designer iterations reach everyone—including the  players who normally never update their apps.
{% endhint %}

### How UI Builder Works

{% stepper %}
{% step %}
**Enter Figma  URL**

Provide a Figma share URL in the Terra chat interface. The system validates the URL and prepares for processing.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 3.21.03 PM.png" alt="" width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
**Let UI Builder parse your file**

Terra selects the UI Builder Assistant and begins automated conversion. The assistant executes a 12-step process including fetching nodes, detecting UI elements, generating spritesheets, and creating prefabs.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 3.20.42 PM.png" alt="" width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
**Get completion confirmation & view the UI in Editor hierarchy**

Upon completion, receive confirmation and asset location details. Generated Unity assets are organized in the `Assets/ui/` folder.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 3.20.50 PM.png" alt="" width="375"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
**Extend UI further in the editor**

The generated Canvas is not static—it’s fully editable. Developers can:

* Attach scripts to prefabs (`AuthValidator`, `PurchaseHandler`).
* Wire up interactions via the Inspector (e.g., `Button.onClick`) using Wire Pilot
{% endstep %}
{% endstepper %}

### What UI Builder does behind the scenes

Building UI in Unity manually involves repetitive tasks that slow teams down. UI Builder automates these jobs so developers get a clean, ready-to-use environment.

#### Intelligent Hierarchy Naming

Instead of generic labels like `Group 12` or `Frame 5`, visual AI renames elements based on what they represent. A `Shop` frame becomes `Canvas/UIBuilder_Shop`, and a `Card List` group becomes a `VerticalLayoutGroup` with proper spacing.

<div><figure><img src="../.gitbook/assets/Screenshot 2025-08-22 at 9.36.16 PM.png" alt="" width="220"><figcaption><p>Poorly named hierarchy in Figma</p></figcaption></figure> <figure><img src="../.gitbook/assets/Screenshot 2025-08-22 at 9.35.03 PM.png" alt="" width="237"><figcaption><p>Hierarchy auto-rnamed</p></figcaption></figure></div>

#### Consistent Text Styling

Figma text styles automatically map to `TextMeshProUGUI` components with correct fonts, sizes, and colors. Missing fonts get flagged and fallbacks applied automatically, eliminating manual TMP setup.

#### Sprite Optimization

UI Builder deduplicates identical sprites and packs them into optimized `SpriteAtlas` files, reducing memory usage and draw calls compared to manual asset management.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-22 at 7.36.13 PM.png" alt=""><figcaption></figcaption></figure>

#### Prefab Generation

Creates Unity prefabs from Figma frames, enabling reusable components across your project instead of manually copying disconnected UI elements.

> **Note:** Advanced features like responsive anchoring and prefab variants are planned for future releases.

### Troubleshooting

<details>

<summary><strong>No prefabs generated?</strong></summary>

Make sure your Figma layers are marked as Components before importing.

</details>

<details>

<summary><strong>Wrong fonts showing up?</strong></summary>

Import the missing TMP Font Asset and update **UI Builder Settings → Font Map**.

</details>

<details>

<summary><strong>Layout breaks when resizing?</strong></summary>

Manually adjust anchors in the `RectTransform`. Smart Anchors coming in v2.0.

</details>

<details>

<summary><strong>Duplicate or missing sprites?</strong></summary>

Clear cached atlases in `Project/UI/Assets` and re-import.

</details>

<details>

<summary>Scripts disappeared after re-import?</summary>

Current limitation - attach scripts at prefab roots as a workaround. Delta Imports will fix this in a future release.

</details>
