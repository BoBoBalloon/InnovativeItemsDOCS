# Overview
Documentation for the Innovative Items plugin, a customizable plugin that can allow people with zero java experience to build their own custom items and abilities!

This plugin has many capabilities from creating custom items and abilities to a developer api that allows users with Java experience to build their own keywords!

Below will show configuration examples and link you to the proper wiki page

# Custom Items

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
