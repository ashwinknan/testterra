# Particle Effects (VFX)

### **ParticleEffectTemplate**

This template manages particle effects within the game, offering flexibility in configuration and event handling. Access it as follows:

#### Properties and Methods in ParticleEffectTemplate

<table data-header-hidden><thead><tr><th width="141"></th><th width="249"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>RepeatCount</td><td>Get or set the number of times the particle effect repeats.</td></tr><tr><td><strong>Property</strong></td><td>PlayForever</td><td>Get or set whether continuous playback is enabled.</td></tr><tr><td><strong>Property</strong></td><td>Duration</td><td>Get or set the duration of the particle effect.</td></tr><tr><td><strong>Property</strong></td><td>Delay</td><td>Get or set the delay between repetitions of the effect.</td></tr><tr><td><strong>Event</strong></td><td>OnParticlePlayingCompleted</td><td>Event triggered when the particle effect playback completes.</td></tr></tbody></table>

#### Usage Example for ParticleEffectTemplate

```csharp
public class ParticleEffectController : StudioBehavior
{
    void ConfigureParticleEffect()
    {
        // Accessing the wrapper
        ParticleEffectTemplate template = (GetTemplate(typeof(ParticleEffectTemplate)) as ParticleEffectTemplate);

        // Accessing and setting the RepeatCount property
        int repeatCount = template.RepeatCount; // Getting repeat count
        template.RepeatCount = 3; // Setting repeat count

        // Accessing and setting the PlayForever property
        bool playForever = template.PlayForever; // Getting continuous playback status
        template.PlayForever = true; // Enabling continuous playback

        // Accessing and setting the Duration property
        float duration = template.Duration; // Getting effect duration
        template.Duration = 5.0f; // Setting effect duration

        // Accessing and setting the Delay property
        int delay = template.Delay; // Getting delay value
        template.Delay = 2; // Setting delay between repetitions

        // Subscribing to events
        template.OnParticlePlayingCompleted += HandleParticlePlayingCompleted;

        // Unsubscribing from events
        template.OnParticlePlayingCompleted -= HandleParticlePlayingCompleted;
    }

    void HandleParticlePlayingCompleted()
    {
        // Handle logic when particle effect playback completes here
    }
}
```
