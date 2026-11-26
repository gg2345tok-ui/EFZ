Structure Loot Injector — Pool Config Files
============================================

Place *.json files in this folder to inject loot into ANY loot table
(vanilla structures, modded structures, mob drops, fishing — everything).

Minimal example:
{
  "target_loot_table": "minecraft:chests/simple_dungeon",
  "enabled": true,
  "inject_items": [
    { "item": "minecraft:diamond", "weight": 10.0, "min_count": 1.0, "max_count": 3.0 }
  ]
}

Fields:
  target_loot_table        : full ResourceLocation  (required)
  enabled                  : true/false, default true
  inject_items[].item      : modid:item_name  (required)
  inject_items[].weight    : 0.01-100.0 = % chance per opening, default 10
  inject_items[].min_count : float, default 1
  inject_items[].max_count : float >= min, default 1
  inject_items[].nbt       : SNBT compound, e.g. {display:{Name:'"Label"'}}.
                             Enable F3+H in-game to copy NBT from item tooltips.

Commands  (require OP 2):
  /structureloot reload                    Reload all JSON files without restart
  /structureloot validate                  Check every item ID for errors
  /structureloot export <name>             Export configs as a ZIP profile
  /structureloot import <name>             Import a ZIP profile
  /structureloot debug items <modid>       List items registered by a mod
  /structureloot debug item <modid:name>   Test whether an item ID resolves

Open the GUI editor with the keybind in Controls > Structure Loot Injector.
