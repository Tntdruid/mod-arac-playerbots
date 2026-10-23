# ![logo](https://raw.githubusercontent.com/azerothcore/azerothcore.github.io/master/images/logo-github.png) AzerothCore
## ARAC Playerbots - All Races All Classes for mod-playerbots
# ![ARAC icon](https://raw.githubusercontent.com/azerothcore/mod-arac/master/icon.png)
- Latest build status with AzerothCore and mod-playerbots: [![Build Status](https://github.com/Tntdruid/mod-arac-playerbots/workflows/core-build/badge.svg?branch=master&event=push)](https://github.com/Tntdruid/mod-arac-playerbots)

A fork of [mod-arac](https://github.com/heyitsbench/mod-arac) for servers running [mod-playerbots](https://github.com/mod-playerbots/mod-playerbots). It works on servers without playerbots too.

## Screenshot

![arac](https://raw.githubusercontent.com/azerothcore/mod-arac/master/images/screen1.png)

![arac](https://raw.githubusercontent.com/azerothcore/mod-arac/master/images/screen2.png)


# Usage

- Make a backup of your database before using this module.
- Apply [the SQL query](https://github.com/Tntdruid/mod-arac-playerbots/blob/master/data/sql/db-world/arac.sql) to your `world` database.
- Update your DBC files (client and server) contained in the release, so add [**Patch-A.MPQ**](https://github.com/Tntdruid/mod-arac-playerbots/blob/master/Patch-A.MPQ) to your WoW/Data/ directory and update the DBC files in your server/data/dbc/ directory with the ones contained in [the DBFilesContent directory](https://github.com/Tntdruid/mod-arac-playerbots/tree/master/patch-contents/DBFilesContent).
- Restart the worldserver. The `skilllineability_dbc` changes are only loaded at startup.

# Playerbots

Random bots pick their race and class from `playercreateinfo`, so with this module they are also created with the new race and class combinations.

Bots learn their spells from class trainers, and trainers only teach a spell to the races listed in `SkillLineAbility.dbc`. This module overrides those rows in `skilllineability_dbc` so the following spells follow the faction instead of the race:

| Class | Alliance races | Horde races |
|---|---|---|
| Shaman | Heroism | Bloodlust |
| Paladin | Seal of Vengeance | Seal of Corruption |
| Paladin | Warhorse and Charger | Thalassian Warhorse and Charger |

Existing bots learn these spells on their next level up. Existing players learn them from their class trainer.

# Need help?

If you encounter a bug, please [open an issue](https://github.com/Tntdruid/mod-arac-playerbots/issues/new).
     

## Credits

* [iThorgrim](https://github.com/iThorgrim)
* [heyitsbench](https://github.com/heyitsbench) for [mod-arac](https://github.com/heyitsbench/mod-arac)
* [Tntdruid](https://github.com/Tntdruid) for the playerbots changes

AzerothCore: [Repository](https://github.com/azerothcore) - [Website](http://azerothcore.org/) - [Discord chat community](https://discord.gg/PaqQRkd)
