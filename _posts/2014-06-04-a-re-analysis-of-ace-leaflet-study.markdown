---
author: admin
comments: true
date: 2014-06-04 00:00:00-05:00
layout: post
slug: a-re-analysis-of-ace-leaflet-study
title: "A Re-Analysis of ACE's Leaflet Study"
categories:
- Meat Reducing
---

Now that I've been doing some research blogging, it's time to continue the trend with something big.  Maybe you've seen [ACE's leafleting study analysis](http://www.animalcharityevaluators.org/research/interventions/leafleting/leafleting-outreach-study-fall-2013/leafleting-outreach-study-analysis-fall-2013/) and was like "woah, that's long, no way I'm going to read all that".  Instead, my reaction was "that's long, but is there any way I can make it longer?"  So I did.  Sixteen hours later, I emerge with this:


## Introduction

[Animal Charity Evaluators](http://www.animalcharityevaluators.org/) (ACE) is a non-profit with the goal of using research to find ways to help more save nonhuman animals with the same amount of resources.  Given that the pro-nonhuman movement is quite small, any increase in our "bang for our buck" is quite important, and I welcome this research and aim to contribue to it myself.

[Vegan Outreach](http://www.veganoutreach.org/) and [The Humane League](http://www.thehumaneleague.com) are two pro-nonhuman non-profits that aim to do direct advocacy on behalf of non-human animals.  One thing they do is deliver leaflets to people aiming to convince people about the [horrors of factory farming](http://www.veganoutreach.org/whyvegan/animals.html) and convince them to [eat less meat](everydayutilitarian.com/essays/why-eat-less-meat).  ACE claims that this is [one of the most cost-effective ways to help non-human animals](http://www.animalcharityevaluators.org/research/interventions/leafleting/), but wants to put this to the test.

Throughout the latter half of 2013, Joey Savoie and Xio Kikauka, in cooperation with Animal Charity Evaluators, implemented a study of the impact of two Vegan Outreach leaflets on diet change.  In March 2014, ACE [released their analysis](ttp://www.animalcharityevaluators.org/research/interventions/leafleting/leafleting-outreach-study-fall-2013/leafleting-outreach-study-analysis-fall-2013/) in cooperation with Statisticians Without Borders.

I was personally somewhat skeptical of the analysis and though there was a decent amount of information still being left on the table.  I wanted to take advantage of the publicly provided dataset to do my own independent analysis to see what I could personally learn.

I did my best to check for errors, but it’s quite possible errors in my analysis may still remain. <!-- more -->



## Summary

**This blog post in one sentence:** ACE’s claims are broadly correct, though perhaps overstated.

I do not feel like the study provides any positive evidence for vegetarian conversion as a whole, so ACE’s claim that “[w]e found support for claims that distributing leaflets from Vegan Outreach (or similar leaflets published by other groups) causes a small percentage of respondents to go vegetarian” is overstated.  I also think there is more nuance affecting some of their conclusions than ACE's analysis admits, though to ACE's credit, they are pretty self-skeptical about their own results.

I think ACE should be appluaded for having a good degree of self-skepticism, a high degree of transparency, and doing great with going through pre-registration and other checks to make sure they wouldn't be fooling themselves.

-

Overall, one’s attitude toward these results depends really on how skeptical and negative one wants to be:

#### Reasons for positivity

* Rates of people eliminating both red meat and poultry after receiving the treatment leaflet were quite high at 2.5% (4/161) (see <a href="#redmeat">"Red Meat Elimination"</a>).

* The connection between the treatment leaflet and elimination of red meat and poultry was statistically significant (see <a href="#statsig">"Are these differences statistically significant?"</a>).

* There is a statistically significant connection between overall meat reduction and receiving the treatment leaflet (see <a href="#statsig">"Are these differences statistically significant?"</a>).

* The sample size of this study was underpowered enough that it could have missed an effect under 6% with >20% chance, and almost certainly would miss an effect at 1% or below (see <a href="#power">"Upper Bound"</a>).


#### Reasons for negativity

* Rates of people becoming entirely vegetarian were quite low at 0.56% (1/178) and this was not statistically significant, even before Bonferroni corrections (see <a href="#redmeat">"Red Meat Elimination"</a>).

* Treatment leaflets appear to have no effect on fish, eggs, or dairy (see <a href="#important">"How important is reducing red meat and poultry, but not anything else?"</a> and <a href="#mechanism">"Why might the leaflets only be reducing red meat and poultry, and not other food groups?"</a>).
.

* Less than half of the people in the treatment group who changed their diet specifically attribute their diet change to the leaflet (See <a href="#attribution">"How much can flyers be attributed to these changes?"</a>).

* There was a problem with the control group (see <a href="#control">"What should the treatment and control groups be?"</a>).

* There were sizable problems with whether people were able to recall the leaflets that were handed out to them at the time of the post-treatment assessment three months later (see <a href="#recollection">"Recollection Errors"</a>)

* There are methodological problems with both food frequency questionnaires and with asking people about their diet change in terms of “vegetarian” and “pescetarian” (see <a href="#challenges">"Challenges to These Variables"</a>).

* The connection between the treatment leaflet and elimination of red meat and poultry was no longer statistically significant after Bonferroni corrections (though see <a href="#bonferroni">"How bad is it that the tests were not able to pass Bonferroni corrections?"</a></p>).

* The change in eliminating red meat and poultry derived from the food frequency questionnaires did not correspond with changes from people stating that they “went pescatarian” (see <a href="#changes">"What changes reportedly occurred as a result of the leafleting?"</a>, though also see <a href="#noconnection">"How bad is it that there was no connection between pescatarianism or meat reduction?"</a>).

* There also appeared to be errors in how the survey was designed (see <a href="#design">"Survey Design Errors"</a>).


## Setting up the Dataset

To start, I went to the survey dataset, downloaded a copy as a csv, removed the first row, and imported the file into R.  The provided survey questions and guide to the data were very useful in interpreting the dataset, and I thank ACE for making it so easy to do this re-analysis.  It reflects really well on their value for transparency.

My [R script for doing the re-analysis is here](https://github.com/peterhurford/personal/blob/gh-pages/tilde/files/leaflets.R).



## What should the independent variable be?

Once I set up the dataset, I looked into how we should represent the independent variable -- the amount of change in diet caused by the survey.

#### Meat Elimination

Question 1 asked about the amount of foods people eat now and Question 3 asks about the amount of foods people ate three months ago.  I summed up the total ranks across red meat, poultry, and fish/seafood for both present and three months ago.  I then compared these totals and looked for people who had no meat consumption at present but did consume meat three months ago (meat eliminator), people who consumed meat both in present and three months ago (no change), and people who consumed meat at present but did not consume meat three months ago (meat adders).

<table>
	<tr>
		<th>Meat Eliminator</th>
		<th>No Change</th>
		<th>Meat Adder</th>
		<th>N</th>
	</tr>
	<tr>
		<td>4 (0.8%)</td>
		<td>532 (99%)</td>
		<td>1 (0.2%)</td>
		<td>537</td>
	</tr>
</table>

Note that while 0.8% new vegetarians might look low, we still have not yet compared that population to the leaflet-receiving population, and thus still cannot make any conclusions about how many people given they receive a leaflet, go vegetarian -- that percentage could still be much higher (or lower).


#### Meat Reduction

I’m not sure how much I trust the Food Frequency Questionnaires to provide accurate and precise measures of people’s diets, so I’m a bit uncomfortable trying to tease meat reduction out of the dataset (as is the ACE analysis).  However, there is also a problem that outright elimination happens too infrequently (only 0.8% of the data set), so we might want a variable that is more easily changed.

Therefore, I compared the past and current consumption of meat and this time assigned categories for Reduced, Stayed the Same, and Increased, looking at relative changes rather than outright elimination.  I do not think this is a variable ACE looked at.

<table>
	<tr>
		<th>Meat Reducer</th>
		<th>No Change</th>
		<th>Meat Increaser</th>
		<th>N</th>
	</tr>
	<tr>
		<td>174 (32.4%)</td>
		<td>243 (45.3%)</td>
		<td>120 (22.3%)</td>
		<td>537</td>
	</tr>
</table>


#### Red Meat Elimination <a id="redmeat">&nbsp;</a>

ACE spent a lot of their analysis looking at how consumption of individual foods changed as a way to measure meat reduction.  I was particularly interested at people’s elimination of red meat, as this is a type of meat frequently eliminated first.

<table>
	<tr>
		<th>Red Meat Eliminator</th>
		<th>No Change</th>
		<th>Red Meat Adder</th>
		<th>N</th>
	</tr>
	<tr>
		<td>13 (2.3%)</td>
		<td>539 (96.4%)</td>
		<td>7 (1.3%)</td>
		<td>559</td>
	</tr>
</table>


#### Poultry Elimination

As ACE found positive results for poultry as well, I looked at that too.

<table>
	<tr>
		<th>Poultry Eliminator</th>
		<th>No Change</th>
		<th>Poultry Adder</th>
		<th>N</th>
	</tr>
	<tr>
		<td>8 (1.4%)</td>
		<td>547 (98%)</td>
		<td>3 (0.6%)</td>
		<td>558</td>
	</tr>
</table>

Some of the people even eliminated both.  Six people were found to eliminate both poultry and red meat, with nine people eliminating just one (seven for just red meat, two for just poultry).


#### Change in Declared Vegetarianism and Veganism

In addition to food frequency questionnaires, the survey also asked people if they identified as vegetarian or vegan at present and if they identified as vegetarian or vegan three months ago.

<table>
	<tr>
		<th>Omnivore (3mo ago)</th>
		<th>Vegetarian (3mo ago)</th>
		<th>Vegan (3mo ago)</th>
		<th>Omnivore (present)</th>
		<th>Vegetarian (present)</th>
		<th>Vegan (present)</th>
	</tr>
	<tr>
		<td>578</td>
		<td>32</td>
		<td>13</td>
		<td>570</td>
		<td>39</td>
		<td>14</td>
	</tr>
</table>

<table>
	<tr>
		<th>Vegan to Omnivore</th>
		<th>Vegetarian to Omnivore</th>
		<th>Vegan to Vegetarian</th>
		<th>No Change</th>
		<th>Vegetarian to Vegan</th>
		<th>Omnivore to Vegetarian</th>
		<th>Omnivore to Vegan</th>
	</tr>
	<tr>
		<td>3</td>
		<td>3</td>
		<td>1</td>
		<td>572</td>
		<td>1</td>
		<td>10</td>
		<td>4</td>
	</tr>
</table>


#### Change in Declared Pescetarianism and Intent to Reduce Meat

As we were looking at whether people were dropping red meat and poultry, I was also curious if this would match up with people personally identifying as pescatarians.

<table>
	<tr>
		<th>Reducer (3mo ago)</th>
		<th>Pescatarian (3mo ago)</th>
		<th>Reducer (present)</th>
		<th>Pescatarian (present)</th>
	</tr>
	<tr>
		<td>35</td>
		<td>28</td>
		<td>44</td>
		<td>33</td>
	</tr>
</table>

<table>
	<tr>
		<th>Pescatarian to Omnivore</th>
		<th>Reducer to Omnivore</th>
		<th>Pescatarian to Reducer</th>
		<th>No Change</th>
		<th>Reducer to Pescatarian</th>
		<th>Omnivore to Reducer</th>
		<th>Omnivore to Pescatarian</th>
	</tr>
	<tr>
		<td>12</td>
		<td>10</td>
		<td>1</td>
		<td>527</td>
		<td>2</td>
		<td>19</td>
		<td>15</td>
	</tr>
</table>


## Challenges to These Variables <a id="challenges">&nbsp;</a>

Why look at eight different independent variables?  One reason was that we were interested in both partial meat elimination and full meat elimination.  But another reason is that it’s really hard to figure out who exactly is vegetarian...


#### First Problem: Vegetarians and Vegans Eat Meat <a id="vegeatmeat">&nbsp;</a>

Weird, I know.  But it seems like people report themselves as “vegetarian” or “vegan” without knowing what it really means.  The good news is that vegetarians and vegans do eat less meat.  But the weird thing is that they still do eat meat.  Therefore, we may have someone who claim they became vegan, but all that might mean in reality is that they merely reduced their meat consumption.

<table>
	<caption>Mean “Ranks” in Meat Eating by Diet Status (Reverse coded so higher = more meat eating)</caption>
	<tr>
		<th>&nbsp;</th>
		<th>Red Meat</th>
		<th>All Meat</th>
		<th>All Animal Products</th>
	</tr>
	<tr>
		<td>Omnivore</td>
		<td>2.97 / 7</td>
		<td>8.2 / 21</td>
		<td>14.30 / 35</td>
	</tr>
	<tr>
		<td>Vegetarian</td>
		<td>0.97 / 7</td>
		<td>2.6 / 21</td>
		<td>8.51 / 35</td>
	</tr>
	<tr>
		<td>Vegan</td>
		<td>0.43 / 7</td>
		<td>1.7 / 21</td>
		<td>3.69 / 35</td>
	</tr>
</table>


#### Second Problem: Pescetarians Underreport Their Pescatarianism <a id="pesce">&nbsp;</a>

If you think people have a hard time with the "vegetarian" label, then you must think people have huge problems with the less popular "pescetarian" label.  Here's a table with whether people label themselves pescetarian and how they respond on the food frequency questionnaires about red meat and poultry (they never ate the two, they no longer eat the two as of the post-survey, or they still eat the two despite self-identifying as pescetarian).

<table>
	<tr>
		<th>&nbsp;</th>
		<th>Not Pescetarian</th>
		<th>Pescetarian</th>
	</tr>
	<tr>
		<td>Never Ate</td>
		<td>28</td>
		<td>7</td>
	</tr>
	<tr>
		<td>No Longer Eat</td>
		<td>5</td>
		<td>1</td>
	</tr>
	<tr>
		<td>Still Eat</td>
		<td>525</td>
		<td>15</td>
	</tr>
</table>

As you can see, the pescetarian label is quite untrustworthy.


#### Third Problem: Food Frequency Questionnaires Seem Troublesome

Quick!  How many servings of cheese did you eat three months ago?

Don’t know the answer?

...Can you ballpark it?

No?

Me neither.

But yet this is the alternative method of figuring out whether people go vegetarian or reduce meat consumption -- compare their actual diets from three months ago to now.  These food frequency questionnaires are standard to the nutrition science industry, so they might be the be best we’ve got.  But I’m skeptical of them.

-

That being said, it's possible that these food frequency questionnaires are reliable in the cases of *elimination* as opposed to *reduction*, as *zero* is a pretty hard number to misremember.



## What should the relevant treatment and control groups be? <a id="control">&nbsp;</a>

So we’re looking to five different independent variables to track changes in diet.  But we’re really interested in the impact of leafleting.  The study was designed well -- there was a control leaflet and two different treatment leaflets.

<table>
	<caption>Leaflets Recognized by Follow-up Survey Respondents</caption>
	<tr>
		<th>EIYLM (treatment)</th>
		<th>CC (treatment)</th>
		<th>CBTC (control)</th>
		<th>Fictional Flyer</th>
		<th>No Leaflet</th>
	</tr>
	<tr>
		<td>95</td>
		<td>125</td>
		<td>44</td>
		<td>5</td>
		<td>428</td>
	</tr>
</table>

EIYLM = [Even if You Like Meat](http://www.veganoutreach.org/EIYLM.pdf), CC = [Compassionate Choises](http://www.veganoutreach.org/cc.pdf), CBTC = [Cruelty Behind the Cuteness](http://www.humanesociety.org/assets/pdfs/pets/puppy_mills/cruelty_behind_the_cuteness_flyer.pdf).  Note: The same respondent may be in multiple categories.


#### Problems with the Control Group

It seems like it might be easy to sort people into a treatment group and a control group.  However, because people received multiple leaflets, a lot of people who received the control leaflet also received the treatment leaflet, which means that they’re in the treatment group.

<table>
	<caption>Leaflets Recognized by Follow-up Survey Respondents</caption>
	<tr>
		<th>Treatment Leaflet Group</th>
		<th>Control Leaflet Group</th>
		<th>No Leaflet</th>
	</tr>
	<tr>
		<td>178</td>
		<td>17</td>
		<td>428</td>
	</tr>
</table>

This makes a control group that is much smaller than we need to use.  The ACE analysis decides to use the No Leaflet group as a secondary control group.  This seems sensible as a point of comparison, though it's possible that there could be selection biases if the type of people who would take a leaflet are more predisposed to go vegetarian.


#### Problems with Leaflet Recall

The fictional flyer refers to participants erroneously identifying receiving a flyer that was never handed out -- at least five people were duped by this, so there’s probably other errors with people remembering which leaflet they actually received.

Also, ACE mentions that more than sixty people also mention receiving a treatment leaflet that was not actually handed out at their location.  This means some people may have sorted themselves into the wrong treatment or control group, messing with our results.


## What changes reportedly occurred as a result of the leafleting? <a id="changes">&nbsp;</a>

So now that we have eight potential independent variables and three groups to look at, how did things actually turn out?

<table>
	<tr>
		<th>&nbsp;</th>
		<th>Treatment Flyer</th>
		<th>Control Flyer</th>
		<th>No Flyer</th>
	</tr>
	<tr>
		<td>Meat Elimination</td>
		<td>
			Elim: 1/158 (0.6%)<br>
			None: 156/158 (98.7%)<br>
			Add: 1/158 (0.6%)
		</td>
		<td>
			Elim: 0/15 (0%)<br>
			None: 15/15 (100%)<br>
			Add: 0/15 (0%)
		</td>
		<td>
			Elim: 3/364 (0.8%)<br>
			None: 361/364 (99.2%)<br>
			Add: 0/364 (0%)
		</td>
	</tr>
	<tr>
		<td>Meat Reduction</td>
		<td>
			Dec: 62/158 (39.2%)<br>
			None: 67/158 (42.4%)<br>
			Inc: 29/158 (18.4%)
		</td>
		<td>
			Dec: 3/15 (20%)<br>
			None: 8/15 (53.3%)<br>
			Inc: 4/15 (26.7%)
		</td>
		<td>
			Dec: 109/364 (29.9%)<br>
			None: 168/364 (46.2%)<br>
			Inc: 87/364 (23.9%)
		</td>
	</tr>
	<tr>
		<td>Red Meat Elimination</td>
		<td>
			Elim: 7/162 (4.3%)<br>
			None: 155/162 (95.7%)<br>
			Add: 0/162 (0%)
		</td>
		<td>
			Elim: 0/16 (0%)<br>
			None: 16/16 (100%)<br>
			Add: 0/16 (0%)
		</td>
		<td>
			Elim: 7/381 (1.8%)<br>
			None: 368/381 (96.6%)<br>
			Add: 6/381 (1.6%)
		</td>
	</tr>
	<tr>
		<td>Poultry Elimination</td>
		<td>
			Elim: 5/165 (3%)<br>
			None: 160/165 (97%)<br>
			Add: 0/165 (0%)
		</td>
		<td>
			Elim: 0/15 (0%)<br>
			None: 15/15 (100%)<br>
			Add: 0/15 (0%)
		</td>
		<td>
			Elim: 3/378 (0.8%)<br>
			None: 372/378 (98.4%)<br>
			Add: 3/378 (0.8%)
		</td>
	</tr>
	<tr>
		<td>Net Vegetarians and Vegans Added</td>
		<td>3/178 (1.7%)</td>
		<td>0/17 (0%)</td>
		<td>5/428 (1.2%)</td>
	</tr>
	<tr>
		<td>Net Pescetarians Added</td>
		<td>4/178 (2.5%)</td>
		<td>1/17 (5.9%)</td>
		<td>0/428 (0%)</td>
	</tr>
	<tr>
		<td>Net Meat Reducers Added</td>
		<td>4/178 (2.5%)</td>
		<td>0/17 (0%)</td>
		<td>5/428 (1.2%)</td>
	</tr>
</table>


## Are these differences statistically significant? <a id="statsig">&nbsp;</a>

Just looking at the table, it appears that a Vegan Outreach flyer does produce more meat reduction, red meat elimination, and net vegetarians/vegans added, relative to the control and no flyer groups, though it also seems to produce less meat elimination than the control / no flyer groups.

But the differences across the groups could just be due to chance.  To be sure, let’s compare across the groups with T-tests.  We’ll compare the population of those who received the treatment flyer to the population receiving the control flyer and then the wider population of everyone sampled who did not receive the treatment flyer.  I think treatment vs. non-treatment is by far the better case to look at, given the small size of the actual control group, though it does have possible opportuniteis for bias.

<table>
	<tr>
		<th>&nbsp;</th>
		<th>Treatment vs. Control</th>
		<th>Treatment vs. Non-treatment</th>
	</tr>
	<tr>
		<td>Meat Elimination</td>
		<td>t = 0.78, p = NS</td>
		<td>t = 0.00, p = NS</td>
	</tr>
	<tr>
		<td>Overall Meat Reduction</td>
		<td>t = -1.44, p = NS</td>
		<td>t = -2.21, p = 0.03</td>
	</tr>
	<tr>
		<td>Red Meat Elimination</td>
		<td>t = -2.69, p = 0.01</td>
		<td>t = -2.48, p = 0.01</td>
	</tr>
	<tr>
		<td>Poultry Elimination</td>
		<td>t = -2.26, p = 0.02</td>
		<td>t = -2.05, p = 0.04</td>
	</tr>
	<tr>
		<td>Net Vegetarians / Vegans Added</td>
		<td>t = -1.00, p = NS</td>
		<td>t = -0.30, p = NS</td>
	</tr>
	<tr>
		<td>Net Pescatarians Added</td>
		<td>t = 0.59, p = NS</td>
		<td>t = -0.99, p = NS</td>
	</tr>
	<tr>
		<td>Net Meat Reducers Added</td>
		<td>t = -1.15, p = NS</td>
		<td>t = -0.51, p = NS</td>
	</tr>
</table>

Based on this, the statistically significant effect of treatment flyers is muddled, but existant.  They do have statistically significant effects on meat reduction (for treatment vs. non-treatment), red meat elimination, and poultry elimination, but there is no corresponding statistically significant effect with declared pescatarianism or declared intent to reduce meat.  And no other variables are statistically significant.

Furthermore, it’s also worth noting that ACE did not do any sort of corrections for doing multiple statistical tests.  When we do a Bonferroni correction here, having done fourteen separate analyses, we reduce our threshold for statistical significance from p = 0.05 to p = 0.05/14, or 0.003, which no tests met.  Even a less stringent test, such as starting from p = 0.1 before Bonferroni corrections is not met.


## How much can flyers be attributed to these changes? <a id="attributon">&nbsp;</a>

One way we can look a little bit closer is with variables that (a) self-report how much of the leaflet was actually read, (b) self-report how influential the leaflet was, and (c) self-report the reason for changing diets.

#### How much of each leaflet was read?

<table>
	<tr>
		<th>&nbsp;</th>
		<th>Did not read</th>
		<th>Glanced</th>
		<th>Read some</th>
		<th>Read all</th>
	</tr>
	<tr>
		<td>EIYLM (treat)</td>
		<td>9 (9%)</td>
		<td>26 (27%)</td>
		<td>34 (36%)</td>
		<td>26 (27%)</td>
	</tr>
	<tr>
		<td>CC (treat)</td>
		<td>12 (10%)</td>
		<td>33 (27%)</td>
		<td>44 (35%)</td>
		<td>35 (28%)</td>
	</tr>
	<tr>
		<td>CBTC (control)</td>
		<td>6 (14%)</td>
		<td>15 (35%)</td>
		<td>16 (37%)</td>
		<td>6 (14%)</td>
	</tr>
	<tr>
		<td>Fictional flyer</td>
		<td>0 (0%)</td>
		<td>4 (80%)</td>
		<td>1 (20%)</td>
		<td>0 (0%)</td>
	</tr>
	<tr>
		<td>No flyer</td>
		<td>155 (82%)</td>
		<td>17 (9%)</td>
		<td>7 (4%)</td>
		<td>9 (5%)</td>
	</tr>
</table>


Interesting that reading patterns for the treatment leaflets are statistically identical (p = 0.11), but statistically distinct from the control flyer (p = 0.05).

...Also of problematic interest is how many people claimed never to receive a flyer, yet claimed to have read a flyer anyway.


#### How influential were the leaflets?

<table>
	<tr>
		<th>&nbsp;</th>
		<th>Leaflet caused diet change</th>
		<th>Thinking differently about farming</th>
		<th>Thinking differently about pets</th>
		<th>Possible effect</th>
		<th>No effect</th>
	</tr>
	<tr>
		<td>EIYLM (treat)</td>
		<td>7 (7%)</td>
		<td>18 (19%)</td>
		<td>6 (6%)</td>
		<td>26 (28%)</td>
		<td>37 (39%)</td>
	</tr>
	<tr>
		<td>CC (treat)</td>
		<td>11 (9%)</td>
		<td>28 (23%)</td>
		<td>2 (2%)</td>
		<td>29 (24%)</td>
		<td>53 (43%)</td>
	</tr>
	<tr>
		<td>CBTC (control)</td>
		<td>2  (5%)</td>
		<td>6 (1%)</td>
		<td>4 (10%)</td>
		<td>13 (31%)</td>
		<td>17 (40%)</td>
	</tr>
	<tr>
		<td>Fictional flyer</td>
		<td>0 (0%)</td>
		<td>1 (25%)</td>
		<td>0 (0%)</td>
		<td>2 (50%)</td>
		<td>1 (25%)</td>
	</tr>
	<tr>
		<td>No flyer</td>
		<td>0 (0%)</td>
		<td>8 (4%)</td>
		<td>10 (5%)</td>
		<td>39 (22%)</td>
		<td>124 (69%)</td>
	</tr>
</table>

-

* 6 people who received the treatment flyer self-reported becoming a vegetarian or vegan.  Of these...

* 5 out of the 6 reported reading all of the leaflet.

* 1 out of the 6 report having their diet changed by the leaflet.

* 2 out of the 6 report the leaflet having zero impact on their diet.

* 2 out of the 6 report changing their diet for animal cruelty or ethical reasons.

-

We can also use this to dig a little bit deeper at red meat elimination, one of the independent variables credited by ACE as being affected by the leaflet.

* 7 people who received the treatment flyer self-reported eliminating red meat.  Of these...

* 2 out of the 7 reported reading all of the leaflet.

* 4 out of the 7 report having their diet changed by the leaflet.

* 1 out of the 7 report the leaflet having zero impact on their diet.

* 4 out of the 7 report changing their diet for animal cruelty or ethical reasons.

-

This is good as a check of our results above -- we have found that some of the people who appear converted by the leaflet also agree that they were converted.  Moreover, I was concerned that people switching to eliminate red meat would be doing so for health reasons alone, and this does not appear to be the case, nearest as we can tell.

Though take this all with a grain of salt -- if you have middling confidence in people’s ability to self-report their diet, like I do, you probably should also have middling confidence in people’s ability to understand how much the leaflet affected them.  I do think you can justify slightly higher confidence in these numbers, as it’s more salient and potentially easier to recall than precise numbers about your diet, but people are still generally bad at retrospecting on causal influences on their life.


#### What are preliminary lower and upper bounds for flyer conversion rates?

**Lower Bound**

178 treatment flyers were given out, and it appears quite plausible (as clear as can be determined by the survey, given that you trust self-reported data) that precisely one person was lead to become a (genuine) vegetarian specifically based on having received the treatment flyer.  One could consider this as establishing a preliminary lower bound on conversion rates at 0.56%, though I would be careful not to generalize from solely one person.


**Upper Bound** <a id="power">&nbsp;</a>

It’s worth noting that the small sample size of this study means that it might have trouble detecting a statistically significant difference in diet change.  This study had a sample size of  623, with 178 having received a flyer.  The past Facebook study had a sample size of 104 and a similar leafleting study had a sample size of “about 500”.

Small changes in diet change can be drowned out by statistical noise.  To figure out what sample size we can use, we can use an “a priori sample size calculator for the two group chi-squared test”.  For this, we need a desired power level (chance of detecting the effect given that the effect exists), a probability level (our threshold p-value), and an estimate of the proportion of people who become vegetarians (or vegans, or reduce meat, etc.) in the control group and treatment group.

Any desired sample size is going to be a trade-off between wanting more statistical power and wanting to spend less money collecting the sample.  An additional consideration is that the desired sample size is the number of people we need to take the follow-up survey, which might be a smaller proportion of the total number of people that see the ads, due to inefficiencies in our conversion process.

Here’s a table with some estimations with the classic probability level = 0.05 and desired power level = 0.8, and our treatment-control proportions found in this survey, here is how much larger our population would need to be to detect the effect with 80% chance, given our current study size and ratios between the treatment and control group:

<table>
	<tr>
		<td>Control %</td>
		<td>Treatment %</td>
		<td>Difference</td>
		<td>Population Needed</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>8%</td>
		<td>+7%</td>
		<td>0.8x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>7%</td>
		<td>+6%</td>
		<td>1.01x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>6%</td>
		<td>+5%</td>
		<td>1.3x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>5%</td>
		<td>+4%</td>
		<td>1.7x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>4%</td>
		<td>+3%</td>
		<td>2.5x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>3%</td>
		<td>+2%</td>
		<td>4.4x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>2%</td>
		<td>+1%</td>
		<td>12.4x larger</td>
	</tr>
	<tr>
		<td>1%</td>
		<td>1.5%</td>
		<td>+0.5%</td>
		<td>39.4x larger</td>
	</tr>
</table>

Based on this table and our sample size, it’s possible that the leaflets could be converting people at a rate of 7% (relative to a 1% baseline) and we’d have about an 80% chance of detecting it. So therefore, I feel confidant placing a preliminary upper bound at 6%.  Based on this data, it’s highly unlikely that flyers convert at a rate higher than 6%.

Also of note is that if we think the difference between treatment and control is quite small (like 0.5%), we’d need a much larger study to detect it -- 39.4x larger than our current study.  Though if we had an even split between treatment and control, it could be detected 80% of the time with just 16,294 people, or 26x our current population.


## Conclusions

#### What are the implications for ACE’s Analysis?

ACE concludes in their analysis that “[w]e found support for claims that distributing leaflets from Vegan Outreach (or similar leaflets published by other groups) causes a small percentage of respondents to go vegetarian or give up eating specific types of meat.”  This claim is tepid, but appears somewhat substantiated by my analysis.

Statistical tests were able to connect the treatment flyers to the cessation of eating red meat and poultry, but these tests ceased to be statistically significant once Bonferroni corrections were made.  Additionally, they did not connect with any statistically significant finding for declared pescatarianism or meat reduction.

Additionally, statistical tests were not able to reject the null hypothesis that leaflets do not cause wholesale shift to a vegetarian diet.  Therefore, the part of ACE’s claim that leaflets cause “a small percentage of respondents to go vegetarian” may not be established at this time.  However, less robust (but still plausibly reliable) were able to detect one person who responded as we would expect a vegetarian who had been changed by the leaflet to respond.


**How bad is it that there was no connection between pescatarianism or meat reduction?** <a id="noconnection">&nbsp;</a>

It seems potentially problematic that while there was a reduction of red meat and poultry consumption, there was no corresponding change in people declaring themselves "pescatarian."  However, given how bad people appear to be with just the common "vegetarian" label (e.g., [how self-identified "vegetarians" eating meat](#vegeatmeat)), I wouldn't trust them one bit to understand the "pescatarian" label.  And once we do the analysis and see that [people who don't eat red meat or poultry still don't call themselves pescetarian](#pesce)), it's clear this variable is untrustworthy.


**How bad is it that the tests were not able to pass Bonferroni corrections?** <a id="bonferroni">&nbsp;</p>

It's true that a statistically robust conclusion should be able to pass Bonferroni corrections.  However, given the sample size of this study [compared to how large the sample size would have to be](#power), it's unlikely that we would be able to detect such robust effects even if they did exist, so I'm not particularly worried.  I'd be inclined to accept that the effects on meat reduction, red meat elimination, and poultry elimination are genuine effects, but that no other real effects exist (e.g., other kinds of meat, or shift to vegetarianism).


#### What are the implications of this study for prior studies of veg outreach?

It’s curious that this study finds a much smaller amount of vegetarian change attributable to flyers than a past study on leafleting, which found a conversion rate of 2% of leaflet takers becoming pescatarian (CCC Flyer Study), which is very similar to our study.


**The Need for Some Point of Comparison, If Not a Control Group**

The CCC Flyer Study sampled everyone, but only permitted those who received a leaflet to take the survey.  Of course, the language of the survey was strong, asking people to directly attribute their diet change to the leaflet.  But I imagine that this didn’t work as intended, and had they sampled people who did not receive the leaflet, or sampled at a college that had no leaflets distributed, it’s possible they would have found a similar conversion rate.  Therefore, it’s good that this study was done with ACE with a point of comparison, so we can see that the 2% figure does make sense in context.  Including these valuable pseudo-control groups is an important step forward.


**Recollection Errors** <a id="recollection">&nbsp;</a>

Prior flyer research had attempted to navigate non-response bias (systematic biases in who fills out the survey) and social desirability bias (systematic increases in vegetarianism as people aim to please or look more virtuous).   Much has been done recently to try to work against these two biases.

However, another important aspect of the ACE Study is drawing our attention to a third form of bias -- recollection errors.  ACE concludes that “[w]e do not know whether this pattern [of decreased meat consumption in our data] reflects real decreases in consumption or only systematic errors in recollection.”

This recollection error also undermines the food frequency questionnaires used for meat reduction statistics -- if they can’t remember receiving a leaflet, how can we trust them to remember intricate details about the number of servings of cheese they ate three months ago?  This seems difficult to deal with and suggests that new designs will be necessary for future studies.


**Survey Design Errors** <a id="design">&nbsp;</a>

Another problem was the design of [the survey](http://www.animalcharityevaluators.org/wp-content/uploads/2014/03/Leafleting-Survey-Packet.pdf).  According to Joey and Xio, who designed the study and helped hand out many of the questionnaires, people were struggling with taking the survey as it was too long and complicated.  One large problem was that people were skimming and had trouble understanding that the two food frequency questionnaires were different items.


#### How important is reducing red meat and poultry, but not anything else? <a id="important">&nbsp;</a>

It’s certainly good that the leaflets are doing something, most notably getting about 4% of respondents to give up red meat and another 4% to give up poultry, with no corresponding increases in meat eating elsewhere.  But how important is this?

In my essay “How Much Suffering is in the Standard American Diet”, I provide figures that show if we take a suffering-per-kilogram point of view to our averting animal products, giving up red meat has 13% of the impact a typical vegan (not vegetarian) conversion would have, giving up poultry has 33.4% of the impact of veganism, and giving up both has 46% of the impact.

This means that a leaflet that converts 2% of people to become pescatarian (giving up red meat and poultry) would have essentially the same impact as a leaflet that converted 0.92% of people to become vegetarian, at least prima facie.  Given that these leaflets appear to have this impact on poultry elimination, that isn’t so bad!


**Vegetarian Recidivism**

One potential problem, though, is that it’s unclear whether people would stick with poultry elimination with the same fervor as one would stick to vegetarianism.  It seems intuitively less likely to me, because there’s less of a culture and moral force surrounding it.


**The 100 Yard Line**

On the other hand, perhaps we could look to Brian Tomasik’s 100 Yard Line Model for vegetarian conversion, which is summarized with the observation that perhaps pushing people to eliminate poultry and/or red meat is just one stepping stone to getting them to become full vegetarian soon.  It’s definitely a big first step!


#### Why might the leaflets only be reducing red meat and poultry, and not other food groups? <a href="mechanism">&nbsp;</a>

Aside from the philosophical question about what the value of reducing red meat and poultry is, we might also be curious as to the empirical question -- why are people only eliminating red meat and poultry, and not other food groups?

Unfortunately, we can only speculate, but it seems quite plausible that the reason is that the two treatment leaflets ([“Compassionate Choices”](http://www.veganoutreach.org/cc.pdf) and [“Even if You Like Meat”](http://www.veganoutreach.org/EIYLM.pdf)) both focus significantly on the meat of pigs, chickens, and cows, and do not focus much at all on dairy, eggs, or fish.


#### What future research should be done?

I think we are getting very close to understanding the impact of leafleting, but I don't think we're quite there yet.  We could use further research (as always).

I think the most important future research should focus on addressing the methodological issues here, trying to come up with better independent variables or better ways to mitigate the drawbacks that have been discovered with these independent variables.  For example, I'd propose further research into how the public understands terms like "vegetarian" or "pescetarian" or more research into leaflet recall after a few months.  Perhaps we could make use of more reliable panel studies, where we know we'd have access to the same participants after a few months.

Additionally, the next step to settle this question as much as it can be settled would be to do a large sample size study with a control group.  Having a couple thousand people in each group should do the trick and place a worthwhile upper bound on what the size of the effects would be, even if we don't yet know the true lower bound (because it might remain too small to detect).

Lastly, something still worthwhile would be to run this study again though with a functional control group (that receives control leaflets) or to run this study in different contexts (e.g., online ads).