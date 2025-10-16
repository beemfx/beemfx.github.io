---
layout: post
title: "Normal Mapping"
date: 2011-08-04 20:44:00 +0000
---
The newest feature implemented in the game is normal mapping (a form of bump mapping). This is a method for creating more detail in a rendered mesh without actually creating more geometry.
In the early days of computer graphics, lighting wasn't calculated at all, later, lighting was calculated on a per vertex basis, today, graphics cards are capable of calculating lighting on a per pixel basis, and normal mapping is one form of doing that.

Lighting can be computing using the normal vector of a surface, in combination with the direction that the light is coming in. On a per vertex basis, this is a fairly easy computation since vertices typically have a normal attached to them. On a per pixel basis this is a little more difficult, since each pixel doesn't have a vertex attached to it, and that is where the normal map comes in. The normal map is loaded as if it were a texture, but each pixel in the texture is treated as if it were a normal.

[caption id="" align="aligncenter" width="409"]![Image](/assets/b/u/bump2.JPG) An example of a normal map.[/caption]

From there is seems like it would be easy to calculate lighting based on that. Wrong. Consider that a texture is actually "wrapped around" a mesh. So each normal in the texture isn't actually the normal of the pixel we are rendering. It's a normal that doesn't take any regard to the orientation of the vertex.

Therein is the problem with normal mapping. It is necessary to transform the per-pixel normal into the space of the vertex. Or, alternatively, transform the direction of the light into the space of the vertex, which is a more useful computation.

Transforming a light vector requires an orthogonal transformation into the vector's tangent space. And for this to be accomplished a tangent vector must be computed for each vertex. The tangent vector depends upon the normal of the vertex, in combination with the orientation of the texture about that vertex. It's a lot of linear algebra, and theory that I don't want to explain, but after programming a complex algorithm, the tangent vector is now computed in the Emergence engine, which in turn can be used for per pixel lighting in a pixel shader. The result is thus,

[caption id="" align="aligncenter" width="469"]![Image](/assets/b/u/bump1.JPG) Note that the spherical surface on this gun is not dependent upon mesh geometry, but rather it is depended upon the normal map (as seen above). The results look much more dramatic in the actual engine where you can move through different light sources.[/caption]
