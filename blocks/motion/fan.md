# Fan

**Category**: 🚀 Motion

![fan thumbnail](https://portal.patchxr.io/block-thumbnails/fan.png)

## Description

Pushes physical objects forward when they pass through the wind area in front of the fan.

Acts as a wind generator: any physical block (made dynamic with Make Physical) crossing the area in front of the fan is pushed along the fan's forward direction. The Wind Strength dial controls the target speed reached by objects (up to ~40 m/s); objects already moving faster than the target along the fan's axis are not affected.

Resize the fan with the Size handle to expand or shrink the affected area. Combine with Marble Spawner for a quick stream of physical particles, or with Thruster and Field for richer aerodynamic setups.

## Related Wiki Pages

[physics](/patching/physics)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Wind Strength | Jolt Input | Patchable input for the Wind Strength dial. Higher values push objects to faster target speeds. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Size | Interactible | Drag this handle to resize the fan and expand or shrink the wind area in front of it (max size: 2 m). |
| Wind Strength | Dial | Sets the wind strength. Higher values push objects to faster target speeds (up to ~40 m/s). |

## Related Blocks

- [thruster](/blocks/motion/thruster)
- [field](/blocks/motion/field)
- [make_physical](/blocks/motion/make_physical)
- [gravity](/blocks/motion/gravity)
- [m_spawner](/blocks/motion/m_spawner)
- [wing](/blocks/motion/wing)

---