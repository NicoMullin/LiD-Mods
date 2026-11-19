# Unbreakable Gear

Your weapons and armor never lose durability, so they never break. In return,
weapons and armor cost more to buy: x10 by default.

## Your values

**Gear price** - default **x10**, from **x1** (stock) to **x100**. What
weapons and armor cost at Choku-Funsha, at every level.

Select this mod and open the **Configuration** tab on the right to change it,
or right-click it and pick **Change values...**. Press Enter or click away,
then **Save Mod List**.

## What it changes

**No wear (BrgGame.upk).** The game checks four things before it takes
durability off your gear:

| Check                               | When                                    |
|-------------------------------------|-----------------------------------------|
| `IsWeaponDurabilityDown`            | hitting with a weapon, blocking with it |
| `IsWeaponShotDurabilityDown`        | firing a gun                            |
| `IsWeaponDurabilityDownBySkillMove` | rage and skill moves                    |
| `IsArmorDurabilityDown`             | taking damage                           |

Each check now answers "no wear" for your fighter. Everyone else gets the
game's own answer, so Haters' weapons still wear down and their armor still
breaks off when you hit it.

**Prices (masters.db).** `master_part.price_s`, the Kill Coin price of every
weapon and armor piece, is multiplied by **Gear price**. The game raises it for
each level on top of that, so every level costs x10. Masks and pants cost
nothing and stay free.

Left alone on purpose:

- `price_b`, what Choku-Funsha pays when you sell. Raising it too would turn
  selling into free money.
- Research costs at Kickback (SPLithium and materials).
- The durability numbers themselves (`dur`, `dur_hit`, `dur_shoot`,
  `dur_rage`). The game never gets as far as using them for you.

## Good to know

- Gear you find in the Tower can come already worn. It stays at whatever
  durability it had when you picked it up, so it never breaks, but it is not
  repaired either.
- Gear that is already worn keeps its current durability.
- Needs the Hash Patcher's check off for `BrgGame.upk`, like the other mods
  that change it. The manager does this for you.
- Works alongside the other BrgGame.upk mods. It changes only these four checks.

## Reverting

Automatic. Untick it and save: `BrgGame.upk` goes back to its own copy and the
prices go back to stock.

## Built for game 5.0.6.0.0 - 1.93

## Credit

By KSFA.
