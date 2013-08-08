---
author: remy
comments: false
date: 2010-12-16 09:47:48+00:00
layout: post
published: true
slug: maxmsp-externals-with-objectivec
title: Max/MSP Externals with ObjectiveC
wordpress_id: 13
categories:
- Science
- Code
---

yes, it's possible because ObjectiveC is a strict superset of C. You  just need to use a *.m extension so that Xcode compiles it as ObjectiveC  and not just C.

I already used C++ to write maxmsp externals so I knew it should be  possible with another C based language. But I needed a proof of concept.  here it is:

{% highlight objc %}
#include "ext.h"
#import 

@interface Fraction : NSObject
{
  int num;
  int den;
}
- (void) setNumerator: (int) d;
- (void) setDenominator: (int) d;
- (int) numerator;
- (int) denominator;
- (void) print;
@end

@implementation Fraction
- (void) setNumerator: (int) d
{
  num = d;
}
- (void) setDenominator: (int) d
{
  den = d;
}
- (int) numerator
{
  return num;
}
- (int) denominator
{
  return den;
}
- (void) print
{
  post("%i/%i",num,den);
}
@end

typedef struct
{
  t_object o;
  Fraction *frac; // to show how we can store an ObjectiveC instance inside a C struct.
} objc_t;

static t_messlist *objc_class = NULL;

static void *objc_new(Symbol *s, short ac, Atom *at)
{
  objc_t *o = (objc_t *)newobject(objc_class);
  Fraction *frac = [[Fraction alloc] init];
  [frac setNumerator: 1];
  [frac setDenominator: 4];
  [frac print];
  o->frac = frac;
  return o;
}
static void objc_free(objc_t *o)
{
  Fraction *frac = o->frac;
  if(frac)
  {
    [frac release];
  }
}
int main(void)
{
  setup(&objc;_class,
        (method)objc_new,
        (method)objc_free,
        (short)sizeof(objc_t), 0L,
        A_GIMME, 0);
}
{% endhighlight %}
