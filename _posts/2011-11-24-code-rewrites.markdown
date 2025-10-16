---
layout: post
title: "Code Rewrites"
date: 2011-11-24 20:27:00 +0000
---
I have mentioned that until I can really start getting content into the game there isn't that much to do with the game engine. Really to make a game with it, most of the programming necessary would be to write AI and scripting. Without designers and artists there isn't much AI to program, so I haven't been doing much with the game engine as of recent.

I did go ahead and rewrite a lot of the code. Well, not completely rewrote it, but I'm trying to make many of the "modules" within the game more independent of each other, and more object oriented.

Get this, I have a string class for the game, which is used for basic string manipulation, it was depending on the file class, which is used for opening and closing files, which in turn was dependent on the string class. I'm working hard to get rid of all such dependencies.

The other independence I worked on is with the Renderer. I would very much like to have the Renderer 100% independent from all Emergence tech except for the IRenderer interface. Currently it is still dependent upon global variables for it's internal settings (such as screen width, height, etc). My ultimate goal is to have it so that the Renderer could be contained in a separate DLL, kind of the way Unreal technology did things. That way I could create new renderers of different types (DX11, for instance), and even more importantly, port the renderer to other platforms. The D3D renderer that I've currently implemented is dependent upon Windows, so I'm trying to abstract it as much as possible. It won't be hard to port to the 360 renderer, and as for Playstation, I really have no idea, since I haven't dealt with PS3 rendering tech at all.
