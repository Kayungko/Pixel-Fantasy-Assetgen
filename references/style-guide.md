# Pixel Fantasy Asset Style Guide

## Art Direction

Target a modern detailed pixel-art look for a 2D side-scrolling fantasy action/platformer. The style should feel polished and atmospheric, but never painterly. Pixel structure must remain visible.

Core mood:

- bright or moody fantasy forest ruins
- dark fairytale adventure rather than high-detail illustration
- readable gameplay silhouettes
- layered parallax backgrounds
- cool shadows with selective warm highlights

Avoid:

- smooth gradients
- painterly brush texture
- anti-aliased material transitions
- realistic 3D lighting
- glossy rendered armor
- excessive micro-detail that disappears at small scale
- text, UI, watermarks, or mockup labels unless requested

## Palette

Base palette:

- outline: dark navy or blue-black
- shadows: deep blue, blue-purple, teal
- nature: fresh greens, emerald accents, moss greens
- sky/daylight: pale cyan, soft cream clouds
- stone: cool gray with mossy green touches
- warmth: small amber, gold, orange, or sunlight highlights
- magic: cyan, turquoise, emerald, violet, or pale gold

Keep each material to roughly 3 to 5 shade levels. Use hard cluster boundaries instead of smooth ramps.

## High-detail Side-scroller Style Lock

Use this lock for environment scenes when the user wants a stable game-ready side-scroller look. Keep the output 16:9 horizontal; do not copy reference screenshot dimensions.

- compose as a playable side-scrolling level, not a standalone illustration
- place the readable gameplay platform in the lower third
- make the playable terrain edge crisp, with a brighter top cap and a dark underside
- separate foreground, midground, and background with clear value and saturation steps
- keep distant shapes lower contrast and lower saturation than foreground assets
- use atmospheric parallax depth with mist, haze, or soft color separation between layers
- preserve visible square pixels, hard edges, and readable blocky pixel clusters
- use high-detail pixel art: clear large silhouettes with small internal texture clusters
- use limited palettes per material, usually 3 to 5 shade levels
- use small local accent lights, such as lanterns, candles, magic sparks, or fireflies
- avoid UI framing, screenshot overlays, minimaps, health bars, labels, or watermark text

Avoid drifting into:

- generic wallpaper or concept-art composition
- overly smooth painterly gradients
- realistic 3D lighting or material rendering
- flat single-layer backgrounds
- muddy terrain edges that do not read as playable
- huge decorative focal objects that steal attention from the level layout

## Character Rules

Default character target:

- isolated asset background should be explicitly chosen: pure white, green screen `#00ff00`, or blue screen `#0000ff`
- facing right unless requested otherwise
- 48x64 frame feeling for humanoids
- chibi heroic proportions
- head and class silhouette slightly exaggerated
- unified dark navy outline
- small simplified face
- clear boots, hands, weapon/staff/tool
- 4 poses when making a sheet: idle, action, walk step, hurt/flinch

## Background Modes

Use one of these three background modes for isolated sprites:

- Pure white: use for quick visual review and when the character does not contain near-white edge details.
- Green screen `#00ff00`: use for later chroma-key removal when the sprite has no green or emerald elements.
- Blue screen `#0000ff`: use for later chroma-key removal when the sprite has green/emerald elements, such as this wizard's scarf and cyan magic.

Never use checkerboard backgrounds for production sprite sheets. Checkerboards are preview conventions, not real alpha, and make Unity slicing and cleanup harder.

Default to pure white for previews if the user does not specify a background. For assets intended for cleanup into transparency, prefer blue screen for green-heavy characters and green screen for non-green characters.

## Unity Sprite Sheet Rules

When the user asks for Unity-ready sprites, include fixed slicing constraints:

- specify exact grid dimensions, such as `5 columns by 5 rows`
- specify equal-size cells, such as `64x64 per frame`
- specify total sheet size when possible, such as `320x320 total`
- keep every frame centered inside its cell
- keep the same foot baseline in every frame
- keep the same body center in every frame
- leave padding around hats, weapons, staffs, capes, and VFX
- no visible grid lines, frame numbers, labels, UI, or scenery
- use one explicit background mode: pure white, `#00ff00`, or `#0000ff`

Unity-ready 5x5 recipe:

```text
Unity-ready 5x5 sprite sheet, exactly 320x320 pixels total, exactly 5 columns and 5 rows, each frame exactly 64x64 pixels, aligned to an invisible grid. Keep every frame centered in its 64x64 cell, same foot baseline at y=56 inside each cell, same body center at x=32, consistent character scale, no cropping, no visible grid, no labels, no text, no UI. Background mode: [pure white / #00ff00 green screen / #0000ff blue screen].
```

For a stronger pixel look:

```text
strict low-resolution pixel art, visible square pixels, nearest-neighbor look, hard edges, no anti-aliasing, limited palette, chunky pixel clusters, hard 1-2 pixel highlights, 3 shade levels per material
```

For reducing material transitions:

```text
flat pixel clusters, blocky shadow shapes, no smooth gradient ramps, no painterly lighting, no soft metal shine, no glossy rendered texture
```

## Class Recipes

Human knight:

```text
Human knight sprite sheet, compact heroic silhouette, steel helmet or short hair visible, simple plate armor with blue-gray shadows, small round shield or short sword, muted blue cloth accent, brown boots, readable armor plates made from blocky pixel clusters, no glossy reflections.
```

Human wizard:

```text
Human wizard sprite sheet, large pointed hat, dark violet robe with 3 shade levels, emerald capelet or scarf accent, brown boots, wooden staff with cyan crystal, tiny simplified face, magical hand pose, readable robe silhouette, no soft cloth gradients.
```

Archer or rogue:

```text
Human archer rogue sprite sheet, hood or short cloak, compact leather armor, short bow or twin dagger silhouette, muted green and brown palette with teal shadows, small amber buckle accents, agile stance, no realistic leather texture.
```

Healer:

```text
Human healer sprite sheet, soft white and muted teal robe, small gold trim, simple hood or circlet, staff or charm, gentle cyan-gold magic accent, clean readable silhouette, no glowing bloom overload.
```

Enemy:

```text
Small fantasy enemy sprite sheet, readable dark silhouette, cool blue-purple shadows, one bright accent color for eyes or magic, compact side-scroller proportions, 4 animation-ready poses, transparent background, no scenery.
```

## Environment Rules

Scene target:

- 16:9 horizontal side-scrolling composition
- no characters unless requested
- no UI or text
- playable platform should sit in lower third
- foreground silhouettes should frame but not block gameplay
- midground should contain readable ruins, trees, vines, props
- background should be lower contrast with atmospheric haze

Daytime forest ruins recipe:

```text
Original 2D side-scrolling pixel art game environment, bright daytime fantasy forest ruins level, modern detailed pixel art with visible pixels and crisp edges. Wide 16:9 horizontal scene, layered parallax composition: foreground leafy silhouettes, playable grassy platform, mossy stone path, small flowers, midground ancient broken arches and vine-covered pillars, background huge soft green trees, pale cyan sky, cream clouds, distant ruins in atmospheric haze. Cool teal/blue shadows, fresh greens, warm sunlight highlights, no characters, no UI, no text.
```

Night or dark forest variant:

```text
Original 16:9 horizontal 2D side-scrolling pixel art game environment, nighttime fantasy forest ruins level. Apply the high-detail side-scroller style lock: readable gameplay platform in the lower third, crisp mossy terrain edge, dark stone underside shadows, strong foreground/midground/background separation, atmospheric parallax depth, and low-contrast distant shapes. Use mossy blue-gray stone platform with fresh grass cap, broken ancient ruin arches, vine-covered pillars, rounded clustered tree canopies, hazy forest layers, teal mist, distant pale blue ruin silhouettes, deep navy and muted violet shadows, restrained emerald vegetation, and small warm amber lantern or candle accents. The moon, if present, should be small and atmospheric, not the main subject. No characters, no UI, no text.
```

Night scene anti-drift rules:

- do not make a giant moon the main focal point
- do not turn the scene into a generic spooky forest
- do not use jagged black gothic trees as the dominant foreground language
- do not use regular castle brick blocks instead of mossy blue-gray ruin stones
- do not over-saturate the scene with neon blue
- do not lose the soft layered haze and side-scroller gameplay readability

## Scene Deconstruction Rules

When turning a scene into reusable game assets, split sheets by object scale and gameplay use. Do not create one crowded mixed sheet when the scene contains both large structures and tiny props.

If the user provides a reference scene image, that image is the source of truth. Match its silhouette language, proportions, palette, lighting direction, foliage clustering, stone shapes, atmospheric depth, and object list. Extract and modularize what is visible in the reference instead of inventing new assets. Avoid changing the scene into a different forest, different ruin style, different tree species, or different color script.

Use four separate sheets by default:

- Large environment objects: complete trees, large tree-canopy chunks, ruin arches, broken pillars, big stone walls, and stone beams.
- Small props and vegetation: grass tufts, flowers, ferns, vines, hanging vines, mushrooms, loose stones, broken bricks, lanterns, banners, and chests.
- Terrain tileset: grass-top tiles, mossy stone fill blocks, platform caps, outer corners, inner corners, broken edges, slabs, and vine edge pieces.
- Parallax background elements: distant ruin silhouettes, far tree layers, cloud chunks, distant hills, and low-contrast canopy masses.

Shared extraction rules:

- background mode: blue screen `#0000ff`
- provided reference scene image is authoritative when available
- match reference shapes, proportions, palette, lighting, and pixel density
- extract visible reference objects before adding any generic fantasy objects
- isolated objects only, not a composed scene
- no text, labels, UI, frame numbers, watermarks, or visible grid
- no overlap and no cropping
- leave generous padding around every object
- keep consistent pixel density, palette, and upper-right light direction
- keep foreground objects sharper and higher contrast than parallax elements
- use hard pixel clusters, limited shade counts, and no smooth gradients

Large environment objects recipe:

```text
Large-object pixel art asset sheet for a 2D side-scrolling fantasy forest ruins level, using the provided reference scene image as the authoritative source. Match the reference image's rounded leafy tree clusters, blue-gray mossy ruin stones, vine-covered arches, broken pillars, cyan daylight, and soft warm highlights. Blue screen background `#0000ff`, isolated complete objects only, no scene composition, no text, no labels, no UI, no visible grid. Include about 6 complete large reusable objects extracted from the reference: full rounded background tree with trunk and canopy, separate large rounded green canopy chunk, foreground vine-covered ruin arch matching the left arch, broken horizontal ruin beam/platform matching the center ruin, tall broken pillar matching the right pillar, and mossy stone wall or base segment matching the playable platform. Generous padding, no overlap, no cropping, especially do not crop tree canopies, arches, pillars, or roots. Modern detailed low-resolution pixel art, visible square pixels, crisp hard edges, cool teal-blue shadows, fresh greens, warm sunlight highlights, consistent upper-right light, limited palette, no smooth gradients, no painterly lighting.
```

Small props and vegetation recipe:

```text
Small-prop pixel art asset sheet for a 2D side-scrolling fantasy forest ruins level, using the provided reference scene image as the authoritative source. Match the reference image's small white and purple flowers, bright grass clumps, fern-like plants, hanging vines, blue banner, warm lanterns, and treasure chest. Blue screen background `#0000ff`, isolated small objects only, no large trees or arches, no scene composition, no text, no labels, no UI, no visible grid. Include 12 to 16 compact reusable props and vegetation pieces extracted from the reference: grass tuft, taller grass clump, white flower cluster, purple flower cluster, fern, hanging vine cluster, short vine strand, loose mossy stone, broken brick pile, warm lantern on stone base, blue hanging banner with gold emblem, treasure chest, small mossy slab, root cluster, foreground leafy silhouette plant, and tiny platform flowers. Consistent small prop scale, generous padding, no overlap, no cropping. Modern detailed low-resolution pixel art, visible square pixels, crisp hard edges, dark navy outlines, cool teal-blue shadows, fresh greens, warm sunlight highlights, consistent upper-right light, limited palette, no smooth gradients, no painterly lighting.
```

Terrain tileset extraction recipe:

```text
Terrain tileset pixel art sheet for a 2D side-scrolling fantasy forest ruins level, using the provided reference scene image as the authoritative source. Match the reference image's playable grassy platform, blue-gray block stone fill, mossy top edge, darker underside, dangling vines, and cracked ruin masonry. Blue screen background `#0000ff`, reusable buildable level pieces only, no decorative props, no trees, no arches, no scene composition, no text, no labels, no UI, no visible grid. Include grass-top tiles, mossy blue-gray stone fill blocks, left platform cap, right platform cap, outer corner, inner corner, broken platform edge, mossy stone slab, vine edge piece, dirt or root underside, small connector stones, and cracked ruin brick tile. 16x16 and 32x32 tile feeling, consistent pixel density, clear tile silhouettes, enough padding for later Unity slicing, no overlap, no cropping. Modern detailed low-resolution pixel art, visible square pixels, crisp hard edges, cool gray stone, moss greens, teal-blue shadows, warm sunlight highlights, limited palette, no smooth gradients, no painterly lighting.
```

Parallax background elements recipe:

```text
Parallax background pixel art asset sheet for a 2D side-scrolling fantasy forest ruins level, using the provided reference scene image as the authoritative source. Match the reference image's pale cyan sky, cream clouds, distant blue ruin arches, hazy tree layers, and rounded background canopy masses. Blue screen background `#0000ff`, isolated background layer elements only, no foreground props, no terrain tiles, no characters, no scene composition, no text, no labels, no UI, no visible grid. Include distant pale blue ruin arch silhouette from the left background, distant broken pillar silhouette, soft far tree line chunk, rounded low-contrast green canopy mass, cream pixel cloud chunk, pale cyan cloud strip, distant forest shape, and atmospheric haze tree cluster. Lower contrast and lower saturation than foreground assets, softer silhouette but still pixelated, generous padding, no overlap, no cropping. Modern low-resolution pixel art, visible square pixels, crisp enough edges, cool teal-blue shadows, pale cyan sky tones, limited palette, no smooth gradients, no painterly lighting.
```

## Tilesets

Use tilesets when the user asks for buildable level pieces:

```text
Pixel art tileset for a 2D side-scrolling fantasy forest ruins level, 16x16 and 32x32 tile feeling, grass top tiles, dirt fill tiles, mossy stone blocks, broken ruin bricks, vine edges, small flowers, roots, platform caps, inner corners, outer corners, limited palette, hard edges, visible pixels, transparent background, no text.
```

Ask for or infer tile size only if the user needs engine-ready slicing. Otherwise use `16x16 and 32x32 tile feeling`.

## UI Icons

UI icon recipe:

```text
Small pixel art RPG UI icon set, 32x32 icon feeling, dark navy outline, limited palette, hard pixel edges, clear silhouette, cool teal shadows and warm gold highlights, transparent background, no text, no mockup UI panel.
```

## VFX

Magic effect recipe:

```text
Pixel art magic effect sprite sheet for a 2D fantasy side-scroller, cyan and emerald glow represented by hard pixel clusters, no soft bloom, 6 animation frames in a row, transparent background, no text, no character.
```

Fire or impact effect recipe:

```text
Pixel art impact effect sprite sheet, amber orange core with deep red shadow pixels, hard-edged pixel clusters, 6 frames in a row, transparent background, no soft gradients, no smoke realism, no text.
```

## Negative Prompt Block

Append this when results drift away from the target:

```text
No painterly rendering, no smooth gradients, no anti-aliased illustration, no realistic 3D materials, no glossy surfaces, no soft bloom, no blur, no high-resolution concept art, no text, no watermark, no UI mockup.
```
