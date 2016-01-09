---
layout: post
title:  "Printing in Python. Again."
date:   2016-1-9 21:45:30 +0700
categories: jekyll update
---
Printing in Python

{% highlight python %}
my_name = 'Gema Bujangga'
my_age = 31 # honestly?
my_height = 165 # centimetres (metric rules!)
my_weight = 56 # kilograms
my_eyes = 'black'
my_teeth = 'yellow'

print "Let's talk about %s" % my_name
print "He is %d centimetres tall" % my_height
print "He's got %s eyes, %s teeth and weighted about %d kilograms" % (my_eyes, my_teeth, my_weight) 

{% endhighlight %}