---
layout: default
title: Skills
parent: "2021-2023 Windwalker"
---
### Skills

To create a flexible system of skills, we chose to utilize a number of interfaces and composition to create different types of skills. These interfaces allowed us to support the types of skills we wanted. Each skill was also a Scriptable Object that we could then slot into a Job or potentially a weapon to provide access to the skills. This applies to both Passive and Active Skills. 

We didn’t end up implementing any, but the passive skills were setup to be able to execute actions during the upkeep and end states of the player.

Active Skill Interfaces

![Active Skills](/assets/images/active-skills-interfaces.png)

Sample Skill

![Sample Skill](/assets/images/sample-skill.png)