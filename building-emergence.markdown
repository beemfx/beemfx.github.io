---
layout: page
title: "Building Emergence"
permalink: /building-emergence/
---
<!-- wp:heading -->
<h2>Getting the Source </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The first thing to do is to get the source 
code and data for Emergence. Emergence is source controlled using 
Perforce. If you are not an employee of Beem Software you will not be 
able to take this step as you won’t have a login.<br><br>
You can obtain P4V from <a href="http://www.perforce.com/downloads/helix#product-9">the Perforce Website</a>. You only need P4V, but P4VS will also come in handy if you are a coder using Visual Studio.<br><br>
When you run P4V you are usually prompted to open a connection. If you 
are an employee you will have been provided with an address for the 
server a login id and password. Remember that the server address needs 
the port. The first time logging in you may leave Workspace blank. Once 
you are logged in, on the depot tab you should see the depot that you 
have access to.<br><br></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Creating a Workspace </h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You’ll need a workspace in order to 
obtain the source files locally. To do this click Connection-&gt;New 
Workspace. Choose the directory where you want the code to go, and give 
the workspace a relevant name such as USERNAME-EMERGENCE, etc.<br><br>
We recommend checking rmdir in the advanced options, but this is not 
required. You may also want to change your workspace mapping, but this 
is recommended only for those comfortable with the use of Perforce.<br><br>
With the workspace created you can right click on the depot and select Get Latest Revision. You should do this daily.<br><br></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2> Building The Game </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You need Visual Studio installed to build 
the game. Being the Beem Software is currently non-profit, we use Visual
 Studio 2013 Community Edition. You can download it <a href="https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx">from Microsoft for free</a>.<br><br></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3> Setting Build Paths </h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The build process for Emergence requires 
environment variables to be set in order for the game to build properly.
 To do this open the system panel of Control Panel, click Advanced System Settings. (In windows 7 just open the start menu and type advanced system settings and you’ll find it). Click Environment Variables.
 You need to create two environment variables. You can do this for 
either your account or for the system. It doesn’t really matter.<br><br>
The first is EGOUT it needs to be set to whatever directory you want the game to build to for example D:\Projects\Emergence\Build\
 (don’t include quotes). The other one is EGSRC it should be set to the 
location where you synced the perforce depot and the Emergence Directory
 within that (it should be whatever directory all.sln is in).<br><br></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3> Building the Game </h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>If you synced the code and set the 
environment variables you should be able to build the game easily. In 
the Emergence directory of the depot is a file all.sln. Double clicking 
that should open it with Visual Studio, so long as you have that 
installed.<br><br>
If you are running Visual Studio for the first time be sure to set the work type to C++.<br><br>
With the project open in visual studio you should be able to build the 
project. In the solution explorer right click egame and select Set as StartUp Project. You should be able to press F7 to build the game.

</p>
<!-- /wp:paragraph -->
