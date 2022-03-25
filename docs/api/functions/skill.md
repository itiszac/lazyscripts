# Skill

| **Name**                     | **Args**        | **Return** | **Description**                                      |
| ---------------------------- | --------------- | ---------- | ---------------------------------------------------- |
| GetActiveSkill(left)         | bool            | Skill      | Gets the player's active skill on left or right hand |
| IsSkillActive(left, skillId) | bool<br/>number | Skill      | Checks if the skill is currently active              |
| HasSkill(skillId)            | number          | bool       | Checks if player has a skill by id                   |
| GetSkillLevel(skill)         | Skill           | number     | Gets the current skill level                         |
| GetSkillCharges(skill)       | Skill           | number     | Gets the remaining charges on a skill                |
| SetSkill(left, skillId)      | bool<br/>number |            | Set's the players skill by id on left or right hand  |
