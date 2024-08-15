---
title: "Windwalker"
date: 2024-08-14
layout: archive
project_name: "Windwalker"
---

**Tools used:**

- **Game Engine**
    - Unity 2022.2.1f1
- **Code Repository/Version Control**
    - [Github](https://github.com/RevDev-Studios/WindWalker)
- **Release Platform**
    - [Steam](https://store.steampowered.com/app/2377890/Windwalker/)
- **Persistence**
    - SQLite
    - Steam Cloud
- **UI/UX Design**
    - Figma

### Steam Deployments:

- We utilize Steam for deploying our game and for the player’s data persistence.
![Steam Deployment](/assets/images/steam-deployments.png)

---

### Turn Based Combat

This is the main combat loop to allow for resolution of skills and attacks in a turn based manner. We used a finite state machine structure to allow actors(player, allies, and enemies) to go from state to state.

![Turn-Based Combat](/assets/images/turn-based-combat.png)

---

### Unity Addressable Assets and Scriptable Objects:

Unity has an asset management system that they built called Addressables. This is built on top of their original Asset Bundle structure and was intended to make the access of assets simpler and handle the memory management better. The theory was that we would load/unload assets as they were needed. 

Before this, we had primarily used lists or dictionaries that were pre-loaded in the editor with the assets. Then we would access them directly. This worked, but we wanted to try out the Addressable approach. Because the assets were pre-loaded, the memory was also pre-allocated for those assets, potentially using up resources for no reason.

---

### Jobs

Jobs are a higher level Scriptable Object that define the skills, stats, etc.

The core part of each Job are the passive skills and the active skills. Generally, the passive skills provide overall stat bonuses for specific type of weapons and the active skills are the ones that buff, debuff, heal, or deal damage during combat.

| Mage           | Warrior    | Ranger        
|:-|:-|:-|
| Necromancer    | Knight     | Marksman      
| Elementalist   | Berserker  | Windwalker    
| Priest         | Spellsword | Beastmaster   

---

### Skills

To create a flexible system of skills, we chose to utilize a number of interfaces and composition to create different types of skills. These interfaces allowed us to support the types of skills we wanted. Each skill was also a Scriptable Object that we could then slot into a Job or potentially a weapon to provide access to the skills. This applies to both Passive and Active Skills. 

We didn’t end up implementing any, but the passive skills were setup to be able to execute actions during the upkeep and end states of the player.

Active Skill Interfaces

![Active Skills](/assets/images/active-skills-interfaces.png)

Sample Skill

![Sample Skill](/assets/images/sample-skill.png)

---

### Status Effects

Status Effects are a Scriptable Object that define effects like Stun, Bleed, etc. that can occur on every turn. We also utilize a similar approach as the skills, using interfaces and composition to build the status effects, but the status effects are more focused on different times during the combat phases on when they are applied. Some status effects are applied immediately, some persist throughout the next turns.

---

### Stat Modifiers

Stats were an interesting problem to solve. Initially, we utilized a regular C# properties to get and set them, but came across issues when doing the calculations. We then pivoted to utilizing a modifier stack, where each Stat was a class that contained a list of StatModifiers, which had a stat value, type of modification(percent vs. flat), and a source indication to track where the stat modification was from. This ended up working well to add/remove stats.

Equipment made use of these stat modifiers to apply them.

---

### Data Persistence

We utilized SQLite for internal data storage to save randomly pre-generated items and monsters that are then loaded in game as needed. We chose the items to be static instead of randomly generating them during runtime so we could more closely control what types of items the players could receive.

Data is also serialized from objects into JSON files in the autosave Steam Cloud folder to automatically sync the Steam Cloud.

Originally, this was designed as a mobile game and we were going to utilize Firebase Realtime Database as our storage, with Firebase Cloud Functions to verify the authenticity of the user. We had created an API using Node to interface with Unity initially to make those calls.