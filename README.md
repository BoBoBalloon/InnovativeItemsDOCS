# Overview
***DISCLAIMER: THIS PLUGIN IS IN EARLY ALPHA TESTING AND IS INCOMPLETE***

Documentation for Innovative Items, a plugin that makes it possible for those with no Java experience to build their own custom items and abilities.

This plugin has many capabilities from creating custom items and abilities to a developer API that allows users with Java experience to build their own keywords.

**Please keep in mind that this plugin depends on the plugin [NBTAPI](https://www.spigotmc.org/resources/nbt-api.7939/), without it installed, Innovative Items will not load.**

Configuration examples are listed below as well as links to the proper wiki pages that describe them in more detail.

# Custom Items

Custom items are a very large part of what makes Innovative Items so amazing. The amount of options you as a server owner are given allow you to acomplish what you're looking for without spending a lot of time learning Java and the Spigot API. You can make custom items by going into the plugin root folder and then going into the folder named *items*. After you have found the items folder, you can place a .yml file into it. You can put as many .yml files as you like and can have as many items as you like stored in each .yml file. This allows you to organize your items by preference.

An example for an item is provided here, a full overview of the item config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Items):

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&4&lBlood Blade'
  ability: 'lifesteal'
  custom-model-data: 987
  unbreakable: true
  lore:
  - ''
  - '&7&oA blade made of the blood of the &4&ogod of war&7&o...'
  - '&7&oLegend says that it was from a paper cut'
  enchantments:
    DAMAGE_ALL: 150
  flags:
    - 'HIDE_ENCHANTS'
    - 'HIDE_ATTRIBUTES'
  attributes:
    ALL:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

![blood-blade](https://user-images.githubusercontent.com/61363161/121826107-18dfc680-cc84-11eb-8b4b-00195290deca.png)

# Abilities

Abilities allow you to give your custom items extra flavor and provide a greater experience to your players. Just like items, you can find the *abilities* folder inside the root directory for the plugin. From there you you can place a .yml file into it. You can put as many .yml files as you like and can have as many abilities as you like stored in each .yml file. This allows you to organize your abilities by preference.

An example for an ability is provided here, a full overview of the ability config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Abilities):

```
test-ability:
  trigger: 'right-click'
  keywords:
    - 'damage(?player, 1)'
    - 'delay(40)'
    - 'effect(?player, JUMP, 80, 2)'
    - 'particle(?player, FLAME, 20, 0, 0, 0)'
```

# Garbage Collector

When running a server with custom items, there will inevitably be a crazy balance issue where an item is too strong or too weak. You can always change the configuration file to be more fair, but what about all the items currently in circulation? This is where the garbage collection system comes in. This is a very powerful system and should be handled with care, please read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Garbage-Collector).

# Debug Level

It's in the nature of any customizable plugin that things will go wrong, whether it be from a bug or a configuration syntax mishap. Because of this, it is important to be able to detect bugs and find out what's going on under the hood of the plugin. This is where debug levels come in. Debug levels as a whole are just to assist what type of debug messages are sent in console and what debug messages are ignored. For example, you as a server owner don't care about every little thing the plugin is doing, and so you don't want your console getting flooded with information you don't care about. To combat this, you can lower the debug level. The lower the debug level, the less information you are given in console. You can read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Debug-Level).

# Developer API

{explain what it is and add a link to the wiki page} (wiki page has how to add the dependency in maven or gradle and what classes to use)
