---
layout: post
title:      "What I Learned at Flatiron: Problem Solving as It Relates to Living"
date:       2020-07-27 04:50:03 +0000
permalink:  what_i_learned_at_flatiron_problem_solving_as_it_relates_to_living
---

# **Debugging:**

An instructor at Flatiron School described applying debugging techniques to one’s own life, and that got me thinking.  First of all, thank you! Yes!

I think there is a time to let your mind rest and wander, play, and potentially stumble across discoveries.  I’m even going to go out on a limb and say it is healthy.  That’s often how I was able to solve tests.  I let my mind rest and stopped trying so hard. 

There is also a time to zoom in on the task at hand.  Which brings us to..

**Debugging in a Few Steps:**

1. * Establish what it is that you are trying to do.  Actually state the desired outcome.
2. * What is blocking you from this outcome?  Identify the problem.
3. * What is your educated guess about what could solve this?
4. * Test your hypothesis.  If you were wrong, use what you learnt to make another more fine tuned guess about what could be a possible solution .

**Tips for Debugging: **

* Use search engines to find credible answers to your questions.
* Ask yourself why, how and what?
* One thing leads to another (sometimes searching the wrong question can lead me to being able to formulate a better question, and sometimes gaining more understanding on one matter, leads me to asking more questions)

All the above can be applied to solving buggy code or to solving one of life’s little conundrums.

**Enter Speel - Debugging Me:**
(Feel free to skip ahead to the Planning of an Application header, because this gets a little bit embarrassing for me.)

```
{  1. What AM I trying to do?: Wake up earlier. ( For the sake of brevity I will not go into why, although I think that is     important to know why we want to do something. )
}
​
{ 2. & 3. What is blocking me from waking up: [ { 
   block: not hearing or remember an alarm going off,
   possible_solutions: [ setting multiple alarms, placing them across the room ] 
}, { 
   block: deciding to let myself and kids sleep as much as possible so as to avoid getting sick, 
   possible_solution_with_blocks: {  
      solution: sleep earlier,
			blocks: [ excess caffeine intake, numerous evening tasks, energized from rushing to complete tasks, numerous    interruptions causing things to take longer and sometimes adding to frustration, seeking alone/quiet time, habitual night owl, habit of watching YouTube or shows, grazing habits  ]
      }
}, {
   block:  getting up can sometimes feel like getting hit on the head with a piece of plywood,   
   possible_solutions: [ “ “]
 },{ 
   block:  sometimes feeling winded and having shortness of breath,
   possible_solutions: [ take a preventative asthma inhaler daily ]
 } ] }
```
	
So, some solutions seem obvious, and others appear ominous.  Let’s dive into one of the ‘sleep earlier blocks’ at index 1,  ‘numerous evening tasks’, which is an array.  

Filter through list of tasks:
```
let remaining_tasks = evening_tasks.filter( (task) => // task that can not be moved to another time of day )
```

Let’s apply a few of the plausible solutions to me, the experiment:
* Stop caffeine intake after 1 pm
* Set and strategically place multiple alarms
* Redistribute evening tasks to other times of day. E.g.,
* * Dinner clean up
* * Laundry
* * Provide ample and accessible snacks to my children right before bed time
* * Set a study limit time
* * Correspondence 
* Use inhalers once a day

# **Planning of an Application:**
I like to sketch out a plan of my application and then bury it sand and let it manifest itself.  Same with my 10 year plan.  That which I don’t remember wasn’t too important.

I am kidding of course--sort of.

If we map out ahead of time what the minimal expectation of our application is it can be easier to debug when bugs arise. We know what is a bug (what we don’t want) because we know what we do want.  

I can use the same logic when setting goals. For instance, if I don’t set a goal to work as a web developer and designer, and design a strategy to make this happen,  I won’t be able to identify the bugs in my life. 

To go back to the web application example, when we pause to write a plan, we are giving ourselves a plan to follow through with.  Things might not go exactly as we wish, but we can work to create a minimal viable product, and smooth out any wrinkles as we code along.


