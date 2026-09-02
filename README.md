# assets

Source assets for [roadrunner](https://github.com/roadrunner-craft/client), a
voxel game. Block textures and the game icon are authored here as layered PSD
files, alongside the game font and the block and texture definitions the game
loads at runtime. The export script renders everything into the plain PNG and
data files the game consumes, so the editable sources never ship with the game.

## Usage

Exporting requires Python and [ImageMagick](https://imagemagick.org), both
installed through [mise](https://mise.jdx.dev):

```sh
mise install
```

Render every asset into a target directory:

```sh
./scripts/export.py <output_dir>
```

Only sources that changed since the last export are re-rendered.

To re-export automatically whenever a file under `res` changes, install
[watchdog](https://pypi.org/project/watchdog/) and run the watcher:

```sh
pip install -r scripts/requirements.txt
./scripts/watch.py <output_dir>
```

## Layout

- `res/textures/block` — block textures, one PSD per texture
- `res/data/blocks.json` — block definitions: solidity, opacity, and the texture of each face
- `res/data/textures.json` — texture indices mapped to texture names
- `res/fonts` — the game font
- `icon/icon.psd` — game icon, exported as PNGs from 16 to 512 pixels
