---
description: >-
  How Hot Deploy helped reach 90% of players with real core gameplay changes &
  finally moved retention
---

# Case Study: When Config Tweaks Weren't Enough

### The Problem: Retention Metrics Weren't Responding

Our  8-ball pool game had stagnant early retention. Players were churning after unlocking the second level because they discovered gameplay was identical—same cue, same mechanics, just a different table background. After a few matches, they had no reason to return.

<figure><img src="../.gitbook/assets/Screenshot 2025-09-24 at 5.28.53 PM.png" alt="" width="563"><figcaption><p><em>Original home-screen had just a basic level unlock system with single cue</em></p></figcaption></figure>

**First attempt: Server config tweaks**

The team tried the standard approach—tweaking parameters through server configs:

* Adjusted currency rewards (+15%)
* Modified match difficulty curves
* Changed unlock timing for levels

**Result after 2 weeks:** Day 3 retention moved from baseline to +0.3 percentage points. Essentially flat.

{% hint style="warning" %}
**The diagnosis:** Parameter tweaks weren't addressing the core problem. Players needed actual gameplay depth, not slightly different numbers.
{% endhint %}

## The Solution: Build a new progression systems&#x20;

The team needed to add a Cue Shop—a full progression system where players could upgrade three parameters that would meaningfully change gameplay: **Power** (Shot strength multipliers), **Guidelines:** (Aiming assistance levels) and t**ime:** Shot planning duration

We first designed & pushed the Cue Shop entry point to our existing homescreen

<figure><img src="../.gitbook/assets/Screenshot_2025-09-24-17-27-52-38_66566482b18a9126eac6423bd3f61898 (1).jpg" alt="" width="563"><figcaption><p>New Cue Shop added to home screen</p></figcaption></figure>

Users were repeatedly trying to click on the "cues" button displayed in-game. This confirmed our instinct was right. Players wanted cue customization. Then we created the full upgrade interface where players could customize their cue with different parameter combinations.

Then we designed  the full upgrade interface where players could finally interact with cues and customize their gameplay experience.

<figure><img src="../.gitbook/assets/Screenshot_2025-09-24-17-28-01-76_66566482b18a9126eac6423bd3f61898.jpg" alt="" width="563"><figcaption><p>A complete cue system rolled out with  Power, Guidelines, Time options</p></figcaption></figure>

Players would discover the new progression system when they opened their game, transforming our simple level-unlock model into meaningful gameplay customization.

## But wait.. still need an app update?&#x20;

**The team's own data showed a problem:** Their historical app update adoption averaged 61% after 3 weeks. Nearly 40% of players—disproportionately casual and at-risk players—simply don't download updates.

**This meant even building the right solution wouldn't work.** The players who needed the Cue Shop most (those showing churn signals) were the least likely to ever experience it.

Enter Hot Deploy

## Hot Deploy pushed major features, without an app update&#x20;

This wasn't a config tweak. This required - New UI screens (`CueShopUI.cs`), New data management (`CueDataManager.cs`), Modified core gameplay (`CueController.cs`, `GameManager.cs`) & Modified home screen (`HomescreenUI.cs`)

Hot Deploy Engine deployed this entire system to players **without requiring any one to update their app.**&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-09-24 at 6.25.13 PM.png" alt="" width="321"><figcaption><p>Multiple Scripts added and modified in the Unity project</p></figcaption></figure>

Examples of real modifications:

{% code title="New Script Added: CueShopUI.cs" overflow="wrap" %}
```csharp
/// This entire shop interface was delivered via Hot Deploy Engine
public class CueShopUI : MonoBehaviour 
{
    [SerializeField] private Button powerUpgradeBtn;
    [SerializeField] private Button guidelineUpgradeBtn; 
    [SerializeField] private Button timeUpgradeBtn;
    
    private CueDataManager cueData;
    
    void Start() 
    {
        // Load player's current cue configuration
        cueData = CueDataManager.Instance;
        UpdateUI();
        
        // Wire up purchase buttons
        powerUpgradeBtn.onClick.AddListener(() => UpgradeParameter("power"));
        guidelineUpgradeBtn.onClick.AddListener(() => UpgradeParameter("guideline"));
        timeUpgradeBtn.onClick.AddListener(() => UpgradeParameter("time"));
    }
    
    private void UpgradeParameter(string paramType)
    {
        // Handle currency check and parameter upgrade
        if (cueData.CanAffordUpgrade(paramType))
        {
            cueData.UpgradeParameter(paramType);
            UpdateUI();
        }
    }
}
```
{% endcode %}

{% code title="Modified Script: CueController.cs" overflow="wrap" %}
```csharp
// Modified existing gameplay to use new cue parameters
public class CueController : MonoBehaviour 
{
    private CueStats currentCueStats;
    
    void Start()
    {
        // Load player's purchased cue configuration
        currentCueStats = CueDataManager.Instance.GetPlayerCueStats();
        ApplyCueParameters();
    }
    
    private void ApplyCueParameters()
    {
        // Apply power multiplier to shot strength
        shotPower *= currentCueStats.powerMultiplier;
        
        // Show/hide guideline based on upgrade level
        trajectoryLine.SetActive(currentCueStats.showGuidelines);
        
        // Adjust shot timing based on time parameter
        maxAimTime = currentCueStats.aimTimeSeconds;
    }
}
```
{% endcode %}

**Five scripts total.** Three modified, two new. All deployed to 100% of active players without requiring an app update.

Players opened their game the next day and discovered the Cue Shop system, transforming our simple level-unlock model into the meaningful customization they had been seeking all along.

### The Impact: The Missing 38% Made the Difference

Day 4 retention increased by **+3.3 percentage points**, moving the game from below to above platform average.

<figure><img src="../.gitbook/assets/Screenshot 2025-09-30 at 11.43.58 AM.png" alt=""><figcaption><p>Hot Deploy moved retention from below to above platform benchmark</p></figcaption></figure>

But the aggregate number masks where the real lift came from:

<figure><img src="../.gitbook/assets/Screenshot 2025-09-30 at 11.44.14 AM.png" alt=""><figcaption><p>Non-updaters responded 2.7x more strongly than app updaters</p></figcaption></figure>

**App updaters (62% of active players):** Day 4 retention lifted +2.3pp\
**Non-updaters (38% of active players):** Day 4 retention lifted +6.2pp

The segment that traditional app updates miss—players showing churn signals who hadn't updated in weeks—responded most strongly to the Cue Shop feature.

<figure><img src="../.gitbook/assets/Screenshot 2025-09-30 at 11.46.45 AM.png" alt=""><figcaption><p>Hot Deploy delivered 49% more retained players than traditional app updates]</p></figcaption></figure>

**Traditional app update:** 5,890 retained players (reached 62% of active base)\
**Hot Deploy:** 8,750 retained players (reached 90% of active base)\
**Result:** +2,860 retained players (+49%)

The 17,100 non-updaters who got the Cue Shop via Hot Deploy made the difference. They needed fresh gameplay and responded strongly—but traditional app updates would have never reached them.

The team built the right solution. Hot Deploy ensured the players who needed it most actually got it.

### What This Demonstrates

Config tweaks are useful for optimization but don't solve fundamental engagement problems—retention moves marginally at best.

Real system changes—new progression, new mechanics, meaningful depth—can significantly move retention metrics. But only if they reach the players who need them.

**The players who need retention features most are the ones least likely to download app updates.**

Hot Deploy solved the reach problem. The Cue Shop feature worked because it reached everyone, especially the 40% who were showing churn signals and wouldn't have updated their apps.

The team built the right solution. Hot Deploy ensured every player who needed it actually got it.

That's when retention moved.
