---
description: Push updates to players without a full app release
---

# 🔥 Hot Deploy Engine

Hot Deploy Engine is a runtime system that lets you deliver new C# code directly into a running Unity game — even one that players already have installed.

Unlike “hot reload” tools (which only speed up coding in the editor), Hot Load actually updates **production builds in players’ hands**. That means you can fix bugs, patch logic, or roll out new features instantly — without waiting for an app store review or forcing players to reinstall.

### Feature Overview

Hot Deploy Engine lets you modify C# scripts and instantly deploy those changes to running Unity builds—including live games already in players' hands. No rebuilds, no app store submissions, no player interruptions.

**Simple example:**

* **Change code:** Lower shop price from $9.99 to $7.99
* **Deploy instantly:** Changes go live immediately to running builds
* **Players see it now:** Updated pricing without app restart or reinstall

### Setting up Hot Deploy Engine

{% stepper %}
{% step %}
#### Open any script you wish to edit&#x20;

Let's say your script is as below&#x20;

```csharp
/*
 * Basic Unity shop manager with purchase button and $9.99 price display.
 * Handles button clicks and logs purchase events.
 */
 
using UnityEngine;
using UnityEngine.UI;

public class ShopManager : MonoBehaviour
{
    public Button purchaseButton;
    public Text priceText;

    void Start()
    {
        priceText.text = "$9.99";
        purchaseButton.onClick.AddListener(OnPurchaseClick);
    }

    void OnPurchaseClick()
    {
        Debug.Log("Purchase initiated");
        // Process purchase logic
    }
}
```

Make changes to any C# script in your project using your normal editor (VS Code, Visual Studio, etc.).

_What you do:_ Normal coding workflow—edit, save, continue working

<figure><img src="../.gitbook/assets/Screenshot 2025-08-22 at 6.06.14 PM.png" alt="" width="375"><figcaption><p>Your script - ShopManager.cs</p></figcaption></figure>
{% endstep %}

{% step %}
#### **Edit Your Script**

Hot Deploy Engine monitors your project and detects when scripts are modified.

```csharp
/*
 * Enhanced shop manager with discount features.
 * Adds 20% off label, reduces price to $7.99, and includes analytics tracking.
 */

using UnityEngine;
using UnityEngine.UI;

public class ShopManager : MonoBehaviour
{
    public Button purchaseButton;
    public Text priceText;
    public Text discountLabel;

    void Start()
    {
        priceText.text = "$7.99"; // Limited time offer!
        discountLabel.text = "20% OFF!";
        discountLabel.gameObject.SetActive(true);
        purchaseButton.onClick.AddListener(OnPurchaseClick);
    }

    void OnPurchaseClick()
    {
        Debug.Log("Discounted purchase initiated");
        Analytics.TrackEvent("discount_purchase_clicked");
        // Process discounted purchase logic
    }
}
```

_What you see in VS Code:_

* File marked as "Modified" in your editor
* Diff view showing exactly what changed (additions, modifications)
* "Changes detected - ready to deploy" status

<figure><img src="../.gitbook/assets/Screenshot 2025-08-22 at 6.06.03 PM.png" alt="" width="375"><figcaption><p>Revised ShopManager.cs</p></figcaption></figure>
{% endstep %}

{% step %}
#### Deploy in Editor with 1 click&#x20;

Hot Deploy prompts you to deploy changes to connected builds.

_What you see:_

* "Deploy UI Changes to Staging(iOS)?" dialog
* Choice to deploy now or later
* Clear indication of which build will be updated

<figure><img src="../.gitbook/assets/Screenshot 2025-09-01 at 5.47.37 PM.png" alt="" width="188"><figcaption></figcaption></figure>
{% endstep %}

{% step %}
#### **Live Updates Delivered to Users instantly**

Changes are pushed instantly to the running Unity build.

_What happens:_

* Running game receives update without restart
* Players see changes immediately
* No download, no interruption to gameplay

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 12.35.59 PM.png" alt="" width="300"><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

### How Hot Deploy Engine Works

* **Dynamic Assembly Injection:** Compiles managed code into loadable bytecode and injects it into Unity’s runtime domain.
* **Type and Symbol Management:** Prevents collisions and ensures new types align cleanly with existing ones.
* **State Preservation:** Updates logic while preserving current game state and memory.
* **Cross‑Platform Runtime:** Provides consistent APIs across Windows, macOS, Android, and iOS.

### 🔑 Key Difference from “Hot Reload”

* **Hot Reload** = a dev-time tool that helps you see changes instantly **while coding**.
* **Hot Deploy** = a runtime system that pushes code updates to **players in production builds**.

Think of hot reload as an **editor convenience**, and Hot Deploy as a **live deployment engine**.

***
