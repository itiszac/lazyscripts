# Unit

All Unit and Player related functions, enums, and usertypes.

## User Types

| **Name**   | **Type**   | **Fields/Methods** | **Description**                                                                                                         |
| ---------- | ---------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| UnitAny    | number     | type               | The unit type<br/>0 => Player<br/>1 => Monster<br/>2 => Object<br/>3 => Missile<br/>4 => Item<br/>5 => Tile<br/>6 => XY |
|            | number     | txtId              | The unit text Id                                                                                                        |
|            | number     | id                 | The unit id                                                                                                             |
|            | number     | actId              | The unit's current act id                                                                                               |
|            | PlayerData | playerData         | Points to the unit's PlayerData                                                                                         |
|            | Path       | path               | Points to the unit's Path                                                                                               |
| PlayerData | string     | name               | The unit's name                                                                                                         |

## Player specific Functions

| **Name**                                | **Args**                                  | **Return** | **Description**                          |
| --------------------------------------- | ----------------------------------------- | ---------- | ---------------------------------------- |
| GetPlayer()                             | None                                      | UnitAny    | Gets my player's unit                    |
| GetPlayerHealthPercent()                | None                                      | number     | Gets my player's current health percent  |
| GetPlayerManaPercent()                  | None                                      | number     | Gets my player's current mana percent    |
| GetPlayerLevelId()                      | None                                      | number     | Gets my player's current level id        |
| MoveUnit(run, x, y)                     | boolean<br/>number<br/>number             | None       | Moves the unit to the given position     |
| UseSkillOnUnit(left, shift, type, id)   | boolean<br/>boolean<br/>number<br/>number | None       | Uses a skill from given hand on the unit |
| UseSkillAtPosition(left, posX, posY)    | boolean<br/>number<br/>number             | None       | Uses the skill at the given position     |
| PacketSkillAtPosition(left, posX, posY) | boolean<br/>number<br/>number             | None       | Uses the skill at the given position     |
| UseWaypoint(waypointId)                 | number                                    | None       | Interacts with the given waypoint        |
| InteractWithUnit(typeId, unitId)        | number<br/>number                         | None       | Interacts with the given unit            |

### GetPlayer()

---

Usage:

```lua
local player = GetPlayer()
local playerName = player.name
PrintConsole("My player's name is: " .. playerName)
```

Returns the player's UnitAny usertype.

### GetPlayerHealthPercent()

---

Usage:

```lua
local health = GetPlayerHealthPercent()
PrintConsole("My player's health is: " .. tostring(health))
```

Returns the player's current health as a percentage.

### GetPlayerManaPercent()

---

Usage:

```lua
local mana = GetPlayerManaPercent()
PrintConsole("My player's mana is: " .. tostring(mana))
```

Returns the player's current mana as a percentage.

### GetPlayerLevelId()

---

Usage:

```lua
local levelId = GetPlayerLevelId()
PrintConsole("My player's level id is: " .. tostring(levelId))
```

Returns the player's current level id.

### MoveUnit(run, x, y)

---

Usage:

```lua
local player = GetPlayer()
MoveUnit(false, player.path.posX + 5, player.path.posY + 5)
```

Moves the unit to the given position by either running or walking.

### UseSkillOnUnit(left, shift, type, id)

---

Usage:

```lua
local andariel = GetUnitByTypeClass(1, 156)
UseSkillOnUnit(true, true, 1, andariel.id)
```

Uses a skill from the given hand and shifted or unshifted and on the specified unit id and type.

### UseSkillAtPosition(left, posX, posY)

---

Usage:

```lua
local player = GetPlayer()
UseSkillAtPosition(false, player.path.posX + 5, player.path.posY + 5)
```

Uses a skill from the given hand at a given position.

### PacketSkillAtPosition(left, posX, posY)

---

Usage:

```lua
local player = GetPlayer()
PacketSkillAtPosition(false, player.path.posX + 5, player.path.posY + 5)
```

Sends a packet to use a skill from the given hand at a given position. (This is the same as UseSkillAtPosition but without animation of the skill being used.)

### InteractWithWaypoint(waypointId)

---

Usage:

```lua
UseWaypoint(0x23)
```

Takes the waypoint with the given id and interacts with it.

### InteractWithUnit(typeId, unitId)

---

Usage:

```lua
local interactId = GetUnitIdByCoords(exit.posX, exit.posY, room2)
InteractWithUnit(5, interactId)
```

Interacts with an entity of the given type and id.

## Unit specific functions

| **Name**                                | **Args**                      | **Return** | **Description**                           |
| --------------------------------------- | ----------------------------- | ---------- | ----------------------------------------- |
| GetUnitName(unit)                       | UnitAny                       | string     | Gets the unit's name                      |
| GetUnitPosX(unit)                       | UnitAny                       | number     | Gets the unit's x position                |
| GetUnitPosY(unit)                       | UnitAny                       | number     | Gets the unit's y position                |
| GetUnitIdByCoords(posX, posY, room2)    | number<br/>number<br/>Room2   | number     | Gets the unit id at the given coordinates |
| GetUnitByTypeClass(typeId, classId)     | number<br/>number             | UnitAny    | Gets the unit of the given type and class |
| IsUnitAlive(unit)                       | UnitAny                       | boolean    | Checks if the unit is alive               |
| GetUnitStatValue(unit, statId, layerId) | UnitAny<br/>number<br/>number | number     | Gets the unit's stat value                |

### GetUnitName(unit)

---

Usage:

```lua
local player = GetPlayer()
local playerName = GetUnitName(player)
PrintConsole("My player's name is: " .. playerName)
```

Returns the specified unit's name as a string value.

### GetUnitPosX(unit)

---

Usage:

```lua
local player = GetPlayer()
local playerXFromFunc = GetUnitPosX(player)
local playerXFromVar = player.path.posX

PrintConsole("My player's x position is: " .. tostring(playerXFromFunc) .. " and " .. tostring(playerXFromVar))
```

Returns the specified unit's x position as a number value.

### GetUnitPosY(unit)

---

Usage:

```lua
local player = GetPlayer()
local playerYFromFunc = GetUnitPosY(player)
local playerYFromVar = player.path.posY

PrintConsole("My player's y position is: " .. tostring(playerYFromFunc) .. " and " .. tostring(playerYFromVar))
```

Returns the specified unit's y position as a number value.

### GetUnitIdByCoords(posX, posY, room2)

---

Usage:

```lua
local player = GetPlayer()
local levelId = GetPlayerLevelId()
local n, exits = GetArea(levelId)
if exits ~= nil then
    for i = 1, n do
        local exit = exits[i]
        local exitLevelId = exit.id
        local room2 = exit.room2
        local targetLevelId = GetNextLevel(exits, n)
        if exitLevelId == targetLevelId then
            local unitId = GetUnitIdByCoords(exit.posX, exit.posY, room2)
            PrintConsole("Unit id at " .. tostring(exit.posX) .. ", " .. tostring(exit.posY) .. " is: " .. tostring(unitId))
        end
    end
end
```

Returns the unit id from the given coordinates and room.

### GetUnitByTypeClass(typeId, classId)

---

Usage:

```lua
local andariel = GetUnitByTypeClass(1, 156)
local posX = andariel.path.posX
local posY = andariel.path.posY
PrintConsole("Andariel's x position is: " .. tostring(posX) .. " and y position is: " .. tostring(posY))
```

Returns the unit usertype from the given unit type and unit class id.

### IsUnitAlive(unit)

---

Usage:

```lua
local andariel = GetUnitByTypeClass(1, 156)
if IsUnitAlive(andariel) then
    PrintConsole("Andariel is alive!")
else
    PrintConsole("Andariel is dead!")
end
```

Returns a boolean value indicating if the specified unit is alive.

### GetUnitStatValue(unit, statId, layerId)
