# Skill

All skill related functions, enums, and usertypes.

## User Types

| **Name**  | **Type**  | **Fields/Methods** | **Description**                        |
| --------- | --------- | ------------------ | -------------------------------------- |
| Skills    | Skill     | attackSkill        | The attack skill                       |
|           | Skill     | leftSkill          | The left skill                         |
|           | Skill     | rightSkill         | The right skill                        |
|           | Skill     | mercSkill          | The mercenary skill?                   |
| Skill     | SkillInfo | skillInfo          | Points to SkillInfo struct             |
|           | Skill     | skillNext          | Points to the next skill in linkedlist |
|           | number    | level              | The skill level                        |
|           | number    | charges            | The remaining charges on a skill       |
|           | number    | isCharge           | Is a charge skill?                     |
| SkillInfo | number    | id                 | The skill id                           |
|           | string    | name               | The skill name                         |

## Functions

| **Name**                     | **Args**        | **Return** | **Description**                                      |
| ---------------------------- | --------------- | ---------- | ---------------------------------------------------- |
| GetActiveSkill(left)         | bool            | Skill      | Gets the player's active skill on left or right hand |
| IsSkillActive(left, skillId) | bool<br/>number | bool       | Checks if the skill is currently active              |
| HasSkill(skillId)            | number          | bool       | Checks if player has a skill by id                   |
| GetSkillLevel(skill)         | Skill           | number     | Gets the current skill level                         |
| GetSkillCharges(skill)       | Skill           | number     | Gets the remaining charges on a skill                |
| SetSkill(left, skillId)      | bool<br/>number |            | Set's the players skill by id on left or right hand  |

### GetActiveSkill(left)

---

Usage:

```lua
local leftSkill = GetActiveSkill(true)
local rightSkill = GetActiveSkill(false)
```

Returns the players left and right hand skill.

### IsSkillActive(left, skillId)

---

Usage:

```lua
local hammers = IsSkillActive(true, 112)

if hammers then
    PrintConsole("You have the hammer skill on your left hand")
end
```

Returns a boolean value whether the player has a skill active on the hand specified.

### HasSkill(skillId)

---

Usage:

```lua
if HasSkill(112) then
    PrintConsole("You have the hammer skill")
end
```

Returns a boolean value whether the player currently has a skill by id.

### GetSkillLevel(skill)

---

Usage:

```lua
local leftSkill = GetActiveSkill(true)
local skillLevel = GetSkillLevel(leftSkill)
PrintConsole("Your left skill level is " .. tostring(skillLevel))
```

Returns the current skill level of the skill specified.

### GetSkillCharges(skill)

---

Usage:

```lua
local rightSkill = GetActiveSkill(false)
local chargesRemaining = GetSkillCharges(rightSkill)
PrintConsole("Your right skill has " .. tostring(chargesRemaining) .. " charges remaining")
```

Returns the value of charges remaining on the skill specified.

### SetSkill(left, skillId)

---

Usage:

```lua
if HasSkill(0x70) and not IsSkillActive(true, 0x70) then
  SetSkill(true, 0x70)
end
```

Sets the skill specified by id on the left or right hand.
