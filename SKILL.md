---
name: pixel-fantasy-assetgen
description: Generate or refine game art prompts and bitmap concepts for a cohesive modern low-resolution 2D pixel fantasy side-scroller. Use when the user asks for pixel-art game assets, side-scrolling fantasy characters, knights, mages, enemies, environments, tilesets, UI icons, palette sheets, sprite sheets, animation poses, or asks to make an asset more pixelated, less painterly, less gradient-like, or closer to the established Idel-Game art direction.
---

# Pixel Fantasy Assetgen

## Core Use

Create consistent AI image prompts and art-direction feedback for the established `Idel-Game` look: modern but clearly pixelated 2D fantasy side-scroller art with crisp silhouettes, limited palettes, cool teal/blue shadows, fresh greens, and selective warm highlights.

Use image generation directly when the user asks to see an asset. When the user asks for guidance, provide concise art-direction notes or a reusable prompt.

## Workflow

1. Identify the asset type: character, enemy, environment, scene deconstruction, tileset, prop, UI icon, effect, or palette sheet.
2. Preserve the style anchors:
   - strict low-resolution pixel art
   - visible square pixels and hard edges
   - unified dark navy outline
   - limited palette with 3 to 5 shade levels per material
   - no gradients, painterly lighting, soft anti-aliasing, or smooth material transitions
3. Make the asset game-ready:
   - characters should read at small sprite scale
   - scenes should support side-scrolling gameplay readability
   - when the user provides a reference scene image, treat that image as authoritative for shapes, proportions, palette, lighting, and object list
   - scene deconstruction should split large objects, small props, terrain tiles, and parallax/background pieces into separate sheets
   - never mix large environment objects such as trees and arches with tiny props in the same extraction sheet
   - animation sheets should separate poses clearly
   - isolated assets should use one explicit background mode: pure white, green screen `#00ff00`, or blue screen `#0000ff`
4. Apply the correct prompt recipe from `references/style-guide.md` when detail is needed.
5. For iterative refinements, keep accepted traits and change only the requested axis, such as stronger pixelation, simpler material transitions, clearer silhouette, or different class identity.

## Quick Recipes

For a character sprite:

```text
Original [human/class/enemy] sprite sheet for a 2D side-scrolling pixel art action platformer, true small game sprite style, 48x64 frame feeling, strict low-resolution pixel art, visible square pixels, hard edges, limited palette, no gradients, no painterly lighting, no anti-aliased smooth material transitions. Unified dark navy outline, chibi heroic proportions, compact readable silhouette, facing right. Transparent background, no text, no UI, no scenery. Include 4 separate animation-ready poses in a row: idle, attack/cast, walking step, hurt/flinch.
```

For a Unity-ready animation sheet, prefer fixed cells and one chosen background color:

```text
Unity-ready sprite sheet, exactly [columns] columns by [rows] rows, each frame in a fixed equal-size cell, all frames centered, same foot baseline, same body center, no cropping, no visible grid, background mode: pure white / #00ff00 green screen / #0000ff blue screen.
```

For a daytime forest ruins scene:

```text
Original 2D side-scrolling pixel art game environment, bright daytime fantasy forest ruins level, modern detailed pixel art with visible pixels and crisp edges. Wide 16:9 horizontal scene, layered parallax composition: foreground leafy silhouettes, playable grassy platform, mossy stone path, small flowers, midground ancient broken arches and vine-covered pillars, background huge green trees, pale cyan sky, cream clouds, distant ruins in atmospheric haze. Cool teal/blue shadows, fresh greens, warm sunlight highlights, no characters, no UI, no text.
```

For scene deconstruction into reusable asset sheets:

```text
Using the provided reference scene image as the authoritative source, deconstruct that exact daytime fantasy forest ruins scene into four separate isolated pixel-art asset sheets: large environment objects, small props and vegetation, terrain tileset, and parallax background elements. Match the reference image's object shapes, proportions, palette, lighting direction, stone texture, foliage clusters, and atmosphere. Do not invent a different style or new object language. Do not mix large objects with tiny props. Use blue screen background `#0000ff`, no text, no labels, no UI, no visible grid, no overlap, no cropping, generous padding, consistent pixel density, consistent upper-right light direction.
```

## Refinement Rules

- If the image feels too illustrated, add: `true small game sprite, hard 1-2 pixel highlights, blocky shadow clusters, reduced shade count`.
- If material transitions feel too smooth, add: `flat cel-like pixel clusters, 3 shade levels only, no soft texture, no gradient ramps`.
- If the silhouette is unclear, simplify accessories, increase outline contrast, and emphasize one class-defining shape.
- If the image is too noisy, reduce tiny detail and keep only readable shapes at gameplay scale.
- If the result is not pixelated enough, specify frame size feeling such as `32x48`, `48x64`, or `64x64`, plus `nearest-neighbor pixel-art look`.

## Reference

Read `references/style-guide.md` for the full style guide, palette notes, negative prompts, and specialized recipes for knights, mages, enemies, scenes, tilesets, UI icons, and VFX.
