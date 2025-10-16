---
layout: post
title: "Making Noise"
date: 2011-05-13 17:31:00 +0000
---
Today I worked more on the problem of implementing a working door in the game. Specifically with regards to sounds. Previously an entity could only make a sound based off of it's animation. When the appropriate animation hit the specified frame a sound would be played. This was well and good for syncing sounds with animations, but an entity like a door isn't animated, it is a physical object that moves in the world, and so when it needed to play a sound, it's AI had to decided when the sound would be played.

An entity definition file allows sounds to be assigned to the entity. Now, the AI controller interface allows the script writer to play any sound associated with the entity whenever they choose. In the case of the door that I've developed, the sound is played when the door is activated, that way as the door opens it makes door opening sound. This portion of development involved coding on both the client and server side of the application, as well as an additional structure for NetComm.

Also, in developing the ability for an entity to play one of it's sounds. I discovered a bug where the position of the the sound being played was not properly being set. In fact, any time a sound was played, it was played at the last position where it should have been played instead of it's current position. Something I had sort of been aware of since the footstep sounds that I implemented previously seemed to be playing all over the place and not necessarily where the entities were standing.
