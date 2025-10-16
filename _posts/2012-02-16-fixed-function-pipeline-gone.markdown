---
layout: post
title: "Fixed Function Pipeline Gone"
date: 2012-02-16 17:32:00 +0000
---
Over the past few months I have been weeding out the fixed function pipeline. Last month all that remained in the FFP was rendering fonts and 2D images. I have now written shaders to handle that type of drawing and the FFP has been completely replaced by the Programmable Pipeline. This is a great improvement because it does away with the need to worry about quite a few render states (such as lighting). It also means that all drawing is done in the same way, so there is less need for branching in the rendering code.
