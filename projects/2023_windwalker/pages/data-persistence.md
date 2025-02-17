---
title: Data Persistence
---
### Data Persistence

We utilized SQLite for internal data storage to save randomly pre-generated items and monsters that are then loaded in game as needed. We chose the items to be static instead of randomly generating them during runtime so we could more closely control what types of items the players could receive.

Data is also serialized from objects into JSON files in the autosave Steam Cloud folder to automatically sync the Steam Cloud.
