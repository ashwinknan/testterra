# Available Wrappers

T# allows you to access behaviors and the variables in them through wrappers.

| Behavior                   | Wrapper                  | Accessible Variables of the Behavior                                                                                                             |
| -------------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Change Magnet              | ChangeMagnet             | <p>- StartOn<br>- MagnetRange<br>- FX Data</p>                                                                                                   |
| Change Material Properties | ChangeMaterialProperties | <p>- Material Data<br>- Lerp<br>- LerpTime<br>- FXData</p>                                                                                       |
| Change Player Speed        | ChangePlayerSpeed        | <p>- Start On<br>- Modifier<br>- Speed<br>- FXData</p>                                                                                           |
| Checkpoint                 | Checkpoint               | - FXData                                                                                                                                         |
| Collectable                | Collectable              | <p>- Start On<br>- Score Group<br>- Score<br>- Delay<br>- FXData</p>                                                                             |
| Delay Broadcast            | DelayBroadcast           | <p>- StartOn<br>- Delay</p>                                                                                                                      |
| Destroy On                 | DestroyOn                | <p>- StartOn<br>- Delay<br>- FX Data</p>                                                                                                         |
| Grow                       | Grow                     | <p>- StartOn<br>- ScaleFactor<br>- Speed<br>- FX Data<br>- Repeat</p>                                                                            |
| InGameTimer                | InGameTimer              | <p>- TimerType [Read Only]<br>- Time [Read Only]<br>- IsUIShown [Read only]<br>- BroadcastsList</p>                                              |
| InterpolatePoints          | InterpolatePoints        | <p>- StartOn<br>- Points<br>- Speed<br>- Turn to Points<br>- Delay at Point<br>- Loop<br>- Do Curve<br>- Loop Type<br>- FX Data</p>              |
| Jump Pad                   | JumpPad                  | <p>- Jump Force<br>- FX Data</p>                                                                                                                 |
| Light                      | Light                    | <p>- Light Color<br>- Light Intensity</p>                                                                                                        |
| Move To Player             | MoveToPlayer             | <p>- Start On<br>- Speed<br>- Offset<br>- Cancel Type<br>- FX Data</p>                                                                           |
| ParticleVfx                | ParticleVfx              | <p>- Start On<br>- Repeat Count<br>- Play Forever<br>- Duration<br>- Delay<br>- Pause On<br>- Resume On</p>                                      |
| Player Animation           | PlayerAnimationControl   | <p>- Start On<br>- Animation Name<br>- Reset Automatically</p>                                                                                   |
| Random Broadcast           | RandomBroadcast          | <p>- Start On<br>- Broadcast List</p>                                                                                                            |
| Reset Score                | ResetScore               | <p>- Start On<br>- Score Group</p>                                                                                                               |
| Reset Timer                | ResetTimer               | - Start On                                                                                                                                       |
| Respawn V2                 | RespawnV2                | <p>- Start On<br>- Animation to Play on Death<br>- Delay<br>- Respawn Type<br>- Lerp Time<br>- FX Data</p>                                       |
| Rotate Oscillation         | RotateOscillation        | <p>- Start On<br>- Rotation Axis<br>- Speed<br>- Degrees<br>- Direction<br>- Repeat Count<br>- Loop<br>- FX Data<br>- Stop On<br>- Resume On</p> |
| SetObjectPosition          | SetObjectPosition        | <p>- Start On<br>- Target Position<br>- FX Data</p>                                                                                              |
| Stop Animation             | StopAnimation            | - Start On                                                                                                                                       |
| Stop Player Movement       | StopPlayerMovement       | <p>- Start On<br>- FX Data<br>- Play Stun Anim<br>- Change to Stun Shader<br>- Restart On</p>                                                    |
| Teleport                   | Teleport                 | <p>- Start On<br>- Teleport Point<br>- FX Data</p>                                                                                               |
| Tick                       | Tick                     | <p>- Start On<br>- Stop On<br>- Resume On<br>- Broadcasts</p>                                                                                    |
| Update Score               | UpdateScore              | <p>- Start On<br>- Score Group<br>- Modifier<br>- Score Value</p>                                                                                |
| Update Timer               | UpdateTimer              | <p>- Start On<br>- Modifier<br>- Timer Value<br>- FX Data</p>                                                                                    |

