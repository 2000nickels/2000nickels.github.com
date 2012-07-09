---
layout: post
title: "Hypercritical Length"
date: 2012-07-08 20:49
comments: true
categories: 
---

On the [Hypercritical](http://5by5.tv/hypercritical) podcast, John Siracusa often worries his podcast is too long.  Personally, I like the long episodes, but as they say, "It's his show."  Let's look at the data.

There are two main questions we can ask about Hypercritical's length:

**The Goal:** In [episode #51](http://5by5.tv/hypercritical/51), John said, "That's my personal goal, that I want to try for something shorter."  Are the episodes after #51 are shorter than the earlier episodes?

**The Jinx:** When John says he is planning a short show, sometimes it becomes one of the  longest episodes. (At 2 hours and 14 minutes, I'm looking at you, [#68: Patent Hands](http://5by5.tv/hypercritical/68).)  Are the *short* shows longer than the *not-short* shows?  Does he jinx it by declaring it a short show?  

### The Data

I collected all the Hypercritical episode lengths, then I started listening to the beginning of each episode.  (Forgive me Dan, but I *might* have listened at double speed.  It was in the name of science.)  I started at episode [#75: Just a Dinosaur](http://5by5.tv/hypercritical/75), and worked my way back to [#51: Unjustified Confidence](http://5by5.tv/hypercritical/51), where John declared his goal (definitely not a New Year's resolution) to have shorter shows.

Of those 25 post-goal episodes, I counted 8 where John said it was going to be a short show or his time was limited: #51, #52, #60, #68, #71, #72, #74, and #75.  These are the *short* episodes, regardless of the actual length.  That leaves 16 *not-short* episodes, ignoring #54, which was the 1 minute public service announcement for the [Kindacritical special](http://5by5.tv/specials/4).

Putting all the data together, here's a plot of the episode lengths, colored by type: *pre-goal*, *short*, and *non-short*.  I can see by eye that the *post-goal* episodes are not shorter than the *pre-goal* episodes, but I can't tell if the "short show" jinx is true.   Let's dig in further.

{% img /images/hypercritical_length_scatter_plot.png Plot of episode lengths %}


### The Goal

When we plot the cumulative distributions of the *pre-* and *post-goal* shows, it's very obvious that the *post-goal* shows are not shorter, by any measure.  After stating his goal, John is not getting any worse (that is, the maximum length has stayed at 135 minutes), but the median episode length has increased from 85 to 106 minutes.

{% img /images/hypercritical_length_goal_cdf.png Cumulative distribution of pre- and post-goal shows %}


### The Jinx

The interesting question is: can John jinx the show by saying it will be short?  The data here is a little more complicated.  In the cumulative distribution plot below, we can see both the *short* and the *not-short* episode lengths.  While 2 out of 3 of the longest episodes were in the *short* group, the median episode length is 7 minutes less when he calls it a "short" show.  Also, 4 of the 5 shortest episodes belong to the *short* group, and the average *short* show is 103 minutes versus 109 minutes for the *not-short* shows.  So, we can disprove the jinx; when John says it will be a short show, I'm going to bet that it will be shorter.

{% img /images/hypercritical_length_short_cdf.png Cumulative distribution of pre- and post-goal shows %}

Let me express my thanks to John Siracusa and Dan Benjamin for making the Hypercritical podcast.  Long or short, I look forward to it every week.
