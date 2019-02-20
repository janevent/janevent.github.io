---
layout: post
title:      "CLI Project Redo"
date:       2019-02-20 17:49:09 +0000
permalink:  cli_project_redo
---


I wrote a previous post about my first CLI project that did function once upon a time.  

It ceased to work. My cohort lead spotted that the website I was using was using React and not Javascript.  So I installed a Capybara_Scraper and thought everything would be fine.  Unfortunately, the css selectors I was using weren't returning the data they were supposed too.  This was because the html on the website I was scraping had changed. Those selectors are obsolete now.

My scraper class was much easier to write this time around, and honestly I needed the practice!  I was able to instantiate new Island objects in the scrape_island_attributes method.  For every node that I looped over I could create an instance and write all of it's attribute values.  




