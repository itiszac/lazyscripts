# Unit

| **Name**                                | **Args**                                  | **Return** | **Description**                           |
| --------------------------------------- | ----------------------------------------- | ---------- | ----------------------------------------- |
| GetPlayer()                             | None                                      | UnitAny    | Gets my player's unit                     |
| GetPlayerHealthPercent()                | None                                      | number     | Gets my player's current health percen t  |
| GetPlayerManaPercent()                  | None                                      | number     | Gets my player's current mana percent     |
| GetUnitName(unit)                       | UnitAny                                   | string     | Gets the unit's name                      |
| GetUnitPosX(unit)                       | UnitAny                                   | number     | Gets the unit's x position                |
| GetUnitPosY(unit)                       | UnitAny                                   | number     | Gets the unit's y position                |
| GetUnitIdByCoords(posX, posY, room2)    | number<br/>number<br/>Room2               | number     | Gets the unit id at the given coordinates |
| GetUnitByTypeClass(typeId, classId)     | number<br/>number                         | UnitAny    | Gets the unit of the given type and class |
| IsUnitAlive(unit)                       | UnitAny                                   | boolean    | Checks if the unit is alive               |
| GetUnitStatValue(unit, statId, layerId) | UnitAny<br/>number<br/>number             | number     | Gets the unit's stat value                |
| MoveUnit(run, x, y)                     | boolean<br/>number<br/>number             | None       | Moves the unit to the given position      |
| UseSkillOnUnit(left, shift, type, id)   | boolean<br/>boolean<br/>number<br/>number | None       | Uses a skill from given hand on the unit  |
| UseSkillAtPosition(left, posX, posY)    | boolean<br/>number<br/>number             | None       | Uses the skill at the given position      |
| PacketSkillAtPosition(left, posX, posY) | boolean<br/>number<br/>number             | None       | Uses the skill at the given position      |
| InteractWithWaypoint(waypointId)        | number                                    | None       | Interacts with the given waypoint         |
