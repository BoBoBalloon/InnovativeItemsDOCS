# Overview
![logo (old)](https://user-images.githubusercontent.com/61363161/159143095-b7917496-ff45-43d4-9832-baa08281e973.png)

Documentation for Innovative Items, a plugin that makes it possible for those with no Java experience to build their own custom items and abilities.

This plugin has many capabilities from creating custom items and abilities to a developer API that allows users with Java experience to build their own functions.

**Please keep in mind that this plugin depends on the plugin [NBTAPI](https://www.spigotmc.org/resources/nbt-api.7939/).  Without the plugin installed, Innovative Items will not load.**

If you need assistance with the plugin, feel free to [join the support discord here](https://discord.gg/jd2Ew5eHjp).

Configuration examples are listed below as well as links to the proper wiki pages that describe them in more detail.

# Custom Items

Custom items are what makes Innovative Items so amazing. The amount of options you as a server owner are given, allow you to acomplish what you're looking for without spending a lot of time learning Java and the Spigot API. You can make custom items by going into the plugin root folder and then going into the folder named *items*. After you have found the items folder, you can place a .yml file into it. You can add as many .yml files as you like into the folder.  If you have the premium version of the plugin you can have as many items as you like stored in each .yml file. This allows you to organize your items by preference.

An example for an item is provided below, a full overview of the item config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Items):

```
blood-blade:
  material: 'DIAMOND_SWORD'
  display-name: '&4&lBlood Blade'
  ability: 'lifesteal' # would only work if you have an ability with the identifier of "lifesteal"
  custom-model-data: 987
  unbreakable: true
  soulbound: true
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
    ANY:
      GENERIC_MAX_HEALTH: 20
    HAND:
      GENERIC_MAX_HEALTH: 500
      GENERIC_MOVEMENT_SPEED: 50
```

![blood-blade](https://user-images.githubusercontent.com/61363161/121826107-18dfc680-cc84-11eb-8b4b-00195290deca.png)

# Abilities

Abilities allow you to give your custom items extra flavor and provide a greater experience to your players. Just like the items section, you can find the *abilities* folder inside the root directory for the plugin. From there you can place a .yml file into it. You can add as many .yml files as you like into the folder.  If you have the premium version of the plugin you can have as many abilities as you like stored in each .yml file. This allows you to organize your abilities by preference.

An example for an ability is provided below, a full overview of the ability config section can be found [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Custom-Abilities):

```
test-ability:
  trigger: 'right-click'
  cooldown: 20
  show-cooldown: '&cYou can use this ability again in {cooldown}'
  show-cooldown-type: 'ACTION_BAR'
  conditions:
    - 'isclearweather()'
  keywords:
    - 'damage(?player, 1)'
    - 'delay(40)'
    - 'effect(?player, JUMP, 80, 2)'
    - 'particle(?player, FLAME, 20, 0, 0, 0)'
```

# Garbage Collector

When running a server with custom items, it is likely that there will be a balance issue where an item is too strong or too weak. You can change the configuration file to be more fair, but what about all the items currently in circulation? This is where the garbage collection system comes in. This is a very powerful system and should be handled with care, please read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Garbage-Collector).

# Item Defender

When making a minecraft server, it is best to assume that not all your players are knowledgeable about the backend work that is done to make everything run smoothly. Because of this some players may try and use custom items you have made in crafting recipes that will destroy the custom item. After that it would be safe to assume that they would come to you asking for help to give them back their item. But from your perspective this could be a player who is lying to you to get their hands on a valuable item for free. To prevent this from happening, the item defender system was created. You can read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Item-Defender).

# Debug Level

It's in the nature of any customizable plugin that things will go wrong, whether it be from a bug or a configuration syntax mishap.  Because of this, it is important to be able to detect bugs and find out what's going on behind a plugin. This is where debug levels come in. Debug levels as a whole are to assist what type of debug messages are sent in console and what debug messages are ignored. For example, you as a server owner don't care about every little thing the plugin is doing.  You don't want your console getting flooded with information you don't care about. To combat this, you can lower the debug level. The lower the debug level, the less information you are given in console. You can read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Debug-Level).

# Update Checker

When using any plugin, it is important to stay up to date with new changes so you are able to take advantage of new features and improve the quality of your server. But checking spigot constantly for new updates is quite annoying, this is where the update checker comes in. You can read more about it [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Update-Checker).

# Developer API

As shown throughout the rest of the wiki pages and documentation, this is a pretty customizable plugin, it allows those with zero Java experience to make their dreams a reality. But the functionality of the keywords used must come from somewhere? Well, this section of the documentation will go over the keyword manager system and how to create and register your own custom keywords. If you are a Java developer and are interested in adding your own keywords you can take a peek at the tutorial [here](https://github.com/BoBoBalloon/InnovativeItemsDOCS/wiki/Developer-API).
