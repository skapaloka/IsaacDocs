# File "entities2.xml"

This page needs some content. You can contribute to it using the Edit Button!

old tutorial: [https://www.reddit.com/r/themoddingofisaac/comments/36o00t/entitys_explained_how_to_add_entity_variants/](https://www.reddit.com/r/themoddingofisaac/comments/36o00t/entitys_explained_how_to_add_entity_variants/)

**Resource-Folder**{: .xmlInfo }: Using this file in a resource folder of a mod is not tested yet.

**Content-Folder**{: .xmlInfo }: Using this file in a content folder of a mod is not tested yet.


| Variable-Name | Possible Values | Description |
|:--|:--|:--|
| name | str | Name of the entity, used in the `spawn` command and the bestiary. |
| id | int | Type of the entity. Max Value: 4095 |
| variant | int | Variant of the entity. The maximum value is 4095. If you leave this blank, then the game will automatically chose the next available number. |
| subtype | int | SubType of the entity. The maximum value is 255. (The reason for this is that the hash map generator of the .stb format expects a specific bit-depth.) |
| anm2path | string | path to the anm2 file, relative to the given anm2root. Example: `001.000_Player.anm2` |
| baseHP | int ||
| boss | int |Entity is a boss. Possible values: ['0', '1'] |
| bossID | int ||
| champion | int |Allow champion variants of this entity. Possible values: ['0', '1'] |
| collisionDamage | float ||
| collisionMass | float ||
| collisionRadius | float | Radius of the collision circle. This value is used for both entity <--> entity and entity <--> grid collisions. This changes the `Entity.Size` field. |
| collisionRadiusXMulti | float | Multiplier for the X direction of the collision circle. This can be used to grant an entity an elliptical hitbox |
| collisionRadiusYMulti | float | Multiplier for the Y direction of the collision circle. This can be used to grant an entity an elliptical hitbox |
| collisionInterval | int | Number of game ticks till the next collision should be evaluated. Default = 1 |
| numGridCollisionPoints | int | Number of points along the edge of the collision circle, which are used to detect collisions with grid entities. |
| friction | float | "Slippyness" of the entity. Default = 1. The entity's velocity is multiplied by this every update.|
| shadowSize | int ||
| stageHP | int ||
| tags | string | possible values: ['nodelirium', 'spider', 'explosive_soul', 'cansacrifice', 'ghost', 'brimstone_soul', 'homing_soul', 'fly', 'noreroll']<br>See Chapter below for in depth explanations of the tags. |
| gridCollision | string | possible values: ['nopits', 'ground', 'none', 'walls', 'floor'] |
| portrait | int | The frame that an entity's death portrait is on in the anm2 file for enemy's bestiary entries.|
| hasFloorAlts | bool | If set to true, floor specific sprites should be used for this entity if they exist. See the chapter below for more informations |
| reroll | bool | If set to true, the entity can be rerolled with D10 and similar effects. |
| shutdoors | bool | If set to true, the entity needs to be defeated for the doors to open. |
| shieldStrength | int | The amount of boss armor that an enemy will have.|
| gibAmount | int ||
| gibFlags | string | used Values: ['poop'] |
| bestiary | bool | If set to true, the entity will appear in the bestiary under its own entry. `besitaryAnim` and `besitaryOverlay` are used only if this is true. |
| bestiaryAnim | string | The animation played while the entity is selected in the bestiary.|
| bestiaryOverlay | string | The overlay animation that will be played on top of the `besitaryAnim`. Not required. |

## Tags explanation

| Stage-Name | Suffix |
|:--|:--|
|cansacrifice| Marks familiars on which sacrificial altar can be used on|
|nodelirium| Blacklists a boss from being used by Delirium|
|fly|Indicates enemies which should be neutralized by Skatole and charmed by Beelzebub|
|spider|Indicates enemies which should be neutralized by Bursting Sack|
|ghost|Indicates enemies which Vade Retro can kill at <50% HP as a special interaction|
|noreroll| Immunity from D10 rerolls|
|brimstone_soul| (*Usage currently unknown*. might be scrapped feature for Hungry Soul or Vade Retro)|
|explosive_soul| (*Usage currently unknown*. might be scrapped feature for Hungry Soul or Vade Retro) |
|homing_soul| (*Usage currently unknown*. might be scrapped feature for Hungry Soul or Vade Retro) |


## Floor specific sprites
If an entity has the attribute `hasFloorAlts` set to `true`, the game tries to load the spritesheet of the entity with an additional suffix, based on the current stage. The Suffix of a stage is defined in the `suffix` attribute in the stages.xml file. If no sprite can be found, it will load the default spritesheet.

**Example:**
Original Gaper sprite: monster_017_gaper.png

Downpour Sprite: monster_017_gaper_downpour.png

**Suffix per stage:**

| Stage-Name | Suffix |
|:--|:--|
|Flooded Caves|_downpour|
|Downpour|_downpour|
|Dross|_dross|
|Ashpit|_ashpit|
|Mausoleum|_mausoleum|
|Gehenna|_gehenna|
