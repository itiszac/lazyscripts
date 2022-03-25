# User Types

| **Name**   | **Type**   | **Fields/Methods** | **Description**                                                                                                         |
|------------|------------|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| GameInfo   | string     | gameName           | The game's name                                                                                                         |
|            | string     | gamePassword       | The game's password                                                                                                     |
|            | string     | regionBuffer       | The region buffer                                                                                                       |
|            | string     | gameIpAddress      | The game's Ip Address                                                                                                   |
| UnitAny    | number     | type               | The unit type<br/>0 => Player<br/>1 => Monster<br/>2 => Object<br/>3 => Missile<br/>4 => Item<br/>5 => Tile<br/>6 => XY |
|            | number     | txtId              | The unit text Id                                                                                                        |
|            | number     | id                 | The unit id                                                                                                             |
|            | number     | actId              | The unit's current act id                                                                                               |
|            | PlayerData | playerData         | Points to the unit's PlayerData                                                                                         |
|            | Path       | path               | Points to the unit's Path                                                                                               |
| PlayerData | string     | name               | The unit's name                                                                                                         |
| Path       | number     | offsetX            | The x offset                                                                                                            |
|            | number     | posX               | The x position                                                                                                          |
|            | number     | offsetY            | The y offset                                                                                                            |
|            | number     | posY               | The y position                                                                                                          |
|            | number     | mapPosX            | The map position x                                                                                                      |
|            | number     | mapPosY            | The map position y                                                                                                      |
|            | number     | targetX            | The x target position                                                                                                   |
|            | number     | targetY            | The y target position                                                                                                   |
| Skills     | Skill      | attackSkill        | The attack skill                                                                                                        |
|            | Skill      | leftSkill          | The left skill                                                                                                          |
|            | Skill      | rightSkill         | The right skill                                                                                                         |
|            | Skill      | mercSkill          | The mercenary skill?                                                                                                    |
| Skill      | SkillInfo  | skillInfo          | Points to SkillInfo struct                                                                                              |
|            | Skill      | skillNext          | Points to the next skill in linkedlist                                                                                  |
|            | number     | level              | The skill level                                                                                                         |
|            | number     | charges            | The remaining charges on a skill                                                                                        |
|            | number     | isCharge           | Is a charge skill?                                                                                                      |
| SkillInfo  | number     | id                 | The skill id                                                                                                            |
|            | string     | name               | The skill name  