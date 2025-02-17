---
title: Status Effects
---
### Status Effects

Status Effects are a Scriptable Object that define effects like Stun, Bleed, etc. that can occur on every turn. We also utilize a similar approach as the skills, using interfaces and composition to build the status effects, but the status effects are more focused on different times during the combat phases on when they are applied. Some status effects are applied immediately, some persist throughout the next turns.