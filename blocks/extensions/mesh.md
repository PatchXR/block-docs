# Mesh

**Category**: 🧩 Extensions

## Description

Imports and displays custom 3D models (GLB, GLTF, OBJ) with options for animations, physics colliders, material appearance adjustments, and poseable bone controls.

The Mesh block allows you to bring your own 3D files into Patchworld. In addition to loading OBJ, GLB, and GLTF files, you can adjust material properties like metallic and gloss levels, enable color editing, and generate physics colliders. If your model has multiple sub-meshes or a skeleton structure, you can enable Movable Models or Movable Bones to make sub-parts independently grab-interactive and poseable in VR.

## Related Wiki Pages

[assets](/patching/assets) • [importing_3D_model](/patching/importing_3D_model)

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Load Animations | checkbox | Enable or disable loading animations embedded within the 3D model. |
| Movable Models | checkbox | Make individual sub-meshes of the 3D model separately grabbable and movable. |
| Movable Bones | checkbox | Expose animation bones as grabbable and movable parts to manually pose or animate the model. |
| Generate collider | checkbox | Generate a collision mesh for the model so physical blocks can interact or collide with it. |
| Metallic | slider | Adjust the metalness of the model's materials. Higher values make it look more metallic. |
| Gloss | slider | Adjust the glossiness/roughness of the model's materials. Higher values make it shinier and less rough. |
| Editable Color | checkbox | Allow coloring the model using the paint bucket tool or block color properties. |

## Related Blocks

- [image](/blocks/visual/image)
- [txt](/blocks/visual/txt)
- [shape](/blocks/visual/shape)
- [make_physical](/blocks/motion/make_physical)
- [set_material_pbr](/blocks/extensions/set_material_pbr)
- [set_material](/blocks/visual/set_material)
- [set_hittable](/blocks/motion/set_hittable)
- [set_blendshape](/blocks/visual/set_blendshape)
- [set_animation](/blocks/visual/set_animation)

## Tags

DoNotInclude

---