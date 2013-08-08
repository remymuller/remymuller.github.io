---
author: remy
comments: false
date: 2010-12-16 09:44:16+00:00
layout: page
slug: motion-following-with-hidden-markov-models
title: Motion Following with Hidden Markov Models
wordpress_id: 11
categories:
- Art
---

The goal of my master thesis was to generalize the idea behind ircam's [score follower](http://recherche.ircam.fr/equipes/temps-reel/suivi/index.html) to the field of dance. The system is based on a video analysis of what is happening on stage done with [eyesweb](http://www.eyesweb.org/), which is compared to an [Hidden Markov Model](http://www.ai.mit.edu/%7Emurphyk/Software/HMM/hmm.html) based on other realizations of the same choregraphy.


## Documents


you can download my [master thesis]({{ site.url }}/downloads/muller-master.pdf) and also browse the [bibliography](http://recherche.ircam.fr/equipes/temps-reel/movement/muller/motion/motion.html) online.

I've made my best to cite references correctly, however I wasn't able to collect all the necessary information for some papers. If something is cited incorrectly please tell me.


## a sample application


using the motion following, we can synchronize a live dance sequence to recorded one:


<object classid="clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B" codebase="http://www.apple.com/qtactivex/qtplugin.cab" width="360" height="304">
    <param name="src" value="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1.mp4" />
    <param name="controller" value="true" /><param name="autoplay" value="false">
    <object type="video/quicktime" data="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1.mp4" width="360" height="304" class="mp4">
        <param name="controller" value="true" />
        <param name="autoplay" value="false">Error text.<br />
    </object><br />
</object> 

  
_video A1 performed by a dancer_
  

<object classid="clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B" codebase="http://www.apple.com/qtactivex/qtplugin.cab" width="360" height="304">
    <param name="src" value="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1b.mp4" />
    <param name="controller" value="true" /><param name="autoplay" value="false">
    <object type="video/quicktime" data="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1b.mp4" width="360" height="304" class="mp4">
        <param name="controller" value="true" />
        <param name="autoplay" value="false">Error text.<br />
    </object><br />
</object> 


_video A1b, the same choregraphy performed by another dancer, with a slightly different timing_
  

  
<object classid="clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B" codebase="http://www.apple.com/qtactivex/qtplugin.cab" width="360" height="304">
    <param name="src" value="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1s.mp4" />
    <param name="controller" value="true" /><param name="autoplay" value="false">
    <object type="video/quicktime" data="http://recherche.ircam.fr/equipes/temps-reel/movement/muller/videos/A1s.mp4" width="360" height="304" class="mp4">
        <param name="controller" value="true" />
        <param name="autoplay" value="false">Error text.<br />
    </object><br />
</object> 



  
_in the upper part: choregraphy A1 below: frames from A1b synchronised to A1._
  


Obviously there are jumps inside the video because the 2 dancers don't perform exactly the way.


## More details


<img src="{{ site.url }}/images/2D4.jpg" alt="" width="640" border="0" />

_4 executions of the same choregraphy performed by 2 different dancers. The trajectory is drawn in the space of the first 2 [principal components](http://ilab.cs.ucsb.edu/projects/turk/Turk%202001.pdf). Colors and point styles represent different steps of the choregraphy._
