# Path

All path related functions, enums, and usertypes.

## User Types

| **Name** | **Type** | **Fields/Methods** | **Description**          |
| -------- | -------- | ------------------ | ------------------------ |
| Path     | number   | offsetX            | The x offset             |
|          | number   | posX               | The x position           |
|          | number   | offsetY            | The y offset             |
|          | number   | posY               | The y position           |
|          | number   | mapPosX            | The map position x       |
|          | number   | mapPosY            | The map position y       |
|          | number   | targetX            | The x target position    |
|          | number   | targetY            | The y target position    |
| Exit     | number   | id                 | The exit id              |
|          | number   | type               | The exit type            |
|          | number   | posX               | The exit x position      |
|          | number   | posY               | The exit y position      |
|          | number   | tileId             | The exit tile id         |
|          | number   | levelId            | The exit's level id      |
|          | number   | room2              | The exit's current room2 |

## Functions

| **Name**                                                                | **Args**                                                                       | **Return**                | **Description**                                     |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------- | --------------------------------------------------- |
| GetPath(levelId, currentX, currentY, destX, destY, reducerType, radius) | number<br />number<br />number<br />number<br />number<br />number<br />number | number<br />vector<POINT> | Returns a number and vector or list of coordinates. |
| GetArea(levelId)                                                        | number                                                                         | number<br />vector<Exit>  | Returns a vector or list of exits.                  |

### GetPath(levelId, currentX, currentY, destX, destY, reducerType, radius)

---

Usage:

```lua
local player = GetPlayer()
local levelId = GetPlayerLevelId()
local nodes, path = GetPath(levelId, player.path.posX, player.path.posY, player.path.posX + 20, player.path.posY + 50, 0, 10)
PrintConsole("There are " .. tostring(nodes) .. " nodes in the path.")
```

Returns a tuple of the number of nodes in the path and a list of all the coordinates in the path.

### GetArea(levelId)

---

Usage:

```lua
local levelId = GetPlayerLevelId()
local n, exits = GetArea(levelId)
PrintConsole("There are " .. tostring(n) .. " exits in the level.")
```

Returns a tuple of the number of exits in the level and a list of all the exits in the level.
