# Animation

### **PlayAnimationTemplate**

This template facilitates the management and execution of animations within the game environment, offering seamless integration and customization options. Access it as follows:

#### Properties and Methods in PlayAnimationTemplate

<table data-header-hidden><thead><tr><th width="168"></th><th width="341"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>CurrentAnimation</td><td>Retrieve the currently playing animation.</td></tr><tr><td><strong>Property</strong></td><td>DefaultAnimation</td><td>Set the default animation for the component.</td></tr><tr><td><strong>Property</strong></td><td>AvailableAnimations</td><td>Access the list of available animations.</td></tr><tr><td><strong>Method</strong></td><td>PlayAnimationOverride</td><td>Play a specified animation with optional looping.</td></tr><tr><td><strong>Method</strong></td><td>StopAnimationOverride</td><td>Stop the currently playing animation.</td></tr><tr><td><strong>Event</strong></td><td>OnAnimationCompleted</td><td>Event triggered when an animation completes.</td></tr></tbody></table>

#### Usage Example for PlayAnimationTemplate

```csharp
public class AnimationController : StudioBehavior
{
    void ConfigureAnimation()
    {
        // Accessing the wrapper
        PlayAnimationTemplate template = (GetTemplate(typeof(PlayAnimationTemplate)) as PlayAnimationTemplate);

        // Accessing and setting the DefaultAnimation property
        string defaultAnimation = template.DefaultAnimation; // Getting default animation
        template.DefaultAnimation = "Idle"; // Setting default animation

        // Accessing AvailableAnimations property
        TerraList availableAnimations = template.AvailableAnimations; // Getting available animations

        // Controlling animation playback
        template.PlayAnimationOverride("Run", true); // Playing animation with looping
        template.StopAnimationOverride(); // Stopping the current animation

        // Subscribing to events
        template.OnAnimationCompleted += HandleAnimationCompleted;

        // Unsubscribing from events
        template.OnAnimationCompleted -= HandleAnimationCompleted;
    }

    void HandleAnimationCompleted(string animationName)
    {
        // Handle logic when animation completes here
    }
}

```

### **PlayerAnimationControlTemplate**

The PlayerAnimationControlTemplate class facilitates the control and management of player animations within the game environment. Access it as follows:

#### Properties and Methods in PlayerAnimationControlTemplate

<table data-header-hidden><thead><tr><th width="136"></th><th width="267"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>AnimationName</td><td>Get or set the current animation name.</td></tr><tr><td><strong>Property</strong></td><td>ResetAnimationAutomatically</td><td>Enable or disable automatic animation reset.</td></tr><tr><td><strong>Event</strong></td><td>OnAnimationCompleted</td><td>Event triggered when an animation completes.</td></tr></tbody></table>

#### Usage Example for PlayerAnimationControlTemplate

```csharp
public class PlayerAnimationController : StudioBehavior
{
    void ConfigurePlayerAnimation()
    {
        // Accessing the wrapper
        PlayerAnimationControlTemplate template = (GetTemplate(typeof(PlayerAnimationControlTemplate)) as PlayerAnimationControlTemplate);

        // Accessing and setting the AnimationName property
        string animationName = template.AnimationName; // Getting current animation name
        template.AnimationName = "Run"; // Setting animation name

        // Accessing and setting the ResetAnimationAutomatically property
        bool resetAutomatically = template.ResetAnimationAutomatically; // Getting auto-reset status
        template.ResetAnimationAutomatically = true; // Enabling automatic reset

        // Subscribing to events
        template.OnAnimationCompleted += HandleAnimationCompleted;

        // Unsubscribing from events
        template.OnAnimationCompleted -= HandleAnimationCompleted;
    }

    void HandleAnimationCompleted(bool success, string animationName)
    {
        // Handle logic when animation completes here
    }
}
```

### **PlayPlayersAnimationTemplate**

The PlayPlayersAnimationTemplate class is designed to manage and control player animations within your game environment. Access it as follows:

#### Properties and Methods in PlayPlayersAnimationTemplate

<table data-header-hidden><thead><tr><th width="130"></th><th width="263"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>AnimationName</td><td>Get or set the current animation name.</td></tr><tr><td><strong>Property</strong></td><td>ResetAnimationAutomatically</td><td>Enable or disable automatic animation reset.</td></tr></tbody></table>

#### Usage Example for PlayPlayersAnimationTemplate

```csharp
public class PlayerAnimationController : StudioBehavior
{
    void ConfigurePlayerAnimation()
    {
        // Accessing the wrapper
        PlayPlayersAnimationTemplate template = (GetTemplate(typeof(PlayPlayersAnimationTemplate)) as PlayPlayersAnimationTemplate);

        // Accessing and setting the AnimationName property
        string animationName = template.AnimationName; // Getting current animation name
        template.AnimationName = "Jump"; // Setting animation name

        // Accessing and setting the ResetAnimationAutomatically property
        bool resetAutomatically = template.ResetAnimationAutomatically; // Getting auto-reset status
        template.ResetAnimationAutomatically = true; // Enabling automatic reset
    }
}
```

### Animation Blending

The following code illustrates how to blend animations using T sharp. Here we are blending the walk and run animations on the zombieGo gameobject:

```csharp
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;
public class ZombieController : StudioBehaviour
{
GameObject zombieGo;
PlayAnimationTemplate playAnimation = null;
float blendFactor = 0f;
private string animA = "walk";
private string animB = "run";
private bool stopBlending = false;
// Gets called at the start of the lifecycle of the GameObject
private void Start()
{
    StopAllCoroutines();
    StartCoroutine(DelayedSetup());
}

private IEnumerator DelayedSetup()
{
    yield return null;

    zombieGo = GetGameObjectVariable("zombie");
    playAnimation = GetTemplate(zombieGo, typeof(PlayAnimationTemplate)) as PlayAnimationTemplate;

    yield return null;

    while (!playAnimation.IsPlayingDefault())
    {
        Debug.Log($"Waiting for default animation to load!");
        yield return null;
    }


    playAnimation.StopAnimationOverride();

    playAnimation.InitializeBlending(animA, WrapMode.Loop, animB, WrapMode.Loop);

    yield return new WaitForSeconds(5f);
    Debug.Log("stopping blending");
    stopBlending = true;

    yield return new WaitForSeconds(1f);
    Debug.Log("plaing death animation");

    playAnimation.PlayAnimationOverride("Death", false); //
    //playAnimation.StopBlendingAndReset();

}

int aState = 0;
//// Gets called every frame
private void Update()
{
    if (playAnimation == null) return;

    if (!stopBlending)
    {
        playAnimation.BlendAnimations(animA, animB, blendFactor);

        if (Input.GetKeyDown(KeyCode.F)) blendFactor = 0.1f;
        else if (Input.GetKeyDown(KeyCode.G)) blendFactor = 0.5f;
        else if (Input.GetKeyDown(KeyCode.H)) blendFactor = 1f;
        //Debug.Log(blendFactor);
    }
}

// Gets called whenever a broadcast is triggered by Behaviours or Other T# scripts
public override void OnBroadcasted(string x)
{

}
}
```

