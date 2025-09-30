---
description: >-
  Deploy any C# code update to 100% of players—without them downloading an app
  update
---

# 🔥 Hot Deploy Engine

<a href="https://flow.letsterra.com/" class="button primary">Visit Website</a>           <a href="https://cal.com/terra-demo/30min?overlayCalendar=true" class="button secondary">Schedule a demo</a>             <a href="../case-studies/case-study-when-config-tweaks-werent-enough.md" class="button primary">Read Case Study </a>

Hot Deploy Engine is your delivery system that ensures every improvement you make reaches all your players—including the 20-30% who normally never update their apps.

Not just server config tweaks. Real gameplay transformations:

* New progression systems
* Game mechanics & features
* Bug fixes & balance changes
* UI system changes
* Core feature transformations

**Hot Deploy is the delivery engine.** Every solution you build, every problem you solve—it reaches 100% of your players without app store friction.

{% hint style="info" %}
Hot Deploy Engine works on all Unity platforms and passes app store reviews:

* iOS App Store approval ✓
* Android Play Store approval ✓
* Console platforms ✓
* Desktop platforms ✓
{% endhint %}

### The Problem Hot Deploy Solves

When you ship traditional app updates:

* **20-30% of active players never download them**
* The rest take **2-3 weeks** to adopt
* Your retention features miss the at-risk players who need them most

{% hint style="warning" %}
Server configs reach everyone but only let you tweak parameters.
{% endhint %}

{% hint style="success" %}
**Hot Deploy changes this:** Ship actual C# code—real gameplay transformations—to all players without download barriers.
{% endhint %}

### How Hot Deploy Works

Hot Deploy Engine uses a system where your main app contains the "foundation" (Unity engine, core systems, UI frameworks), while your game logic runs as interpreted code that can be updated anytime.

### What Hot Deploy Engine Does

Hot Deploy Engine is designed to feel invisible during development. You work exactly like you always have—no special tools, no different workflow, no learning curve.

**Your existing setup just works.**

Open VS Code, make changes, hit F5 to test in Unity Play Mode. Hot Deploy Engine runs alongside your normal development without getting in the way.

Your breakpoints work. Your console logs appear normally. Your performance profiler shows accurate data.

**Debugging feels natural.**

When something breaks, you get the same stack traces you're used to. Whether the error comes from hot code or native code, Unity's console shows you exactly where the problem is.

Your favorite debugging techniques—Debug.Log, breakpoints, Unity's profiler—all work identically.

**No context switching.**

You don't need to think "is this hot code or native code?" while developing. Write your Mono Behaviours, test them in Play Mode, debug issues the same way.

The only difference is that when you're ready to ship, you can push these changes to live games instantly.

### Example Work Flow

**Simple example:** You want to change your shop price from $9.99 to $7.99 for a flash sale. With Hot Deploy Engine, you edit the code, click deploy, and players see the new price immediately—no app update required.

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



### Setting Up Your Project for Hot Deploy

{% stepper %}
{% step %}
#### Organizing Your Code

Split your project into two parts:

* **Base build:** Unity engine, core systems, third-party plugins, UI frameworks
* **Hot code:** Game logic, content systems, business rules, gameplay mechanics

Your hot code can reference anything in the base build, but not vice versa.
{% endstep %}

{% step %}
#### Working with Assets

**GameObjects and Components:** Your hot scripts can attach to any GameObject using `AddComponent()`. Scene objects work normally.

**Prefabs:** Keep prefabs with hot scripts in AssetBundles rather than scenes. This prevents Unity from breaking references during builds.

**ScriptableObjects:** Define ScriptableObjects in hot code and they work exactly like regular ones.
{% endstep %}

{% step %}
#### Handle Third Party Plugins

Keep plugins like `UniTask`, `DOTween`, or analytics SDKs in your base build. Reference them from hot code. Don't try to hot-load plugins themselves.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
### Things to remember

1.  #### Reflection

    Reflection works for common Unity operations like `GetType()` and `AddComponent()`, but complex reflection scenarios have \~50% success rate. Test your specific use cases.&#x20;
2.  #### Code Stripping

    IL2CPP may strip types that your hot code needs. Use Unity's link.xml to preserve required types, especially generic types like `List<YourClass>`.
3.  #### Hot Swapping

    To load fresh code, you must restart the app. Live code swapping during gameplay isn't supported.
4.  #### Plugin Restrictions

    Third-party plugins must stay in the base build. Trying to hot-load plugins often causes runtime errors.
{% endhint %}

### Memory and Performance Impact

#### App Size

* Hot Deploy Engine adds **\~175 KB** to your app
* Hot code reduces your app size since game logic is downloaded separately

{% hint style="success" %}
If you have 1MB+ of hot code, using Hot Deploy  will keep it smaller than bundling everything together in the base app
{% endhint %}

#### Runtime Memory

* Each hot assembly uses **\~5.5-6** times its file size in memory for metadata
* Each thread running hot code uses **\~1MB** additional memory
* Objects created by hot code use identical memory to native objects

#### Performance

* Most game logic runs at **70%-90%** of native speed
* UI updates, gameplay systems, and business logic show no noticeable difference

{% hint style="warning" %}
Intensive computation (physics, rendering, audio) should stay in the base build
{% endhint %}

### Multiple Assembly Support

Hot Deploy Engine supports organizing your hot code into multiple assemblies when your project grows complex. This is useful for large games where different teams work on separate systems (like UI, gameplay, and monetization) that need to update on different schedules.

Each assembly operates independently—you can update your UI code without touching gameplay systems, or push monetization changes without affecting core mechanics. This gives teams flexibility to ship features at their own pace.

{% hint style="info" %}
The trade-off is complexity: you need to manage dependencies between assemblies and ensure updates don't break compatibility with other systems. Most projects work well with a single assembly initially.
{% endhint %}

### Enterprise Features & Custom Development

These features aren't part of our standard product since every organization has different needs. We build them custom after understanding your specific requirements:

**Build Pipeline Integration:** We design CI/CD integrations that fit your existing workflow.

**Deployment Management:** We build hosting, versioning, and rollback systems based on your infrastructure needs.

**Security & Sign-in:** We create signing and encryption solutions that work with your security requirements.

**Enterprise Deployment:** We develop staged rollouts and multi-DLL systems tailored to your deployment processes.

{% hint style="info" %}
Contact us at the link below to discuss your specific needs. We'll design solutions that fit your exact requirements and timeline.
{% endhint %}

<p align="center"><a href="https://cal.com/terra-demo/30min?overlayCalendar=true" class="button primary">Contact us</a> </p>

