---
layout: post
title: "Progress Update: Decorative Entities"
date: 2011-04-02 18:06:00 +0000
---
To give a little background on what this post is about, let me explain what entities are. An entity in a game is basically anything that is not part of the map. Entities include player and AI controlled characters, objects sitting on the ground, torches hanging on a wall, pretty much anything you see that wouldn't be classified as a wall, the floor, or the ceiling. Some games refer to these as actors, in the Emergence Engine they are referred to as entities.

In the Emergence Engine, entities are declared using an entity definition file (with the extension .edef). These are XML files that describe how an entity is to work within the game. Until today, entities were all physics objects, meaning that they all reacted to gravity, collisions, and so forth. They all moved around in the world.

However, it was necessary to have "decorative entities", that is, entities that don't react to the physical world, they are merely in it, and they are visible. In PhysX these are called static actors. Typically static actors occupy space, and other actors will collide into them, but they themselves will not move. Actors can also be set up to ignore all collisions.

The Emergence Engine now employs these possibilities. In the physics tag of the XML file, the property "type" may now be set to three possible values: normal, static, or disabled. Here is an example: &lt;physics type="disabled"/&gt;. With this setting the entity is merely in the world, and it does not react to any collisions, or gravity. With the type static, the entity occupies space, but does not move if bumped into. With the normal type (or if no type is specified) the entity reacts to collisions.

This was important because in a game world there are many entities that are decorative only, and they are best served when their physics is either static or disabled. One reason I wanted to get this implemented was to show off the pixel shader technology in the game engine. I had developed a water pixel shader, but previously the only way to show it off was to create an entity of water. This had an interesting effect though, in that if something bumped into the water, the water would slide around the room. Now the water entity can be defined as having no physics, and bumping into it will do nothing. (Actual water that you can swim around in is not implemented, and will not be handled by entities. The water entity is only the visuals of the water surface.)

Check out the water.

[caption id="" align="aligncenter" width="473"]![Image](/assets/e/w/ewater.JPG) The water pixel shader.[/caption]

Along with this new feature for entities, quite a bit of code was rewritten as well. I renamed a few classes with names that make more sense. For example, entity definitions were referred to as entity templates, and their associated class was CEntT, which is a class name that didn't make much sense. I renamed that class CEntDef, which makes quite a bit more sense.

To give you an idea of how entity definitions work, the .edef file defines and entity. It is loaded by the CEntDef class. Then, each save game references an entity dictionary. An entity dictionary is a list of entity definitions. This is also an XML file. So what the game does when a new save game is loaded (or a new level) is that it loads the entity dictionary, the dictionary in turn loads all the definitions. Then when an entity is to be spawned, the game refers to the dictionary file to get the definition, which is then used to create the entity. Admittedly, it is somewhat complicated, and it is actually more complicated than what I just described, because there are other physics properties to be concerned about, which are declared in another XML file altogether, but it has to be complicated in order to allow the most functionality.
