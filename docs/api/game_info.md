# Game Info

All game info related functions, enums, and usertypes.

## User Types

| **Name** | **Type** | **Fields/Methods** | **Description**       |
| -------- | -------- | ------------------ | --------------------- |
| GameInfo | string   | gameName           | The game's name       |
|          | string   | gamePassword       | The game's password   |
|          | string   | regionBuffer       | The region buffer     |
|          | string   | gameIpAddress      | The game's Ip Address |

## Functions

| **Name**      | **Args** | **Return** | **Description**            |
| ------------- | -------- | ---------- | -------------------------- |
| GetGameInfo() |          | GameInfo   | Gets the current game info |

### GetGameInfo()

---

Usage:

```lua
local gameInfo = GetGameInfo()
local gameName = gameInfo.gameName
local gamePassword = gameInfo.gamePassword
local regionBuffer = gameInfo.regionBuffer
local gameIpAddress = gameInfo.gameIpAddress

PrintConsole(gameName .. " " .. gamePassword .. " " .. regionBuffer .. " " .. gameIpAddress)
```

This function returns the current game info.
