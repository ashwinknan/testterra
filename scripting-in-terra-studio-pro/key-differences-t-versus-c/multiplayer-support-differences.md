---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Multiplayer Support Differences

## 🌐  NetworkBehaviour versus TerraNetBehaviour

For multiplayer games, Unity devs might use `NetworkBehaviour` from Netcode for GameObjects or Mirror.  In Terra Studio, **you must use `TerraNetBehaviour` instead**. It provides network-specific lifecycle methods & wrappers for multiplayer-enabled GameObjects.

```csharp
public class MyMultiplayerScript : TerraNetBehaviour {
    public override void OnNetworkSpawn() {
        // Code for when object spawns on the network
    }

    public override void OnNetworkDespawn() {
        // Code for when object despawns from the network
    }
}
```
