---
layout: post
title: "Another Log Entry"
date: 2011-05-09 18:13:00 +0000
---
<pre>I finally did something with doors, that is there is now a door in the game that
opens and closes. It is currently not controlled by the player, but runs on a
timer, but it is a step in the correct direction. Also, it confirmed my
suspicions that the AI needs to be updated every frame for a smooth animation
as opposed to the every 5 frames that it was updating for usual AI updates. This means I
will need some kind of mechanism for transferring AI updates around.
Also, I changed the mtree file type, it no longer exists, but was merged with
the edef file type. This was to make defining new entities easier, since
realistically every mtree would belong to only one edef anyway. I also want to
create a tool that will generate an edef based upon a mesh, and I want to get
default mesh textures working so that skins and materials don't necessarily need
to be defined. That way at a minimum all that would be needed for a simple
object would be a mesh, texture, and definition file.</pre>
