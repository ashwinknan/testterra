---
description: Enables Multiplayer experiences
---

# Multiplayer

The `Multiplayer` static class acts as a gateway for managing multiplayer sessions in Terra Studio. It encapsulates access to the underlying MultiplayerSession and exposes a suite of properties, events, and methods for common multiplayer operations such as session management, property updates, remote procedure calls (RPCs), object spawning/destroying, and ownership handling. All operations are safely forwarded to the active session, if available. ​\
\
To activate this, you first need to make sure that the Multiplayer Mode is enabled in Game Settings and you have set the correct number of players required for your multiplayer game.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-04-01 at 3.56.12 PM.png" alt="" width="336"><figcaption><p>GameSettings has multipler enabled and Max Players set</p></figcaption></figure>

***

#### Properties and Events in MultiplayerServices

| Type     | Name                   | Description                                                                                                                      |
| -------- | ---------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Property | **IsClient**           | Returns `true` if the current session is running as a client; otherwise `false`.                                                 |
| Property | **IsHost**             | Returns `true` if the current session is running as a host; otherwise `false`.                                                   |
| Property | **IsConnected**        | Returns `true` if the multiplayer session is currently connected; otherwise `false`.                                             |
| Event    | **OnGameStarted**      | Triggered when the game has started. Internally, this subscribes to the session's `OnGameHasStarted` event.                      |
| Event    | **OnHostDisconnected** | Triggered when the host disconnects. Internally, this relays the session's `OnServerDisconnected` event.                         |
| Event    | **OnRpcReceived**      | Triggered when an RPC is received. Provides the RPC key and arguments via an `Action<string, object[]>`.                         |
| Event    | **OnPropertyModified** | Triggered when a multiplayer property is modified. Provides the property name and its new value via an `Action<string, object>`. |

***

#### Methods in MultiplayerServices

| Type   | Name                | Description                                                                                                                                                          |
| ------ | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Method | **StartSession**    | Begins the multiplayer session and accepts a callback (`Action<bool>`) to notify when the session starts successfully.                                               |
| Method | **LeaveRoom**       | Exits the current multiplayer room.                                                                                                                                  |
| Method | **GetMyPlayer**     | Retrieves information about the current player. Returns an `IReadonlyMemberInfo` for the calling client.                                                             |
| Method | **GetAllPlayers**   | Returns a list (`IReadOnlyList<IReadonlyMemberInfo>`) of all players currently in the session.                                                                       |
| Method | **UpdateProperty**  | Updates a multiplayer property by name with the specified value.                                                                                                     |
| Method | **GetProperty**     | Retrieves the value of a multiplayer property by its name. Returns `default` if the session is not available.                                                        |
| Method | **SendRPC**         | Sends a remote procedure call to specified targets using a given key and arguments. Accepts a `SendTarget`, an optional list of client IDs, and variadic parameters. |
| Method | **Spawn**           | Spawns a GameObject into the session at specified local transforms. Accepts a reference GameObject and one or more `Vector3` positions.                              |
| Method | **Destroy**         | Destroys a GameObject within the multiplayer session.                                                                                                                |
| Method | **TrySetParent**    | Attempts to set the parent transform for a given GameObject. Returns `true` if successful; otherwise, `false`.                                                       |
| Method | **TryRemoveParent** | Attempts to remove the parent transform from a GameObject. Returns `true` if successful; otherwise, `false`.                                                         |
| Method | **IsOwner**         | Checks if the current client is the owner of the specified GameObject. Returns `true` if the client is the owner; otherwise, `false`.                                |
| Method | **ChangeOwnership** | Transfers ownership of a GameObject to another player. Overloaded to accept either a client ID (`ulong`) or a username (`string`).                                   |
