# Overview
***WARNING, THIS PLUGIN IS IN EARLY ALPHA TESTING AND IS INCOMPLETE IN ALMOST EVERY WAY***

Documentation for the Innovative Items plugin, a customizable plugin that can allow people with zero Java experience to build their own custom items and abilities!

This plugin has many capabilities from creating custom items and abilities to a developer API that allows users with Java experience to build their own keywords!

Below will show configuration examples and link you to the proper wiki page

# Custom Items

Custom items are a very large part of what makes Innovative Items so amazing, the amount of options you as a server owner are given allow you to acomplish what you're looking for without spending a ton of time learning Java and the Spigot API. You can make custom items by going into the plugin root folder and than going into the folder named *items*. After you have found the items folder, you can place a .yml file into it. You can put as many .yml files as you like and can have as many items as you like stored in each .yml file. This allows you to organize your items however you want.

An example for an item is provided here, a full overview of the item config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Items):

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&r&4&lBlood Blade'
  ability: 'lifesteal'
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

# Abilities

Abilities allow you to give your custom items a bit of extra flavor and provide a far greater experience to your players. Just like items, you can find the *abilities* folder inside the root directory for the plugin. From there you you can place a .yml file into it. You can put as many .yml files as you like and can have as many abilities as you like stored in each .yml file. This allows you to organize your abilities however you want.

An example for an ability is provided here, a full overview of the ability config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Abilities):

{put example config here} //TODO
