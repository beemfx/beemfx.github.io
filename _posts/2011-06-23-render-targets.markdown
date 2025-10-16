---
layout: post
title: "Render Targets"
date: 2011-06-23 21:54:00 +0000
---
For a while now I've been experimenting with various techniques using render targets. That is, the usual render target is called the back buffer, you can draw a game simply by drawing to the back buffer directly, but it is also possible to render to a texture that has been created as a render target. This allows for various possibilities such as a mini-map display, mirrors, video playback, and so forth. I have been working on the implementation of render targets within the game. Previously my implementations had been experimental and sporadic, but I now have a much better system implemented that is not dependent upon Direct3D.

The main reason I have been working on these is because I want to develop a "window" system for the game so that I can create menus and so forth. (Actually, I have already implemented a "window" system, and the console is part of that system, but it is heavily dependent upon Direct3D, and I want to create a more generic system.)
