---
description: >-
  The original had no replay value - players unlocked levels but every game felt
  identical. Here's how Hot Deploy Engine let us add a complete cue
  customization system that transformed player engagement
---

# Adding a Complex Progression System to a live game

## The Problem: No Replay Value

Our game launched with a simple progression model. Players used currency to unlock new levels, which led them to play their first game. When they unlocked the second level, they discovered the gameplay was identical - same cue, same mechanics, just a different table background

<figure><img src="../.gitbook/assets/Screenshot 2025-09-24 at 5.28.53 PM.png" alt="" width="563"><figcaption><p><em>Original home-screen had just a basic level unlock system with single cue</em></p></figcaption></figure>

&#x20;After trying a few matches, they had no reason to return because gameplay never changed. We needed to add depth to the game play

## The Solution -  Cue Shop Addition to the live build

We knew players needed more gameplay variety to keep returning. Our plan was to add a Cue Shop system where players could upgrade three key parameters that would change how each match played - Power for shot strength, Guidelines for aiming assistance, and Time for how long they could plan shots.

We first added the Cue Shop entry point to our existing homescreen

<figure><img src="../.gitbook/assets/Screenshot_2025-09-24-17-27-52-38_66566482b18a9126eac6423bd3f61898 (1).jpg" alt="" width="563"><figcaption><p>New Cue Shop added to home screen</p></figcaption></figure>

Users were repeatedly trying to click on the "cues" button displayed in-game. This confirmed our instinct was right. Players wanted cue customization. Then we created the full upgrade interface where players could customize their cue with different parameter combinations.

Then we rolled out the full upgrade interface where players could finally interact with cues and customize their gameplay experience.

<figure><img src="../.gitbook/assets/Screenshot_2025-09-24-17-28-01-76_66566482b18a9126eac6423bd3f61898.jpg" alt="" width="563"><figcaption><p>A complete cue system rolled out with  Power, Guidelines, Time options</p></figcaption></figure>



Players discovered the new progression system when they opened their game, transforming our simple level-unlock model into meaningful gameplay customization.

What seemed like a simple screen addition was actually a sophisticated technical implementation involving multiple interconnected systems. Our development team had to create entirely new user interface components while seamlessly integrating them with existing core gameplay mechanics - all delivered through Hot Deploy Engine without requiring any app updates.

## What was pushed using Hot Deploy&#x20;

Multiple scripts were modified—changes that would normally require a full app release. Three existing scripts were updated (**`HomescreenUI.cs, CueController.cs, GameManager.cs`**) and two new ones were added (**`CueShopUI.cs`** and **`CueDataManager.cs`**).&#x20;

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

Players who had been hoping for cue interaction discovered the new progression system when they opened their game, transforming our simple level-unlock model into the meaningful customization they had been seeking all along.

### The Impact

Players now had meaningful strategic choices and clear progression paths. The currency economy transformed from cosmetic unlocks to gameplay-affecting decisions. Hot Deploy Engine made this substantial system addition seamless for our entire live player base, dramatically improving retention and engagement.
