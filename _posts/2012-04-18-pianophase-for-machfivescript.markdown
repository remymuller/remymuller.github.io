---
author: remy
comments: false
date: 2012-04-18 12:31:21+00:00
layout: post
slug: pianophase-for-uviscript
title: Piano phase for UVIScript
wordpress_id: 264
categories:
- code
- music
tags:
- Falcon
- UVIScript
- phase
- piano
- reich
- script
- steve
---

Here's a very small script that regenerates [Steve Reich](http://en.wikipedia.org/wiki/Steve_Reich)'s [_Piano phase_](http://www.youtube.com/watch?v=JW4_8KjmzZk) piece for 2 pianos in [Falcon](http://www.uvi.net/falcon.html) using [UVIScript](http://www.uvi.net/uviscript/) to generate the phasing piano parts. 

<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F43538091"></iframe>

    
{% highlight lua %}
pattern = {64, 66, 71, 73, 74, 66, 64, 73, 71, 66, 74, 73}
vels    = {80, 80, 70, 70, 50, 80, 80, 70, 70, 80, 50, 70}
    
function play(period, channel)
    local i=1
    while true do
        local note = pattern[i]
	local vel = vels[i] * (1+0.1*math.random())
	playNote(note, vel, beat2ms(period/2), 0, channel)
        waitBeat(period)
        i = 1+i%#pattern
    end
end
    
spawn(play, 1/3, 1)
spawn(play, ((12*12+1)/(12*12)) * 1/3, 2)
{% endhighlight %}



_N.B.: It doesn't follow exactly the instructions: the second piano parts advance continuously by one step every 12 bars, and there's no real articulation._
