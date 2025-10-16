---
layout: post
title: "Progress Is Made"
date: 2009-06-21 17:55:00 +0000
---
<pre>The Emergence game engine has come along nicely. XML is being
used for almost all file formats in the game including the mesh and skeleton
files. The XML format is much more extensible (hence the name) and the core
XML parsing code is much more solid than anything ever found in the Legacy
Engine. The game is strictly NVIDIA PhysX, and the primary math library is the
D3DX Math functions, this is because the ML_lib math library used by Legacy
was pretty much a clone of D3DX math, but not as robust, and so the custom
library was seen as irrelevant.
For the past month the game has come along nicely. The only remnant of the
Legacy engine format is .lw files (Legacy World files), which are not in XML
format, but an XML level format will be developed soon, after which time the
Legacy Engine will be gone.
The lf_sys2 file system is used by the Emergence engine, so technically that
might be a remnant of Legacy, but lf_sys2 has been renamed fs_sys2 and it
was never developed strictly for the Legacy engine anyway. Because of that
LPaKager is still a useful tool, and the lpk a file format is used by Emergence.
There is no LMEdit or clone of LMEdit in the Emergence toolset. This is
because all functionality of that application can be done by hand, just as
easily as by the LMEdit utility (well not just as easily, cut and pasts are
required, and renumbering frames, and manually typing in animation
sequences, but the process is still pretty strait forward.) Also bounding
boxes, etc, are no longer necessary parts of these file formats. So no
utility needs to calculated that information.
Indeed Emergence is almost to the point where Legacy was scrapped, but it is
much more solid and well designed.</pre>
