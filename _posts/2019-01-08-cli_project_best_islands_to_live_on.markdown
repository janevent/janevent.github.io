---
layout: post
title:      "CLI Project: Best Islands To Live On"
date:       2019-01-09 02:50:07 +0000
permalink:  cli_project_best_islands_to_live_on
---



I know how important it is to complete things, because I tend towards the opposite.  It's not for lack of trying.  I like to draw the working process out until the end, and then push the end to tomorrow,  and then tomorrow evening...   Honestly, even actually starting can be daunting.  You can read all the supporting material, watch all the instructional videos and search for the right website to scrape, before you have even created a github repository.

After a few hiccups of setting up a working environment,  I found that looping through elements from my chosen website was not going to be straightforward.  At first, I created a new instance of the class Island every time I iterated over a name, but I didn't know how to connect the instance with the other attributes, the facts about the islands.  (By the way my project is about the Best Islands To Live On,  because I like good vibes).  The facts were in a seperate node from the name.  After consulting with my cohort lead, I went to the container, #article-body, and iterated over all the lis.  If an li had the name of an Island, I created a new instance and stored it in a variable.  If the li had a list of facts, I assigned the facts to the instance variable attributes.

I had a similar predicament when I wanted to add a descriptive attribute.  There were about two paragraphs per Island, and each paragraph in a seperate li.  This time, I stored the paragraphs in an array.  For each paragraph, I would assign it to an attribute of the instance of Island,  paragraph_1 or paragraph_2, and add it onto the array.  I would then clear the array when it's length was 2.    This works swell if there are always 2 paragraphs per island.  But one island had 3.  I used conditionals to skip over this paragraph.   I know there must be a better way, so if any one wants to share their ideas, please do!

In short, it feels nice to complete something, for now!

In case you are interested in checking out the html, the website I scraped is at [https://www.islands.com/top-20-best-islands-to-live-on/]
