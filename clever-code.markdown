---
layout: page
title: "Clever Code"
permalink: /clever-code/
---
## countof operator

In C++ the sizeof operator is pretty handy. 
It is also useful to know the size of an array. The countof operator is 
useful for that, here’s how you define it:

{% highlight C++ %}
#define countof(a) (sizeof(array) / sizeof(0[(array)]))
{% endhighlight %}

And an example of how it could be used:

{% highlight C++ %}
SomeStruct myStruct[] = { {value1,value2} , {value1_1,value2_1} };
for (int i = 0; i < countof(myStruct); i++)
{
   myStruct[i].TheValueA = SomeNewValue;
}
{% endhighlight %}

