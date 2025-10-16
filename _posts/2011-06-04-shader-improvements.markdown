---
layout: post
title: "Shader Improvements"
date: 2011-06-04 20:11:00 +0000
---
I recently read that in most cases the view transform (D3DTS_VIEW) should not actually be used, as it is faster computationally to combine the view and world transforms into a single matrix, so I implemented that. In doing so, however, it was necessary to work with shaders, and I made some major improvements there.

I've mentioned that certain matrixes and other data are shared across all shaders. This is accomplished by using an ID3DXEffectPool interface which is shared by all shaders. But in order to initially define the matrixes it was necessary to load at least one shader with the matrices declared. Previously I had done this by including a file off the disk, but this presented the inherit problem that that file might not be copied over for a given mod, and it required an explicit path.

Now I have changed my implementation of ID3DXInclude to include resource files. Specifically one resource called base.fx. Now any shader may use the preprocessor command "#include &lt;base.fx&gt;" (using caret brackets as opposed to quotes), and the contents of that internal file will be included in their effect file. The effect will then have access to all of the internally defined structures such as the various transform matrices, and the g_fTime variable that I talked about in the last post. Standard includes using quotes still worked as they did before and will include any other fx file that is within the file system.

On the server side of things I removed an issue where objects that had their physics disabled were still being hit by raycasts.
