# Image

**Category**: 🎨 Visual

![image thumbnail](https://portal.patchxr.io/block-thumbnails/image.png)

## Description

Displays a .png/.jpg/.gif file with transparency support. Includes a spritesheet feature (set up via the Inspector) for playing animations.

Spawn an image from your library to display it in the world. Animated GIFs are loaded as a spritesheet automatically. You can also configure spritesheet playback manually for sprite-based animations: set rows, columns, frame count, and framerate in the inspector, then drive the current frame via the Frame ID jolt input or have it auto-play at the configured framerate. Use the 'Convert to 360 Image' inspector button to turn a regular image into an immersive 360 sky.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Frame ID (spritesheet) | Jolt Input | When using the spritesheet feature, this input controls which frame to display. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize handle | Draggable part | Drag to resize the image. Hidden when 'Lock Size' is enabled in the inspector. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock Size | checkbox | When enabled, the resize handle is disabled and the image size cannot be changed. |
| Filtering Quality | dropdown | Texture filtering quality. 'Pixelated' uses no mipmaps; 'Soft' adds bilinear filtering; 'Soft++' adds trilinear filtering. Higher quality looks smoother at a distance but uses more memory. |
| Transparency | checkbox | When enabled, transparent pixels in the source image are rendered as transparent. |
|    Occlusion Method | dropdown | How transparent pixels are handled. 'None' uses smooth alpha blending; 'Alpha Cut Off' uses a hard cutoff (good for opaque shapes with transparent edges); 'Multi Sampling' uses alpha-to-coverage for cleaner edges. |
| Blur (default:1) | slider | Mipmap LOD bias. Higher values increase blur by picking lower-resolution mip levels. |
| Spritesheet columns | integer | Number of columns in the spritesheet grid. |
| Spritesheet rows | integer | Number of rows in the spritesheet grid. |
| Spritesheet frames | integer | Total number of frames in the spritesheet (may be less than rows x columns if the grid isn't full). |
| Spritesheet Framerate | text_input | Playback rate in frames per second. Set to 0 to disable auto-play and drive the current frame via the Frame ID jolt input. |
| Spritesheet: One Shot | checkbox | When enabled, the spritesheet plays through once and then hides the image instead of looping. |
| Convert to 360 Image | button | Replaces this image with a 360_image block that uses the same source file, allowing the image to be displayed as an immersive skybox. |
| Set as current world cover | button | Uses this image as the cover/thumbnail for the current world. Only available to the world's owner or an editor. |
| Lock Size | checkbox | When enabled, the resize handle is disabled and the image size cannot be changed. |

## Related Blocks

- [txt](/blocks/visual/txt)
- [snapshot](/blocks/visual/snapshot)
- [magic_window](/blocks/visual/magic_window)

---