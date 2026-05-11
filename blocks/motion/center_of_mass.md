# Center Of Mass

**Category**: 🚀 Motion

![center_of_mass thumbnail](https://portal.patchxr.io/block-thumbnails/center_of_mass.png)

## Description

Override the physical center of mass of the group it is placed in. Use to balance vehicles, change the rotation pivot, or stabilize physics objects.

Place this block inside a physical group (built with Make Physical, Joint, Piston, etc.) and the group's rigidbody will use the position of this block as its center of mass instead of the auto-computed barycenter.

This affects how forces (gravity, thrust, hits, fields) make the group rotate. Pulling the center of mass low helps keep cars and boats upright, while moving it far from the geometry creates exaggerated tipping behavior, useful for tumbling props or wobbly characters.

## Related Wiki Pages

[physics](/patching/physics)

## Related Blocks

- [make_physical](/blocks/motion/make_physical)
- [make_physical_extra](/blocks/motion/make_physical_extra)
- [thruster](/blocks/motion/thruster)
- [field](/blocks/motion/field)
- [wing](/blocks/motion/wing)
- [joint](/blocks/motion/joint)
- [piston](/blocks/motion/piston)

---