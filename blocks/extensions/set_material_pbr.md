# Set Material Pbr

**Category**: 🧩 Extensions

## Description

Sub-block of the Set Material block. Holds the PBR shader editor panel with all material parameters (color, metallic, roughness, normal, emission, transparency, displacement...).

Is the panel from Set Material. This sub-block is automatically spawned and attached to a Set Material block when it is created and is not meant to be spawned on its own. It exposes the full set of PBR shader parameters, grouped in collapsible sections (Color, Glossiness, Transparency, Metallic, Bump/Normal, Emission, Rim Light, Displacement, Grunginess), each with toggles, sliders, color pickers and texture/selector tag inputs. Changing the material preset, color, or any parameter on this panel updates the material currently applied by the parent Set Material block.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Grunginess | Jolt Input with Slider | Controls the amount of grunge/dirt overlay applied on top of the material. 0 disables the effect. |
| Glossiness | Jolt Input with Slider | Controls the surface smoothness. 0 = fully rough (matte), 1 = fully smooth (mirror-like). |
| Metallic | Jolt Input with Slider | Controls how metallic the surface looks. 0 = dielectric (plastic, wood, fabric), 1 = pure metal. |
| Paint | Jolt Input with Slider | Blends the Color Multiply / Color Tint over the underlying material color. 0 = base material color, 1 = full custom color. |
| Normal Map Strength | Jolt Input with Slider | Strength of the normal map effect. 0 = flat, higher values exaggerate the surface bumps. |
| Fresnel Intensity | Jolt Input with Slider | Brightness of the Fresnel rim light effect. |
| Fresnel Power | Jolt Input with Slider | Sharpness/falloff of the Fresnel rim light. Higher values concentrate the effect on the edges only. |
| Grungy Paint Threshold | Jolt Input with Slider | Threshold above which the grunge paint becomes visible. Adjusts how much of the surface is covered by the grunge effect. |
| Bump Culling | Jolt Input with Slider | Controls back-face culling for normal-mapped surfaces. Useful for thin/double-sided geometry. |
| Displacement Strength | Jolt Input with Slider | Amount of vertex displacement applied. 0 = no displacement, higher values push vertices further along the displacement direction. |
| Displacement Offset | Jolt Input with Slider | Constant offset added to the displacement value. Useful to push the surface in or out uniformly. |
| Texture Tiling X | Jolt Input with Slider | Horizontal tiling (scale) of the main texture. Higher values repeat the texture more times along U. |
| Texture Tiling Y | Jolt Input with Slider | Vertical tiling (scale) of the main texture. Higher values repeat the texture more times along V. |
| Texture Offset X | Jolt Input with Slider | Horizontal offset (translation) of the main texture along U. |
| Texture Offset Y | Jolt Input with Slider | Vertical offset (translation) of the main texture along V. |
| Main Texture | Tag Input | Main color texture (albedo). Connect a Snapshot block or any texture-providing block to use a custom image. |
| Glossiness Texture | Tag Input | Glossiness/Smoothness map. Brighter pixels are smoother, darker pixels are rougher. |
| Metallic Texture | Tag Input | Metallic map. Brighter pixels are metallic, darker pixels are dielectric. |
| Normal Map Texture | Tag Input | Normal map (tangent-space) used to add surface detail without extra geometry. |
| Emission Texture | Tag Input | Emission map. Pixel values are multiplied by Emission Color to define which parts of the surface glow. |
| Displacement Texture | Tag Input | Texture driving vertex displacement. Used as a height map by default, or as an XYZ direction map when 'Displace RGB to XYZ' is enabled. |
| Transparency Texture | Tag Input | Texture providing transparency through its alpha channel. Used when 'Alpha From Custom Texture' is enabled. |
| Transparency | Jolt Input with Slider | Material transparency. 0 = fully opaque, 1 = fully transparent. Activates the transparent render queue when greater than 0. |
| Displacement Selector | Tag Input | Drag to a block to use its transform as the reference orientation for RGB-to-XYZ displacement (forward, up, position). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Use Tint Method | Toggle Button | When enabled, the main texture is tinted by replacing its 'Original Color' with the 'Color Tint' (preserves luminosity). When disabled, colors are applied multiplicatively via 'Color Multiply'. |
| Invert Glossiness | Toggle Button | Inverts the glossiness/smoothness value (smooth becomes rough and vice-versa). Useful when a texture authored as roughness needs to be used as smoothness. |
| Displace RGB to XYZ | Toggle Button | When enabled, the RGB channels of the displacement texture are interpreted as a 3D direction (XYZ) instead of just a height value. Combine with a Displacement Selector to set the reference orientation. |
| Displacement Shadows | Toggle Button | When enabled, the displaced surface casts and receives shadows correctly. Disable for a cheaper, shadow-less displacement. |
| Alpha From Custom Texture | Toggle Button | When enabled, the material's transparency is read from the dedicated Transparency Texture input (alpha channel). |
| Alpha From Main Texture | Toggle Button | When enabled, the material's transparency is read from the alpha channel of the Main Texture (Color Texture). |
| Passthrough | Toggle Button | Turns the material into a passthrough cutout: the surface becomes a window into the real world (Mixed Reality / AR). |
| Use Color Texture | Toggle Button | Enables the main color texture. When off, only the flat color values are used. |
| Use Glossiness Texture | Toggle Button | Enables the glossiness/smoothness texture. When off, the Glossiness slider value is used uniformly across the surface. |
| Use Metallic Texture | Toggle Button | Enables the metallic texture. When off, the Metallic slider value is used uniformly across the surface. |
| Triplanar Mapping | Toggle Button | When enabled, the main texture is projected from three world-space axes instead of using UV coordinates. Avoids stretching on irregular meshes. |
| Use Normal Map | Toggle Button | Enables the normal map texture to add surface detail (bumps) without extra geometry. |
| Use Emission Texture | Toggle Button | Enables the emission texture so emission can vary across the surface instead of being a flat color. |
| Use Displacement Texture | Toggle Button | Enables vertex displacement driven by a texture (height map or RGB direction map). Subdivision of the target mesh affects the result quality. |
| Use Fresnel Rim Light | Toggle Button | Enables a fake Fresnel effect that brightens the silhouette of the object based on the view angle, blending between Fresnel Color 1 and Fresnel Color 2. |
| Color Multiply | Interactible | Color multiplied with the underlying material color. White leaves the surface unchanged. Used when 'Use Tint Method' is OFF. |
| Color Tint | Interactible | Tint color applied on top of the texture, replacing the 'Original Color'. Used when 'Use Tint Method' is ON. |
| Original Color | Interactible | Reference color in the texture that will be replaced by 'Color Tint' (when Use Tint Method is enabled). Pick the dominant color of the texture for best results. |
| Emission Color | Interactible | Emissive (self-lit) color of the material. Brightness above 1 is supported via HDR for bloom-friendly emission. |
| Fresnel Color 1 | Interactible | Inner color of the Fresnel rim light, visible when looking straight at the surface. |
| Fresnel Color 2 | Interactible | Outer color of the Fresnel rim light, visible at grazing angles (silhouette). |
| Grunginess Color | Interactible | Color of the grunge/dirt overlay applied when Grunginess is greater than 0. |
| Color Section | Toggle Button | Expand/collapse the Color section (Color Multiply, Color Tint, Paint). |
| Grunginess Section | Toggle Button | Expand/collapse the Grunginess section (Grunginess amount, Grungy Paint Threshold, Grunginess Color). |
| Color Texture Section | Toggle Button | Expand/collapse the Color Texture section (Main Texture, Triplanar, Tiling/Offset, Use Tint Method, Original Color). |
| Glossiness Section | Toggle Button | Expand/collapse the Glossiness section (Glossiness amount, Glossiness Texture, Invert Glossiness). |
| Transparency Section | Toggle Button | Expand/collapse the Transparency section (Transparency amount, alpha sources, Passthrough, Transparency Texture). |
| Metallic Section | Toggle Button | Expand/collapse the Metallic section (Metallic amount, Metallic Texture). |
| Normal Map Section | Toggle Button | Expand/collapse the Bump / Normal Map section (Normal Map Texture, Strength, Culling). |
| Emission Section | Toggle Button | Expand/collapse the Emission section (Emission Color, Emission Texture). |
| Rim Light Section | Toggle Button | Expand/collapse the Rim Light (Fresnel) section (Fresnel Intensity, Power, Color 1, Color 2). |
| Displacement Section | Toggle Button | Expand/collapse the Displacement (Inflate) section (Displacement Texture, Strength, Offset, Selector, RGB-to-XYZ, Shadows). |

## Related Blocks

- [set_material](/blocks/visual/set_material)
- [material_brush](/blocks/visual/material_brush)

## Tags

DoNotInclude

---