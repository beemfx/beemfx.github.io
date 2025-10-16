---
layout: post
title: "Spawning Entities"
date: 2011-06-11 22:27:00 +0000
---
I have finally created the console command "spawn" this function will spawn any entity from the entity dictionary, at any location desired. This is long due because it it how one could actually design a level with objects in their proper places, that in conjunction with the ability to save. So for example, one would spawn the desired entities at their desired locations. Then save the game, then with a few modifications the save would then be the basis for a level.

Also, because spawn is a console command, a level could be designed through lua scripts. For example, the following lua script generates a triangular stack of barrels (2 is the dictionary entry for a barrel in my demo).

nSize = 10
for i = 1, nSize, 1 do
for j = 1, (nSize-i+1), 1 do
spawn(2, j*0.75 + (i-1)*0.75/2, (i-1)*1.0, 20.0)
end
end

![Image](/assets/b/a/barrels.JPG)

I also worked on a problem that I was experiencing which involved the net message queues filling up too quickly. This especially happened when the client was loading a level and didn't have time to empty the message queue, so the queue got overfilled and clamped. Now the net message queue has priorities for different types of messages. The most frequently posted message is the entity update message which contains information about an entities position and animation. These messages aren't that important though, because if an entity does get updated for a frame or two it really doesn't matter, it will still end up in the correct position eventually and probably with very little lag. However, a message indicating that a new level should be loaded comes much less frequently but it is very important that the client receives that message otherwise the client and server could end up working with two different maps. Now a load message has a higher priority and will always go through, whereas the update message, and other less important messages may not go through.
