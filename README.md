# Overview
Documentation for the Innovative Items plugin, a customizable plugin that can allow people with zero java experience to build their own custom items and abilities!

This plugin has many capabilities from creating custom items and abilities to a developer api that allows users with Java experience to build their own keywords!

Below will be summaries of the capabilities of this plugin.

# Custom Items

In this section we will talk about how to build custom items for the Innvative Items plugin! Now lets get started, all items must have a name and a material, without them, the item will fail to load. An example is provided here:

```
blood-blade:
  material: 'DIAMOND_SWORD'
```

This will create a custom item by the name of *blood-blade* with the material value of a *diamond sword*

But this is not all you can do, you can also make a display name and lore to make your item look pretty:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
```

As shown above you set the display name using the *display-name* field and set the item lore using the *lore* field

These fields also support color codes as shown above, you can find all the color codes [here](https://minecraft.tools/en/color-code.php)

On top of that there is also support for enchantments, lets say we wanted to give the blood blade item sharpness 150, that would be as easy as this:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
```

Now under the *enchantments* field you can see I put "DAMAGE_ALL", instead of sharpness, this is because the internal names for enchantments dont match their display names. A list of all enchantments and their internal names can be found [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html)

Another field that this plugin supports is item flags, item flags can be used to hide enchantment displays, hide leather armor dye, and much more, they just make items look a lot more appealing. For example, if we wanted to hide the "Sharpness 150" text in the item lore, we could do this:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
  flags:
    - 'HIDE_ENCHANTS'
```

A list of all valid item flags and their usage can be found [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html)

