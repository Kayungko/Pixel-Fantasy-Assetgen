# Pixel Fantasy Assetgen 使用文档

`pixel-fantasy-assetgen` 是一个面向 2D 横版像素奇幻游戏素材生成的 Codex Skill。它用于生成或优化统一画风的角色、动画精灵图、场景、tileset、拆件素材、UI 图标和特效提示词。

目标画风：

- 现代低分辨率 2D 像素奇幻横版风格
- 可见方块像素、硬边、低色阶
- 深蓝/蓝黑描边
- 青蓝阴影、鲜绿色植被、少量暖金高光
- 避免平滑渐变、厚涂感、真实 3D 材质、柔和抗锯齿

## 安装

将仓库克隆到 Codex 技能目录：

```powershell
git clone git@github.com:Kayungko/Pixel-Fantasy-Assetgen.git "$env:USERPROFILE\.codex\skills\pixel-fantasy-assetgen"
```

重启 Codex 桌面版或重新打开 workspace 后，在技能页中查找：

```text
Pixel Fantasy Assetgen
```

## 基础用法

在 Codex 中直接点选技能，或在提示词中显式调用：

```text
Use $pixel-fantasy-assetgen to generate a human wizard sprite in the established side-scrolling pixel fantasy style.
```

中文也可以：

```text
使用 $pixel-fantasy-assetgen，生成一个人类骑士角色，横版像素奇幻风格，朝右。
```

## 背景色规则

隔离素材和 sprite sheet 必须指定一种背景：

- `pure white`：快速预览用。
- `#00ff00 green screen`：适合非绿色角色或道具，方便后期抠图。
- `#0000ff blue screen`：适合森林、草、藤蔓、绿色角色等素材，避免和绿色主体冲突。

不要使用棋盘格背景作为生产素材背景。

## 角色素材提示词

### 人类骑士

```text
Use $pixel-fantasy-assetgen to create a human knight sprite for a 2D side-scrolling pixel art action game. Facing right, compact heroic chibi proportions, 48x64 frame feeling, dark navy outline, steel helmet or short visible hair, simple blue-gray plate armor, muted blue cloth accent, brown boots, small round shield and short sword. Strict low-resolution pixel art, visible square pixels, hard edges, limited palette, 3 shade levels per material, no smooth gradients, no painterly lighting, no glossy metal. Background mode: #0000ff blue screen, no text, no UI, no scenery.
```

### 人类魔法师

```text
Use $pixel-fantasy-assetgen to create a human wizard sprite for a 2D side-scrolling pixel art action game. Facing right, 48x64 frame feeling, large dark violet pointed hat, tiny simplified face, red hair, emerald scarf or capelet, dark violet robe with 3 shade levels, brown boots, wooden staff with cyan crystal. Strict low-resolution pixel art, visible square pixels, hard edges, dark navy outline, compact readable silhouette, no soft cloth gradients. Background mode: #0000ff blue screen, no text, no UI, no scenery.
```

### 敌人

```text
Use $pixel-fantasy-assetgen to create a small fantasy enemy sprite sheet for a 2D side-scrolling pixel art game. Readable dark silhouette, compact proportions, cool blue-purple shadows, one bright cyan or amber accent for eyes or magic, 4 animation-ready poses in a row: idle, attack, walk step, hurt. Strict low-resolution pixel art, visible square pixels, hard edges, limited palette, no smooth gradients, no painterly lighting. Background mode: #00ff00 green screen, no text, no UI, no scenery.
```

## Unity 动画精灵图

### 5x5 待机到跑动再回待机

```text
Use $pixel-fantasy-assetgen to create a Unity-ready 5x5 sprite sheet for the established human wizard character. Exactly 320x320 pixels total, exactly 5 columns and 5 rows, each frame exactly 64x64 pixels, aligned to an invisible grid. Animation sequence: idle breathing poses, transition into run, full run cycle, transition back to idle, final idle pose. Keep every frame centered in its 64x64 cell, same foot baseline at y=56, same body center at x=32, consistent scale, no cropping, no visible grid, no labels, no text, no UI. Background mode: #0000ff blue screen. Strict low-resolution pixel art, visible square pixels, hard edges, no anti-aliasing, no smooth gradients.
```

### 跑动横条

```text
Use $pixel-fantasy-assetgen to create a wizard running animation sprite sheet, 8 frames in one row, fixed equal-size cells, each frame centered, same foot baseline, same body center. Facing right, large dark violet hat, emerald scarf, dark robe, brown boots, wooden staff with cyan crystal. Background mode: #0000ff blue screen, no grid, no text, no UI, no scenery. Strict low-resolution pixel art, visible square pixels, hard edges, limited palette.
```

## 场景提示词

### 通用横版场景风格锁

```text
High-detail side-scroller style lock: keep a 16:9 horizontal playable side-scrolling level composition, not a wallpaper or concept-art scene. Place the readable gameplay platform in the lower third. Use a crisp playable terrain edge with a brighter top cap and dark underside shadows. Separate foreground, midground, and background with clear value and saturation steps. Use atmospheric parallax depth, low-contrast distant shapes, visible square pixels, hard edges, blocky pixel clusters, and limited 3 to 5 shade levels per material. Add only small local accent lights. No UI, no labels, no screenshot overlay.
```

### 白天森林遗迹 16:9

```text
Use $pixel-fantasy-assetgen to create an original 16:9 horizontal 2D side-scrolling pixel art game environment, bright daytime fantasy forest ruins level. Layered parallax composition: foreground dark leafy silhouettes, playable grassy platform in lower third, mossy blue-gray stone path, small white and purple flowers, midground ancient broken arches and vine-covered pillars, background huge rounded green trees, pale cyan sky, cream clouds, distant ruins in atmospheric haze. Cool teal-blue shadows, fresh greens, warm sunlight highlights, no characters, no UI, no text. Strict pixel art, visible square pixels, crisp hard edges, no smooth gradients, no painterly lighting.
```

### 夜晚森林遗迹 16:9

```text
Use $pixel-fantasy-assetgen to create an original 16:9 horizontal 2D side-scrolling pixel art game environment, nighttime fantasy forest ruins level.

High-detail side-scroller style lock: readable gameplay platform in the lower third, strong foreground/midground/background separation, atmospheric parallax depth, low-contrast distant shapes, crisp playable terrain edge, dark underside shadows, visible square pixels, hard edges, limited palette with 3 to 5 shade levels per material.

Scene content: mossy blue-gray stone platform with fresh grass cap, broken ancient ruin arches and vine-covered pillars in the midground, rounded clustered tree canopies and hazy forest layers in the background, teal mist between layers, distant pale blue ruin silhouettes, dark cyan night sky. Add small warm lantern or candle accents and a few subtle emerald fireflies.

Night scene lock: use deep navy, muted violet, teal mist, blue-gray stone, restrained emerald vegetation, and small warm amber highlights. The moon, if present, must be small and atmospheric, not the main subject.

No characters, no UI, no text. Do not create a generic spooky forest, giant dominant moon, jagged black gothic trees, regular castle brick blocks, neon-blue over-saturation, painterly gradients, soft blur, realistic 3D lighting, or anti-aliased illustration.
```

## 场景拆件提示词

有参考场景图时，明确要求参考图是唯一权威来源：

```text
Use $pixel-fantasy-assetgen. Use the attached reference scene image as the authoritative source. Deconstruct that exact scene into reusable game assets. Match the reference image's object shapes, proportions, palette, lighting direction, foliage clusters, stone texture, and atmosphere. Do not invent a different style or new object language.
```

### 大件 Sheet

```text
Use $pixel-fantasy-assetgen to create a large environment object extraction sheet from the attached reference scene. Extract only large visible elements: complete moss-covered stone arch, broken horizontal ruin beam or platform, smaller arch fragment, tall broken pillar, rounded background tree canopy with trunk, mossy blue-gray platform wall or base segment. Background mode: #0000ff blue screen. Isolated complete objects only, no full scene composition, no text, no labels, no UI, no visible grid. Generous padding, no overlap, no cropping. Match the reference palette and pixel density.
```

### 小物件 Sheet

```text
Use $pixel-fantasy-assetgen to create a small props and vegetation extraction sheet from the attached reference scene. Extract only small visible elements: grass tuft, taller grass clump, white flower cluster, purple flower cluster, fern-like plant, hanging vine cluster, short vine strand, mossy loose stone, broken blue-gray brick pile, warm lantern on stone base, blue hanging banner with gold emblem, treasure chest, small mossy slab, root cluster, dark foreground leafy silhouette plant. Background mode: #0000ff blue screen. Isolated small objects only, no large arches, no trees, no platform tiles, no text, no labels, no grid.
```

### 地形 Tileset

```text
Use $pixel-fantasy-assetgen to create a terrain tileset extraction sheet from the attached reference scene. Extract playable platform and stone terrain pieces: grass-top blue-gray stone tile, mossy stone fill block, left platform cap, right platform cap, outer corner, inner corner, broken platform edge, flat mossy stone slab, vine-covered edge piece, dark underside stone block, cracked ruin brick tile, connector stone tile, vertical side tile. Background mode: #0000ff blue screen. Buildable level pieces only, no props, no trees, no arches, no visible grid. 16x16 and 32x32 tile feeling.
```

### 远景 / Parallax Sheet

```text
Use $pixel-fantasy-assetgen to create a parallax background element extraction sheet from the attached reference scene. Extract only background layer elements: distant pale blue ruin arch silhouette, distant large ruin arch, faint broken tower silhouette, far tree line chunk, rounded low-contrast green canopy mass, cream pixel cloud chunk, pale cyan cloud strip, hazy forest shape, atmospheric blue-green tree cluster. Background mode: #0000ff blue screen. Lower contrast and lower saturation than foreground assets, no foreground props, no terrain tiles, no text, no labels, no visible grid.
```

## UI 图标和 VFX

### RPG UI 图标组

```text
Use $pixel-fantasy-assetgen to create a small RPG UI icon set, 32x32 icon feeling, dark navy outline, limited palette, hard pixel edges, clear silhouettes, cool teal shadows and warm gold highlights. Include sword, shield, staff, potion, coin, spell book, boot, helmet. Transparent or pure white background, no text, no mockup UI panel.
```

### 魔法特效

```text
Use $pixel-fantasy-assetgen to create a pixel art magic effect sprite sheet for a 2D fantasy side-scroller. 6 animation frames in one row, cyan and emerald glow represented by hard pixel clusters, small star particles, no soft bloom, no character, no text. Background mode: #0000ff blue screen, strict low-resolution pixel art, visible square pixels, no smooth gradients.
```

### 打击特效

```text
Use $pixel-fantasy-assetgen to create a pixel art impact effect sprite sheet for a 2D side-scrolling action game. 6 frames in one row, amber orange core, deep red shadow pixels, hard-edged pixel clusters, readable at small scale, no smoke realism, no soft gradients, no text. Background mode: #00ff00 green screen.
```

## 常用修正提示词

更像素：

```text
Make it more like true small game pixel art: visible square pixels, nearest-neighbor look, chunky pixel clusters, hard 1-2 pixel highlights, reduced shade count, no anti-aliasing.
```

减少材质过渡：

```text
Reduce smooth material transitions: use flat pixel clusters, blocky shadow shapes, 3 shade levels only, no gradient ramps, no painterly lighting, no soft texture.
```

增强剪影：

```text
Improve gameplay readability: simplify tiny details, strengthen the dark navy outline, enlarge the class-defining silhouette, keep accessories readable at small sprite scale.
```

更适合 Unity 切分：

```text
Make it Unity-ready: fixed equal-size cells, exact grid dimensions, same body center, same foot baseline, no cropping, no visible grid, no labels, no text, one explicit background color.
```

## 注意事项

- AI 生成图适合作为概念稿和初版素材，不保证天然像素级严格对齐。
- 真正进 Unity 前，建议二次整理为固定 cell、统一 pivot、统一透明背景。
- 参考图拆件时，优先拆参考图已有物件；不要让模型自由发明新风格。
- 大件、小件、地形、远景建议分成不同 sheet 生成，避免大树、拱门等物件被裁切。
- 第三方游戏截图只适合本地风格分析；公开仓库中应保存原创规则、原创素材和可迁移的文字化风格规范。
