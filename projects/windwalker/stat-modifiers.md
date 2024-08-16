---
layout: default
title: Stat Modifiers
parent: Windwalker
---
### Stat Modifiers

Stats were an interesting problem to solve. Initially, we utilized a regular C# properties to get and set them, but came across issues when doing the calculations. We then pivoted to utilizing a modifier stack, where each Stat was a class that contained a list of StatModifiers, which had a stat value, type of modification(percent vs. flat), and a source indication to track where the stat modification was from. This ended up working well to add/remove stats.

Equipment made use of these stat modifiers to apply them.