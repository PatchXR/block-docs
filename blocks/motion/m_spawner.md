# Marble Spawner

**Category**: 🚀 Motion

![m_spawner thumbnail](https://portal.patchxr.io/block-thumbnails/m_spawner.png)

## Description

Spawns physical marbles when triggered. Initial velocity is controllable and the spawner's colour tints each marble.

Press the button (or send a jolt to Spawn Marble) to spawn a marble at the spawner's mouth, shooting downward along its local up axis at the configured speed. Recolour the spawner to set the spawned marble's colour. The Set Marble Speed input sets the velocity used for subsequent spawns. Multiplayer ownership of the spawned marbles can be configured via the inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set Marble Speed | Jolt Input with Dial | Initial speed given to the next spawned marble (m/s). |
| Spawn Marble | Jolt Input | Trigger a marble spawn. The jolt value is forwarded to the marble (available as its set value). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Button | Button | Press to spawn a marble. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Synced By | dropdown | Selects which player owns and synchronises the spawned marbles across the network (Room Master, Closest Player, or Everybody). |

## Related Blocks

- [block_spawn](/blocks/system/block_spawn)
- [block_remove](/blocks/system/block_remove)
- [thruster](/blocks/motion/thruster)
- [make_physical](/blocks/motion/make_physical)

---