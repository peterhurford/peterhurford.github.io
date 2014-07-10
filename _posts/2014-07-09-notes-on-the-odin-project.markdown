---
author: admin
comments: true
date: 2014-07-09 20:57:00-06:00
layout: post
slug: odin-project
title: "A Better Way to Learn Programming? Notes on The Odin Project"
categories:
- Programming
---

I'm currently working as a computer programmer at a start-up in Chicago.  I'm getting paid to write code.  It's pretty neat.  Most notably, I was not a Computer Science major in college, and I only took two CS classes.  I got the job nearly entirely through about 700 hours of self study.

Best of all, you can do it too!

I [wrote a guide on how to go from "zero to hero"](http://everydayutilitarian.com/essays/learn-code/) in computer programming.  I got a lot of people I know who program to contribute.  I think it's a pretty good guide, linking a few resources together into a coherent curriculum.  In fact, I think it is the best guide you could find, short of working full-time to develop a complete online curriculum of their own.

Well, turns out someone did work full-time to develop a complete online curriculum of their own.

Enter **[The Odin Project](http://www.theodinproject.com)**.

Visit there, and [find a complete curriculum](http://www.theodinproject.com/courses?ref=home), focused on Ruby on Rails, that takes you from zero to hero in a fulfulling way.  Best of all, they focus on doing projects, so you actually learn by doing.

I went through it and now, after a few months, I've completed the curriculum in entirety.  I must say, I'm forced to admit defeat.  I find it much easier, more thorough, and more motivating than my own guide.  I recommend people follow through it instead of follow my own guide.

...That being said, I do have some modifications I'd like to see to The Odin Project.  So consider doing The Odin Project, except with the _following modifications._  I advise that you read these notifications in their entirety before starting The Odin Project, and then follow them as they come up.
<!-- more -->




## Things You Should Skip

The first thing you should know about The Odin Project (TOP) is that they tend to overload on large heapings of repetition.  For real beginners, this is often a feature and not a bug.  However, don't be afraid to skip through things or skim things if you already understand them.  It is frequently unnecessary to do every reading unless you're confused on a concept.  This is doubly true for "Additional Resources" -- the initial allegedly "required" resources are already _more_ than enough, and you should rarely need to consult any of the "Additional Resources".

Here are some things I particularly advise skipping, to save time:

When TOP links you to a YouTube video that's longer than 10 minutes, it's probably unnecessary.  Skim the videos or ignore them entirely.  Don't forget you can speed them to 1.5x (or often even 2x) to get through them quicker, as they tend to be pretty slow.

[Course "1: Introduction to Web Development"](http://www.theodinproject.com/introduction-to-web-development) is cute and fun to read, but, in my opinion, not really necessary.  Skip it if you'd like.  If you do read it, try and skim.  Don't spend too much of your time here.

For ["Web Development 101 >> The Basics >> 2: How Does the Web Work?"](http://www.theodinproject.com/web-development-101/how-does-the-web-work), I don't think you really need to spend nearly that much time understanding the internet.  It might come up on an interview question or two, but a thorough understanding isn't really necessary outside the interview.  Just watch http://www.dontfeartheinternet.com/the-basics/not-tubes and then move on to the next lesson.

Skip ["Web Development 101 >> Web Development Frameworks >> 3: Backbone.js"](http://www.theodinproject.com/web-development-101/backbone-js) it's more confusing than helpful and you end up reviewing it in its proper detail later, after you understand more stuff.




## Things You Should Do More Of

Overall, I think you should be skipping more of TOP and getting through it faster than they tell you to, so you get to the good stuff quicker.  However, there are a few cases where I think TOP doesn't have you do enough, and slowing down is warranted.

In ["Web Development 101 >> The Front End >> 4: jQuery Basics"](http://www.theodinproject.com/web-development-101/jquery-basics), you'll get a chance to do lessons from either Codecademy or Code School.  I personally found it highly to do lessons from both, because they emphasize different things and the repetition is useful.  Code School does a better job of explaining in my opinion, so I highly recommend doing all of Code School's lessons first, then do all of Codecademy's lessons.  Also, TOP tells you that the remaining sections on events are extra credit, but I think that they're important to do, so I'd instruct you to **fully complete** both Codecademy and Code School lessons for jQuery.

In ["Ruby Programming >> Intermediate Ruby >> Project: OOP"](http://www.theodinproject.com/ruby-programming/oop), I chose to do some additional work: make an AI for the Tic-Tac-Toe program that plays optimally.  I think this was a worthwhile learning experience, and I urge you to try it.

I don't think you should build a copy of Tic-Tac-Toe in JavaScript as TOP has you do -- Snake an Minesweeper seem like enough.  But I do think there is an important lesson to be had with Tic-Tac-Toe and JavaScript: a much better exercise to make an Ajax front-end for the Ruby Tic-tac-toe you already created earlier in the courses.  After you complete ["Javascript and jQuery >> Better Forms with jQuery and AJAX >> Project: Infinite Scroll and Submitting a Form with AJAX"](http://www.theodinproject.com/javascript-and-jquery/infinite-scroll-and-submitting-a-form-with-ajax), do this.




## Let's Fix The Learning Ruby Section

I'll be honest -- TOP is great, but I don't like the TOP's approach to learning Ruby much at all.  It just throws too many resources at you, and you never learn everything you need at once.  So, when you get to ["Web Development 101 >> The Back End >> 2: Ruby Basics"](http://www.theodinproject.com/web-development-101/ruby-basics), **freeze**.  We're going to fix this.

Skip this lesson entirely.  Do not do "Web Development 101 >> The Back End >> 2: Ruby Basics" -- just mark it as complete and move on.

**Instead**, go to [Codecademy's Ruby Track](http://www.codecademy.com/tracks/ruby) and complete it entirely.  Throughout the course, TOP will make you complete it all eventually anyway in stages, so we might as well get it out of the way now.  This way, you'll get a better mastery of some things that come up in TOP before they're introduced.

Then, after your done with Codecademy's Ruby Track, read Chris Pine's ["Learn to Program"](https://pine.fm/LearnToProgram) and then read Chapters 1-3 of Peter Cooper's "Beginning Ruby".  Also review http://www.tutorialspoint.com/ruby/ruby_loops.htm, which is a resource I like that isn't in TOP, and important for the things TOP focuses on.

This counts as you completing this lesson.  Go on to the next lesson "Testing Basics".  Note that you have completely ignored tryruby.org, "Ruby in 100 Minutes", and Ruby Monk and this is for the best, because I don't think they're very good resources, and you should have already learned everything they teach 2-3x over through the resources you did consult.  Doing it five times seems like overkill (see "Things You Should Skip").

-

Since you did things a little out of order, you'll need the following clean-up.

When you get to ["Ruby Programming >> Basic Ruby >> 2: Ruby Building Blocks"](http://www.theodinproject.com/ruby-programming/ruby-building-blocks) you'll realize that you've been plopped in quite well, having already completed assignments 1-5.  Continue from assignment 6.  Skip assignment 9.


When you get to ["Ruby Programming >> Basic Ruby >> 3: Advanced Ruby Building Blocks"](http://www.theodinproject.com/ruby-programming/advanced-ruby-building-blocks) skip all the assignments and go straight to the Code Quizzes.  Complete those.  If you do well (>87% on each), continue.  Otherwise, go back and review, and try again.  Try to really understand why you got each question wrong.

When you get to ["Ruby Programming >> Intermediate Ruby >> 1: Object Oriented Programming"](http://www.theodinproject.com/ruby-programming/object-oriented-programming), skip assignment 1 because you have already done it.




## Reorder the JavaScript and jQuery Readings

For "Javascript and jQuery >> The Basics and the Browser >> 2: Javascript Basics", I think now is a better time to do some of the readings that TOP puts off for later.  So read the following links now and not later:

1.) http://agentcooper.github.io/js-ruby-comparison/

2.) http://skilldrick.co.uk/2011/01/ruby-vs-javascript-functions-procs-blocks-and-lambdas/

-

For "Javascript and jQuery >> Deeper into Javascript" and "Javascript and jQuery >> Advanced Browser Work", I have different opinions than the authors of the Odin Project.  In my opinion, the readings make more sense when they are presented like this:

1.) http://javascriptissexy.com/javascript-objects-in-detail/

2.) http://javascriptissexy.com/javascript-prototype-in-plain-detailed-language/

3.) http://javascriptissexy.com/oop-in-javascript-what-you-need-to-know/

...Now, pause to build something object oriented.  I don't think re-creating Tic-tac-toe in JavaScript is necessary -- Minesweeper and Snake should already be enough.  So build something object oriented, but simpler.  I'm not very good at exercises, but maybe build a town full of people objects, and then make professions (like doctor, police officer, etc.) that inherit from "person" but do special things.

...Now back to reading.

4.) http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/

5.) http://javascriptissexy.com/understand-javascript-closures-with-ease/

6.) http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/

7.) http://stackoverflow.com/questions/11233633/understanding-asynchronous-code-in-laymans-terms (a reading not in TOP that I added)

8.) http://sporto.github.io/blog/2012/12/09/callbacks-listeners-promises/

9.) http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/

10.) http://javascriptissexy.com/javascript-apply-call-and-bind-methods-are-essential-for-javascript-professionals/

11.) http://www.smashingmagazine.com/2014/01/23/understanding-javascript-function-prototype-bind/

12.) http://stackoverflow.com/questions/8197072/non-blocking-javascript-and-css-in-modern-browsers-is-it-still-needed

13.) http://alistapart.com/article/the-design-of-code-organizing-javascript

...Now do [the Minesweeper project](http://www.theodinproject.com/javascript-and-jquery/minesweeper).

Then do the readings in ["Javascript and jQuery >> Advanced Browser Work >> 3: Using Canvas to Draw and More"](http://www.theodinproject.com/javascript-and-jquery/using-canvas-to-draw-and-more) and then complete ["Javascript and jQuery >> Advanced Browser Work >> Project: Building Games with Canvas"](http://www.theodinproject.com/javascript-and-jquery/building-games-with-canvas).

You're now ready to go onto "Javascript and jQuery >> Better Forms with jQuery and AJAX" as normal.  Don't worry too much about the stuff you skipped -- it was either really unnecessary (a third review) or something I'll have you come back to later.




## Consider a Programming Bootcamp

This is mentioned in passing in TOP, but I thought I'd put it right here where you can see it, and spend more depth on it.

If you feel like you enjoy programming and want to make a career about it, but haven’t been doing so well at self-teaching, you could consider going to a programming bootcamp.  These are more-than-full-time intense programs that teach you programming and help you with job placement.  Here, you set aside 10+ weeks, enroll in the site, learn from the program, and hopefully pop out with a job on the way.

I've never personally gone to a boot camp (and don't plan to).   Keep in mind that a bootcamp is neither necessary nor sufficient to land a good programming job.  But for people with the time and inclination, it could be _a lot better_ than trying to go through this guide yourself.  If you’ve got the time, it’s definitely at least worth investigating.

[App Academy](http://www.appacademy.io/#p-home) is widely considered to be the best program and [there’s been lots of discussion of it on LessWrong](https://www.google.com/search?q=site%3Alesswrong.com+app+academy&oq=site%3Alesswrong.com+app+academy&aqs=chrome..69i57j69i58.5575j0j7&sourceid=chrome&es_sm=91&ie=UTF-8).  App Academy basically does Step 2-17 from this guide, but gives you support, formal teaching, and a good learning environment.  Buck Shlegeris is a TA at App Academy and is happy to be a contact if you're interested in getting more information on applying and/or getting coached through the process.  [Here's an interview with Buck about App Academy](http://80000hours.org/blog/329-interview-with-buck-shlegeris-from-app-academy) for more information.

Buck and Chris Hallquist (who went to App Academy) also say that [Hack Reactor](http://www.hackreactor.com/) is the second-best program if you’re not able to get into App Academy (it is somewhat selective).  [Here's a full list of all available bootcamps, with details](http://www.skilledup.com/learn/programming/the-ultimate-guide-to-coding-bootcamps-the-exhaustive-list/).

It's worth noitng that App Academy might be best for people in the US.  [Maker's Academy](http://www.makersacademy.com/) seems pretty good for people near London, though.




## More Things to Learn

This is sort of more of an afterthought than it probably should be, but it could be useful to learn Python.  Python is somewhat popular in the start-up world, though not nearly as popular as Ruby on Rails.  However, Python is really popular in the academic world.  It has [good support for statistical programming](http://www.numpy.org/) and has a platform called [Django](https://www.djangoproject.com/) that acts similarly to Rails.  It's probably good to learn Python so you're not "pidgeonholed" into only one type of programmer job (though the demand is definitely there).

Ultimately, Python is a good language to know, but that being said, several of us don’t think it’s worth the time investment if you’re solely focused on getting into the start-up world and don’t have a particular use for it.

However, if you’re interested, now would be a good time to pick it up.  If you’d like, work your way through [“Learn Python the Hard Way”](http://learnpythonthehardway.org/), skimming a bit as necessary.  Also, give a look through [“Think Python”](http://www.greenteapress.com/thinkpython/thinkpython.pdf), though you’ve probably learned much of it already from completing “Learn Python the Hard Way”.

-

Once you've completed all of TOP, I really think you should start applying for jobs (I mean, if you want one), because the best learning will come from being on the job.  However, while you're applying (or after you have the job), here are some things I think you might want to focus on, to extend your skills even further beyond what TOP asks for:

-

ERB, which you have been using to display Ruby in HTML, is nice, but HAML is also popular.  Haml makes a trade-off that allows you to write code faster, but has a steeper learning curve and is hard to understand.  Read through http://haml.info/tutorial.html.  For a project, take a project you have done where you wrote views in ERB, and re-write all those views in Haml.  Make sure it works.

-

It could be a good idea to learn CoffeeScript.  Skim through http://code.tutsplus.com/tutorials/rocking-out-with-coffeescript--net-17027, then through http://coffeescript.org/.  Next, do the tutorial at http://coffeescript.carbonfive.com/.  Finally, watch Coffeescript in action here: http://railscasts.com/episodes/267-coffeescript-basics.

As a project, make a Coffescript function that prints out the first twenty numbers in the Fibonacci sequence.  That should be good enough, but feel free to re-do some of your JS stuff in CoffeeScript if you'd like.  You also might want to read through http://coffeescript.org/ a little more thoroughly to get a better understanding of what it can do.  You'll also benefit from reading through http://css-tricks.com/jquery-coffeescript/ to get an idea of how to do jQuery stuff with Coffeescript.

-

It could be a good idea to learn Knockout.js.  Do this tutorial: http://learn.knockoutjs.com/#/?tutorial=intro




## Conclusion

In my guide, I said the following, and it equally applies here:

 > There are multiple paths to getting a programming job, learning programming, or whatever goal you may have. There’s no “one true way”, and there’s going to be a lot of conflicting advice on what is the “best” way to learn. Honestly what is best is going to vary person by person, and based on your interests and goals.

-

Like I said before, "I’ve designed a guide here based on my personal experience."  It's entirely possible that TOP is right about something and their original method was better for you, and I was wrong to disagree.  It's also entirely possible TOP is wrong about something for you, and I didn't catch it, because it didn't come up for me.

Your mileage might vary.  I'm not better than TOP -- they have their way, and I have mine.  I just wanted to write up my experience.  The best thing to do is just start, somewhere. See if this guide works for you, tweak if it doesn’t. Let me know.