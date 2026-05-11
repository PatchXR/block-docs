# Scene Watcher

**Category**: ⚙️ System

![scene_watcher thumbnail](https://portal.patchxr.io/block-thumbnails/scene_watcher.png)

## Description

Outputs collision events from marbles hitting your real-room furniture in Mixed Reality (walls, floor, ceiling, windows, doors, desks). Tune the bounciness per surface group with the three dials.

Requires Mixed Reality / scene understanding to be active so Patchworld knows where your physical walls/floor/ceiling and furniture are. For each marble collision the block emits the hit position (X/Y), velocity, and which surface category was hit. Walls, windows, doors and desks also emit an index so you can tell which specific wall or piece of furniture was struck.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Hit X | Jolt Output | Horizontal position (in local space) of the marble's impact point on the surface. |
| Hit Y | Jolt Output | Vertical position (in local space) of the marble's impact point on the surface. |
| Velocity | Jolt Output | Magnitude of the marble's relative velocity at the moment of impact. Useful as a 'hit force' value for sound or visual feedback. |
| Is floor | Jolt Output | Fires 1 when a marble hits the floor. |
| Is ceiling | Jolt Output | Fires 1 when a marble hits the ceiling. |
| Wall index | Jolt Output | Index of the wall face the marble just hit (each wall in the room has a different index). |
| Window index | Jolt Output | Index of the window frame the marble just hit. |
| Door index | Jolt Output | Index of the door frame the marble just hit. |
| Desk index | Jolt Output | Index of the desk the marble just hit. |
| Other side | Jolt Output | Fires when a marble hits any furniture category not covered by the dedicated outputs above. |
| Other index | Jolt Output | Index of the 'other' furniture item the marble just hit. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Grab area | Sub Part | Grab here to move the block around. |
| Floor/ceiling bounciness | Dial | How bouncy the floor and ceiling are for marbles hitting them. 0 = absorbs everything, 1 = bouncy. |
| Walls/windows/doors bounciness | Dial | How bouncy the walls, windows and door frames are for marbles hitting them. |
| Desks/others bounciness | Dial | How bouncy desks and other furniture are for marbles hitting them. |

## Related Blocks

- [passthrough](/blocks/visual/passthrough)
- [mixed_reality](/blocks/visual/mixed_reality)
- [block_watcher](/blocks/system/block_watcher)
- [m_spawner](/blocks/motion/m_spawner)
- [set_hittable](/blocks/motion/set_hittable)

---