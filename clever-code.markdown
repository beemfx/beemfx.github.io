---
layout: page
title: "Clever Code"
permalink: /clever-code/
---
<!-- wp:heading {"level":3} -->
<h3> countof operator </h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In C++ the sizeof operator is pretty handy. 
It is also useful to know the size of an array. The countof operator is 
useful for that, here’s how you define it:<br><br>
#define countof(a) (sizeof(array) / sizeof(0[(array)]))<br><br>
And an example of how it could be used:<br><br>
SomeStruct myStruct[] = { {value1,value2} , {value1_1,value2_1} };<br><br>
for( int i=0; i&lt;countof(myStruct); i++ )<br>
{<br>
   myStruct[i].TheValueA = SomeNewValue;<br>
}<br><br></p>
<!-- /wp:paragraph -->
