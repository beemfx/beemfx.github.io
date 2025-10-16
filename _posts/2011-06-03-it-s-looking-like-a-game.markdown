---
layout: post
title: "It's Looking Like A Game"
date: 2011-06-03 20:17:00 +0000
---
I'm please to say that the Emergence engine is starting to look like a game. Not that it did before, but now there is more to do besides walking around and looking at the sights. I developed an AI for guns, an explosion for where the gun shoots, and I modified several of the AI so that they now react to the gun.

Most of this work required only modding the game, but I did change some of the source code. For example, the explosion that I made for the gunshot is a sprite explosion, but I decided that the best way to animate it would be to put all the frames in one texture, and then use a vertex shader to choose appropriate texture coordinates to make the static texture look like an animation.

Previously HLSL scripts had access to a global variable g_fTime which would always store the current time of the game. This was useful for animating pixel shaders, but the problem I had was that every single pixel shader used the exact same time so they would all animate together. I modified the source code so that the g_fTime value is now the number of seconds since the object being rendered was created. So in the case of my explosion, the explosion will start it's animation at the first frame, and advance through the frames for the longevity of the explosion. It looks quite cool, and I'm happy to say that it turned out much as I expected it to.
