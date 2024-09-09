# T# Code Examples

The code examples illustrate how to write scripts in T#. You will notice that each of these scripts uses only available wrappers and avoids any Unity C# functionality that is not supported in T# as is stated in the section on [Unsupported Functionalities in T#](../scripting-custom-logic-components/unsupported-functionalities-in-t.md).

## Example 1: Skybox Rotation

```csharp
// The code below rotates the SkyBox per frame
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class SkyboxRotator : StudioBehaviour
{
    private float m_fRotationSpeed = 1.5f;
    private float m_fRotationValue;

    // Gets called every frame
    private void Update()
    {
        m_fRotationValue += m_fRotationSpeed * Time.deltaTime;
        RenderSettings.skybox.SetFloat("_Rotation", m_fRotationValue);
    }
}

```

## Example 2: Emission Color Change

```csharp
// Resets the emission Color to Black in Start
//Then changes the emission color of a tile back when the player touches it
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class TileColorChanger : StudioBehaviour
{
    private Color m_refEmissionColor;
    private bool m_bColorHasChanged;
    // Gets called at the start of the lifecycle of the GameObject
    private void Start()
    {
        m_refEmissionColor = (this.gameObject.GetComponent(typeof(Renderer)) as Renderer).material.GetColor("_EmissionColor");
        m_bColorHasChanged = false;
        (this.gameObject.GetComponent(typeof(Renderer)) as Renderer).material.SetColor("_EmissionColor", Color.black);
    }

    void OnTriggerEnter(Collider col)
    {
        if (!m_bColorHasChanged && StudioController.CheckIfController(col.gameObject) != null && m_refEmissionColor != null)
        {
            (this.gameObject.GetComponent(typeof(Renderer)) as Renderer).material.SetColor("_EmissionColor", m_refEmissionColor);
            m_bColorHasChanged = true;
        }
    }
}

```

## Example 3: Playing a Random VFX

```csharp
// Plays a random VFX when the player reaches a CheckPoint or when Dying
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using TerraStudio.TerraSharp.Collections;
using Unity.Mathematics;
using UnityEngine;

public class MiscStuff : StudioBehaviour
{
    private TerraList m_refDeathParticles;
    private TerraList m_refCheckpointCrossedParticles;

    // Gets called at the start of the lifecycle of the GameObject
    private void Start()
    {
        m_refCheckpointCrossedParticles = new TerraList();
        m_refDeathParticles = new TerraList();
        for (int i = 0; i < 10; i++)
        {
            GameObject toAdd = GetGameObjectVariable("GoodParticle" + i);
            if (toAdd != null)
            {
                m_refCheckpointCrossedParticles.Add(toAdd);
            }
            else
            {
                break;
            }
        }
        for (int i = 0; i < 10; i++)
        {
            GameObject toAdd = GetGameObjectVariable("KillParticle" + i);
            if (toAdd != null)
            {
                m_refDeathParticles.Add(toAdd);
            }
            else
            {
                break;
            }
        }
    }

    // Gets called whenever a broadcast is triggered by Behaviours or Other T# scripts
    public override void OnBroadcasted(string x)
    {
        Debug.Log("Broadcast received : " + x);
        if (string.Equals(x, "PlayerKilled"))
        {
            PlayRandomSadParticle();
        }
        else if (x.StartsWith("CP"))
        {
            PlayRandomHappyParticle();
        }   
    }

    private void PlayRandomSadParticle()
    {
        GameObject kill = Instantiate(GetRandomLoseParticle(), StudioController.GetMyController().GetLocator("headwear_l1_loc"));
        kill.transform.localPosition = new Vector3(0f, 0.01f, 0f);
        kill.transform.localScale *= 0.01f;
        StartCoroutine(DestroyAfter3Seconds(kill));
    }

    private void PlayRandomHappyParticle()
    {
        GameObject kill = Instantiate(GetRandomWinParticle(), StudioController.GetMyController().GetLocator("headwear_l1_loc"));
        kill.transform.localPosition = new Vector3(0f, 0.01f, 0f);
        kill.transform.localScale *= 0.01f;
        StartCoroutine(DestroyAfter3Seconds(kill));
    }

    private GameObject GetRandomWinParticle()
    {
        return m_refCheckpointCrossedParticles[UnityEngine.Random.Range(0, m_refCheckpointCrossedParticles.Count)] as GameObject;
    }

    private GameObject GetRandomLoseParticle()
    {
        return m_refDeathParticles[UnityEngine.Random.Range(0, m_refDeathParticles.Count)] as GameObject;
    }

    IEnumerator DestroyAfter3Seconds(GameObject a_refObj)
    {
        yield return new WaitForSeconds(3.0f);
        if (a_refObj != null)
        {
            Destroy(a_refObj);
        }
    }
}
```

## Example 4:  Camera & Light Change

```csharp
// On reaching the last checkpoint, Moves the Camera to victory pose
// It then changes the lights so the character looks good
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class EndCinematics : StudioBehaviour
{
    private GameObject m_refLight1;
    private GameObject m_refLight2;
    // Gets called at the start of the lifecycle of the GameObject
    private void Start()
    {
       m_refLight1 = GetGameObjectVariable("Light1");
       m_refLight2 = GetGameObjectVariable("Light2");
    }

    // Gets called whenever a broadcast is triggered by Behaviours or Other T# scripts
    public override void OnBroadcasted(string x)
    {
        if (string.Equals(x, "CP20"))
        {
            StartCoroutine(MoveCameraForWin());
        }
    }

    private IEnumerator MoveCameraForWin()
    {
        Transform cameraTarget = StudioController.GetMyController().GetControllerCamera().transform.parent;
        Vector3 currentPos = cameraTarget.localPosition;
        Vector3 posToGoTo = new Vector3(0f, -3.7f, -1.1f);

        Vector3 currentRot = cameraTarget.localEulerAngles;
        Vector3 rotToGoTo = new Vector3(74.709f, 180f, 0);

        m_refLight1.transform.localEulerAngles = new Vector3(m_refLight1.transform.localEulerAngles.x, m_refLight1.transform.localEulerAngles.y-180f, m_refLight1.transform.localEulerAngles.z);
        m_refLight2.transform.localEulerAngles = new Vector3(m_refLight2.transform.localEulerAngles.x, m_refLight2.transform.localEulerAngles.y-180f, m_refLight2.transform.localEulerAngles.z);

        float time = 0f;

        do
        {
            cameraTarget.localPosition = Vector3.Lerp(currentPos, posToGoTo, time);
            cameraTarget.localEulerAngles = Vector3.Lerp(currentRot, rotToGoTo, time);
            time += Time.deltaTime;
            yield return new WaitForEndOfFrame();
        } while (time <= 1f);
        cameraTarget.localPosition = posToGoTo;
        cameraTarget.localEulerAngles = rotToGoTo;
        Broadcast("DoTheDance");
    }
}


```
