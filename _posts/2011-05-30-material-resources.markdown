---
layout: post
title: "Material Resources"
date: 2011-05-30 18:53:00 +0000
---
In my last post I hinted that I wanted to redo the way textures and shaders are handled by the renderer. What I wanted to do was make it so that all textures are materials. Materials include properties such as textures, shaders, diffuse colors, specular colors, and other information. Previously the engine allowed textures to be loaded and used directly. Now a texture may still be loaded, but it will be loaded internally as a material with default color values and no shader. So now, instead of having SetTexture, SetShader, and SetMaterial for drawing triangles, there is only one method: SetMaterial. Materials can be loaded in three different ways. The programmer may specify the specifics of a material using a material definition class (CMaterialDef), they may specify a filename pointing to an XML material definition file, or they may specify a filename that points directly to a texture (in which case the material is created internally).

Resource managers for all of these resources have been implemented as well. Thus insuring that a shader, texture, and material get loaded only one time, and are deleted only when all references have been released. So for example, more than one material may refer to more than one shader, but that shader will get loaded only one time (the same goes for textures). And more than one mesh might refer to the same material, but that material will only get loaded one time.

This finally corrects all of the resource management problems I had previously. Now resources are properly deleted in the engine when they are no longer used, whereas, previously, resource cleanup occurred when the game shut-down. Now resource cleanup can properly occur between level loads, for example.
