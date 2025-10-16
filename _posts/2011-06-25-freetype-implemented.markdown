---
layout: post
title: "FreeType Implemented"
date: 2011-06-25 21:47:00 +0000
---
One problem I've revisited many times within the game engine was implementing fonts for outputting text. Fonts are used to render the console. Fonts pose a difficult problem and there are many ways to implement them. I've tried manually created fonts, this has presented quit a few problems. One way to do this is by creating an individual case for each letter. Another way is to create a single font containing all the characters, and some way of calculating where each character is located (this is the method I previously attempted). In either case there must be some sort of algorithm or data file to specify how each letter is to be loaded. I had generally gotten bad results using these methods. The fonts looked terrible and it was difficult to create new fonts.

My solution to this had been to use the ID3DXFont interface. This is a font renderer specific to Direct3D. This worked well enough, and the console looked alright with it. However, I was not satisfied using something so dependent upon Direct3D. In creating this game engine I have been designing it to be easily portable, but the ID3DXFont interface is obviously not portable to anything outside of Direct3D, and it is dependent upon the Windows Font library as well.

The solution to this was to use the FreeType library, an open source library for loading and rendering fonts. I used this in conjunction with the newly implemented ability to draw on Render Targets to create a font engine for the game. The font engine now works by loading a font file, which can be packaged into an LPK file (whereas ID3DXFont mostly used fonts that were registered in Windows), and then the font engine creates a texture containing the characters of that font (currently it creates the standard ANSI characters, but it is designed so that it could easily work with any UNICODE character set). While it is creating this texture it also stores information about where each character is stored, as well as other properties for rendering.

The results have turned out quite well, and in fact the CFont class that I created is a little more robust than the ID3DXFont interface as it allows fonts to be scaled dynamically as they are drawn. I must admit I'm actually surprised out how sharp the fonts look considering the results that I in previous attempts at creating a font engine.

This is also the last specific rendering code that was Direct3D depended an it has now been eliminated. Due to that it would be very easy to port the engine to OpenGL or some other API if necessary. Part of the reason I worked on fonts was to go back to developing the "window" system in the game, and hopefully create some kind of main menu soon.
