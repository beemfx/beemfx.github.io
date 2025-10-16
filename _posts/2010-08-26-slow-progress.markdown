---
layout: post
title: "Slow Progress"
date: 2010-08-26 18:04:00 +0000
---
<pre>Well, I haven't updated this log in a long time but I am
still working on the engine. Scripting has been implemented to some degree.
Graphs were added to the map format, and I developed an AI that will follow a
graph, it won't take multiple paths, just the first one that it finds. For
that reason a path must be circular.
Also, I've worked on sound quite a bit, but some core problems with the game
design are making that very difficult. I wanted to assign sounds to an
entity based on the animation, so a certain sound would play when a certain
frame of animation of the skeleton was played. This didn't work because as far
as the game is concerned animations are played based on percentages, not
actual frames. For that reason I'm still working on the same idea, but the
percentage of the animation where the sound should be played needs to be
estimated.
I've also rewritten a lot of the video code. The texture manager has been
seriously updated, also I fixed some issues where the device could not be
reset. Many other code problems have been repaired as well.
I mentioned in the start of this log that some of the problems with Legacy was
that it was trying to be too ambitious, and unfortunately parts of Emergence
are too ambitious as well. It's just so hard for me to try to be really basic.
In all honesty, I could probably build a working demo in a few months, but I'm
putting a lot of work into the finer details that might not be so important.
I started developing a window system, that could be used for menus and
interface items. This replaced the old CDrawPad that I had, which was way too
intertwined with the CVideo class. Now it is much more independent. The graphic
console was also ported to the new window system, and that seems to be a better
choice as windows are more streamlined for use in the engine, than an independent graphic object.
I am kind of disappointed at how little I've worked on this engine this summer.
I wanted to put a lot more work into it. It's going to be difficult to work on
the engine while school is in. I suppose the main thing I really need to do
is get sound worked out, and built some kind of basic demo where you can at
least shoot some entities dead.</pre>
