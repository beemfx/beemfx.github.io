---
layout: post
title: "Lights and Clients and Servers"
date: 2011-06-06 21:53:00 +0000
---
The first thing I did today was actually fix a lighting problem that had been introduced when I changed the way world and view matrixes worked. I found that it was necessary to multiply a light's direction by the view matrices rotation matrix explicitly. The Emergence Game Engine uses only direction lights even though other light types are available in Direct3D. The engine itself handles computing lighting dynamically and finishes up by feeding a direction light to the device.

The other thing I worked on today was the client-server relationship. When I originally developed the engine my main focus was insuring that entities and other real-time updates occurred correctly. So my main focus had been insuring that the client and server communicated appropriately with those, but now that I am moving into developing an actual game demo it was necessary to improve other facets of communication between the client and server.

One thing that the game had been doing previously, was that it loaded one demo level, and that was it. It was the only level loaded in the game, and loading a different level involved quitting the game, changing a text file, then restarting the game.

I have now introduced the console command "server.load("filename")" which instructs the server to load a new level. This took a lot more work than simply issuing the order, as it was necessary for the server to notify the client that a new level had been loaded, and in turn the client had to notify the server that it went ahead and loaded the new level. Also, it turned out I had a problem when I was unloading a level on the server side, the server was not properly destroying active entities. It was only adding them to the removal que, but that que was never being processed. It is now.

This whole process of loading a new level required quit a bit of communication between the client and server, although it didn't require many changes to the in-place structures. I'm pleased that it is working. I need to run some testing to make sure it is working properly, and try to account for any unexpected inputs and so forth, but it seems to be in pretty good shape.

I'm hoping to have a more interesting tech demo up shortly, something much more exciting than the last one.
