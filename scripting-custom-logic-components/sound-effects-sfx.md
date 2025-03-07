# Sound Effects (SFX)

### **SoundFxTemplate**

This template manages sound effects within the game, allowing customization of volume, pitch, 3D audio settings, distance ranges, looping capabilities, and pause/resume events.&#x20;

#### Properties and Methods in SoundFxTemplate

<table data-header-hidden><thead><tr><th width="151"></th><th width="155"></th><th></th></tr></thead><tbody><tr><td><strong>Type</strong></td><td><strong>Name</strong></td><td><strong>Description</strong></td></tr><tr><td><strong>Property</strong></td><td>Volume</td><td>Get or set the volume.</td></tr><tr><td><strong>Property</strong></td><td>Pitch</td><td>Get or set the pitch.</td></tr><tr><td><strong>Property</strong></td><td>Is3DAudio</td><td>Get or set whether the sound is 3D audio.</td></tr><tr><td><strong>Property</strong></td><td>MinDistance</td><td>Get or set the minimum distance for 3D audio.</td></tr><tr><td><strong>Property</strong></td><td>MaxDistance</td><td>Get or set the maximum distance for 3D audio.</td></tr><tr><td><strong>Property</strong></td><td>CanLoop</td><td>Get or set whether the sound can loop.</td></tr><tr><td><strong>Property</strong></td><td>PauseOn</td><td>Get or set the event on which the sound pauses.</td></tr><tr><td><strong>Property</strong></td><td>ResumeOn</td><td>Get or set the event on which the sound resumes.</td></tr><tr><td><strong>Event</strong></td><td>OnPaused</td><td>Event triggered when the sound is paused.</td></tr><tr><td><strong>Event</strong></td><td>OnResumed</td><td>Event triggered when the sound is resumed.</td></tr></tbody></table>

#### Usage Example for SoundFxTemplate

```csharp
public class SoundManager : StudioBehavior
{
    void ConfigureSound()
    {
        // Accessing the wrapper
        SoundFxTemplate template = (GetTemplate(typeof(SoundFxTemplate)) as SoundFxTemplate);

        // Accessing and setting properties
        float volume = template.Volume; // Getting volume
        template.Volume = 0.5f; // Setting volume

        float pitch = template.Pitch; // Getting pitch
        template.Pitch = 1.0f; // Setting pitch

        bool is3DAudio = template.Is3DAudio; // Checking if 3D audio
        template.Is3DAudio = true; // Enabling 3D audio

        float minDistance = template.MinDistance; // Getting minimum distance
        template.MinDistance = 1.0f; // Setting minimum distance

        float maxDistance = template.MaxDistance; // Getting maximum distance
        template.MaxDistance = 50.0f; // Setting maximum distance

        bool canLoop = template.CanLoop; // Checking if looping
        template.CanLoop = true; // Enabling looping

        string pauseOn = template.PauseOn; // Getting pause event
        template.PauseOn = "PlayerDeath"; // Setting pause event

        string resumeOn = template.ResumeOn; // Getting resume event
        template.ResumeOn = "PlayerRespawn"; // Setting resume event

        // Subscribing to events
        template.OnPaused += OnSoundPaused;
        template.OnResumed += OnSoundResumed;

        // Unsubscribing from events
        template.OnPaused -= OnSoundPaused;
        template.OnResumed -= OnSoundResumed;
    }

    void OnSoundPaused()
    {
        // Your code here
    }

    void OnSoundResumed()
    {
        // Your code here
    }
}
```
