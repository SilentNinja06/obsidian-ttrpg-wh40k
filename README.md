# TTRPG Campaign Manager — Warhammer 40,000 System Pack

System pack for the [TTRPG Campaign Manager](https://github.com/SilentNinja06/obsidian-ttrpg-core) Obsidian plugin, adding Warhammer 40,000 support.

## What this pack adds

- Nine characteristics: WS, BS, S, T, W, I, A, Ld, Sv
- Wound tracking via `wounds-current` and `w` frontmatter fields
- Character fields: faction, unit type, squad size, points cost, wargear, special rules
- Unit entity type with squad-level tracking
- d6-based combat with alternating turn order and Ld morale tests
- No currency system (points-based instead)
- Arc fields adapted for 40k narrative: role, faction, agenda, wants from warband
- NPC fields: role, faction, agenda, threat level

## Installation

1. Install the [TTRPG Campaign Manager core plugin](https://github.com/SilentNinja06/obsidian-ttrpg-core)
2. Download `wh40k.yaml` from the [Releases](../../releases) page
3. Copy it into your vault's `ttrpg/systems/` folder
4. In Obsidian, open Settings → TTRPG Campaign Manager → click "Reload systems"

## Dataview queries

Query all your 40k characters by faction:

```dataview
TABLE faction, unit-type, points, w AS "Wounds"
FROM "ttrpg/campaigns"
WHERE ttrpg-type = "character" AND system = "wh40k"
SORT faction ASC
```

## Notes on WH40k vs D&D differences

The combat tracker uses alternating turns rather than initiative order, reflecting 40k's alternating activation style. The HP tracker maps to Wounds (W characteristic). The Sv (Save) field is a string to accommodate values like "3+" and "4+". Morale tests use the Ld characteristic.

## License

MIT
