# LiD Mods

Every mod for the [LID DB Mod Manager](https://github.com/NicoMullin/LiD-DB-Editor) that
needs no plugin, in one place. Each mod is its own download, so you get only the ones you
want, and a fixed mod goes out on its own without a new manager.

## Getting mods

In the mod manager, open **Get mods** and the **Mods** tab, then click **Check GitHub for the
newest**. Every mod is listed with the version you have and the newest one:

- **Get** adds a mod you do not have.
- **Update** brings a newer version of one you have. **Update all** does every one at once.
- Nothing is downloaded until you click, and you see what will be written before anything is.

A mod you update keeps its settings. Click **Save Mod List** afterwards to apply the new
version to the game.

The manager comes in two downloads: one with every mod here, and one with none, for players
who would rather pick. Updating the manager from inside it (**Help > Check for updates**)
only ever brings the program and never changes your mods.

Mods that need a plugin (Timers, HUD, Death Metals and the rest) each have their own
repository; they are on the **Mods with a plugin** tab of the same window.

Every zip is also on the [release page](../../releases/tag/mods). Unzipped, it holds the mod's
folder under `mods/`, which goes in the manager's own `mods` folder as it is.

## Publishing a change

1. Change the mod in `mods/<its folder>/`.
2. Raise `"version"` in its `mod.json`. The manager re-applies a mod only when its version
   changes, so a change without a new version would never reach anyone who already has it -
   the build stops and says so.
3. Push to `main`.

GitHub then builds a zip for every mod whose version went up, signs it, uploads it to the
release **mods** and updates `mods-index.json`, the list the manager reads. Mods that did not
change are left as they are. A new mod is a new folder with a `mod.json`; a folder that is
removed is taken off the list.

To try it without publishing, run the same build locally:

```
py -3 tools/publish_mods.py --mods mods --out out
```

## Checking a download

Every zip is built by GitHub Actions from this repository, and its SHA-256 is in
`mods-index.json` and on the release page. The manager checks each download against it. To
check one yourself, with the [GitHub CLI](https://cli.github.com/):

```
gh attestation verify <file>.zip --repo NicoMullin/LiD-Mods
```

## Credit

Each mod's author is in its `mod.json` and shown in the manager. Mods by others are here
with their permission: S3er0i9ng (LET IT DIE Crossover Content, Colored PlayStation Buttons,
Online Research Costs, Tower Static Radio), ZeroUnderOne (Tengoku Enjoyer, Pre-Nerf Gear) and
3bgdragon (the ammo refill and decal menu in Vending Machine). Everything else is by KSFA.
