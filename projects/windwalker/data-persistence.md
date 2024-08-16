---
layout: default
title: Data Persistence
parent: Windwalker
---
### Data Persistence

We utilized SQLite for internal data storage to save randomly pre-generated items and monsters that are then loaded in game as needed. We chose the items to be static instead of randomly generating them during runtime so we could more closely control what types of items the players could receive.

Data is also serialized from objects into JSON files in the autosave Steam Cloud folder to automatically sync the Steam Cloud.

Originally, this was designed as a mobile game and we were going to utilize Firebase Realtime Database as our storage, with Firebase Cloud Functions to verify the authenticity of the user. We had created an API using Node to interface with Unity initially to make those calls.