---
layout: post
title: "AI Controller Progress"
date: 2011-06-02 19:15:00 +0000
---
I pretty much exclusively worked on AI Controllers today. AI Controllers are how the plugin-able DLL communicates with the game server, they are what allow the game to be mod-able.

I added three new features to the AI controller. An AI can now cause it's associated entity to be removed from the game, it can cause another entity to be spawned into the game, and it can change it's physical properties.

These new features were necessary to begin developing a first person shooter demo. So for example say you want a shooter. That shooter could previously do a raycast, but now it could, for instance create a bullet hole at the location where it hit, then that bullet hole could delete itself after a certain amount of time. Or if an enemy character was hit by the weapon it could change it's physical properties so that it no longer collided with anything, and essentially becomes a static dead entity.

Most of the actual engine work was simple, but I did have to modify the AIs and create some new AIs to experiment with and test the new features. So I created a shootable AI, that simple adds an impulse whenever it get's shot so it will bounced around when it get's shot as seen in many games. I also modified my "Hell Trooper" AI, so that when it get's shot it plays a death animation then turns static so that it is no longer affected by the ingame physics.

Finally I can say that the engine is looking like a real game that you can do something besides walk around in.
