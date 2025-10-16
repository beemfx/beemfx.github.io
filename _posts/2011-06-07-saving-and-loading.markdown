---
layout: post
title: "Saving and Loading"
date: 2011-06-07 20:37:00 +0000
---
Today I made progress on the ability of the game to save and load data. Previously it could only load data, but now it can save. This has actually created some interesting caveats, as it is questionable as to what data should be saved. Currently the game is only saving basic data about the level and about the entities, though it has the potential to save a lot more data. I also eliminated the .pinfo XML files from the engine. These were files that described additional PhysX data for the game. I combined the important parts of that file into the entity dictionary file format (.edict) because it seemed more fitting for those descriptors to be in those files since they only affected entities.

The groundwork has been laid for saving, but I'm going to have to decide further what I wanted to do with the saving ability. For example, how much PhysX data should be saved. Clearly it would be nice to save velocities and torque since it would be very weird to save a game with an object flying through the air, then load it with the object standing still in the air. I'm also running into problems with the way the player entity is saved, because the player controlled entity is treated differently throughout the game than the other entities. What I'm thinking is to create a special save tag for saving the player entity. Then when a client connects it uses that data to load the player entity. Doing so would also solve some other "hard-coded" items that are currently in place.
