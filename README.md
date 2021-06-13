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

Another feature provided by this plugin is support for attributes, attributes can be used to change and set basic values for this item and the player using it. This plugin handles attributes in an interesting way, this is because buffs (or debuffs) given by attributes are on an equipment slot basis, meaning it would have a different effect when held in your main hand slot vs. your chestplate slot. This is useful if you want to make armor that buffs the users damage, but you dont want it to buff their damage when held in their hand. An example of attributes is provided below:

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
  attributes:
    ALL:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

This example would make it so when a player was holding the blood blade in their main hand, the base value of their max health would increase by 520 (because the *ALL* field is in addition to, not in place of) and the base value of their movement speed would increase by 50. A list of MOST valid equipment slots can be found [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/EquipmentSlot.html) (keep in mind that *ALL* is also a valid option, it just does not appear on the provided list). A list of valid attributes, can be found [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html)

On top of that there is also support for custom model data in case you have your players using a custom texture pack, an example can be found here:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  custom-model-data: 987 #LOOK HERE!!!
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
  flags:
    - 'HIDE_ENCHANTS'
  attributes:
    ALL:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

The example above has the *custom-model-data* field, this would set the custom model data of the blood blade item to 987.

Additionally, we also provide support for making items unbreakable, an example can be found here:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  custom-model-data: 987
  unbreakable: true #LOOK HERE!!!
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
  flags:
    - 'HIDE_ENCHANTS'
  attributes:
    ALL:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

The example above shows how to use the *unbreakable* field to make an item unbreakable, if you want your item to not be unbreakable, there is no need to include this field as all items have this field set to false by default.

Last but not least, we also provide support for linking custom abilities written by you, to be linked to the items you create, an example can be found here:

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  ability: 'lifesteal' #LOOK HERE!!!
  custom-model-data: 987
  unbreakable: true
  lore:
  - '&r&7&oA blade made of the blood of the god of war...'
  - '&r&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
  flags:
    - 'HIDE_ENCHANTS'
  attributes:
    ALL:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

The example above would link the ability by the name of *lifesteal* to the blood blade item

Keep in mind,, not all these values are required, the only required value is the material field and the name field, as long as those are present, the item will load.
