---
layout: post
title: "AI Controllers"
date: 2011-05-24 19:13:00 +0000
---
Alright, I implemented the ability for one AI to access the AI controller of another entity. The main reason I did this was so that when the door that I've implemented is activated it can tell from what direction the activating entity is activating it from. In this way the door can decide to open inwards or outwards for a more natural door opening reaction. That is, the door opens away from the activator. That way a player wouldn't have to move out of the way when opening a door that swings towards it.

Of course one AI activating another will also have other useful benefits for other AI operations such as implementing weapons, shooting, conversations, etc.
