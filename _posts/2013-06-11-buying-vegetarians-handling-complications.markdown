---
author: admin
comments: true
date: 2013-06-11 04:00:45+00:00
layout: post
slug: buying-vegetarians-handling-complications
title: 'Buying Vegetarians: Handling Complications'
wordpress_id: 223
categories:
- All
- Meat Reducing
- Strategic Philanthropy
---

**Continuation of [How Much Does It Cost to Buy a Vegetarian](http://www.everydayutilitarian.com/essays/how-much-does-it-cost-to-buy-a-vegetarian/)**

Recently, I've been trying to figure out how much it costs to save animals from factory farming.  The idea is to get people to become vegetarian by funding advertisements to influence them.  In [the previous essay](http://www.everydayutilitarian.com/essays/how-much-does-it-cost-to-buy-a-vegetarian/), I used a simple formula to work out the cost and it turned out to be a really cheap $0.02 to prevent a year of animal suffering on a factory farm (about $10 to get someone to become vegetarian for a year).

I [built a calculator](http://www.everydayutilitarian.com/vegan-outreach-cost-effectiveness-calculator/) so that anyone can play around with the formulas and be as pessimistic or optimistic as they like and see how that effects the calculations.

However, the simple calculation is... well... _simple_, and it needs some "beefing up", no pun intended.  Therefore, I also built a "complex calculator" that works on a much more complex formula[1] that is hopefully correct[2] and will provide a more accurate estimation.  Here are the details...<!-- more -->






## Accounting For Biases


The big, big deal for the surveys is concern for bias.  The most frequently mentioned bias is [social desirability bias](http://en.wikipedia.org/wiki/Social_desirability_bias), or people who say they reduced meat just because they want to please the surveyor or look like a good person, which actually happens a lot more on surveys than we'd like.

To account for this, we'll have to figure out how inflated answers are because of this bias and then scale the answers down by that amount.  Nick Cooney who says that he's been reading studies that about 25% to 50% of people who say they are vegetarian actually are, though I don't yet have the citations.  Thus, if we find out that an advertisement creates two meat reducers, we'd scale that down to one reducer if we're expecting a 50% desirability bias.



The second bias that will be a problem for us is [non-response bias](http://en.wikipedia.org/wiki/Non-response_bias), as those who don't reduce their diet are less likely to take the survey and therefore less likely to be counted.  This is especially true in the Facebook study, which only measures people who "liked" or requested a starter kit, showing some pro-vegetarian affiliation.

We can balance this out by assuming everyone who didn't take the survey went on to have no behavior change whatsoever.  [Nick Cooney's Facebook Ad Survey](http://www.utilitarian-essays.com/FacebookAdsSurveyResults2011.pdf) is for the 7% of people who liked the page (and then responded to the survey), and obviously those who liked the page are more likely to reduce their consumption.  I chose an optimistic value of 90% to consider the survey completely representative of the 7% who liked the page, and then a bit more for those who reduced their consumption but did not like the page.  My pessimistic value was 95%, assuming everyone who did not like the survey went unchanged and assuming a small response bias among those who liked the page but chose not to take the survey.

For the pamphlets, however, there should be no response bias since the entire population of college students was surveyed from randomly, and no one was said to reject taking the survey.






## Additional People Are Being Reached


In the Facebook survey, those who said they reduced their meat consumption were also asked if they influenced any of their friends and family to also reduce eating meat, and found that they usually produced 0.86 additional reducers.

This figure seems very high, but I do strongly expect the figure to be positive -- people who reduce eating meat will talk about it sometimes, essentially becoming free advertisements.  I'd be very surprised if they ended up being a net negative.






## Accounting for Product Elasticity


Another way to boost the effectiveness of the estimate is to be more accurate about what happens when someone stops eating meat.  The change isn't from the actual refusal to eat, but rather from the reduced demand for meat, which leads to a reduced supply.  Following the laws of economics, however, this reduction won't necessarially be one-for-one, but rather depend on the [elasticity of product demand and supply](http://en.wikipedia.org/wiki/Elasticity_(economics)).  By getting this number, we can find out how much meat is reduced for every meat not demanded.

My guesses in the calculator come from the following sources, some of which are PDFs: [1](http://www.agecon.ksu.edu/livestock/Extension%20Bulletins/BeefDemandDeterminants.pdf), [2](http://ageconsearch.umn.edu/bitstream/21679/1/sp99ma02.pdf), [3](http://www.thepigsite.com/swinenews/21164/market-preview-understanding-pork-demand), [4](http://www.poultryscience.org/docs/PS_822.pdf), [5](http://ageconsearch.umn.edu/bitstream/31190/1/23020558.pdf), [6](http://onlinelibrary.wiley.com/book/10.1002/9781119993384), [7](http://dare.colostate.edu/skoontz/arec510/papers/marsh%20%28ajae%201994%29.pdf), [8](http://ageconsearch.umn.edu/bitstream/14745/1/wp9808.pdf), [9](http://www.rti.org/pubs/muth_pork-slaughter_final.pdf), [10](http://ageconsearch.umn.edu/bitstream/31510/1/27010043.pdf), [11](http://oregonstate.edu/dept/IIFET/Japan/proceedupdates/306.pdf)






## Putting It All Together, Redux


Implementing the formula [on the calculator](http://www.everydayutilitarian.com/vegan-outreach-cost-effectiveness-calculator/), we end up with an estimate of **$0.03 to $36.52** to reduce one year of suffering on a factory farm based on the Facebook ad data and an estimate of **$0.02 to $65.92** based on the pamphlet data.

Hopefully the complexities in this calculator address some of the criticism for this approach.  In the third and final part of this essay series, I'll discuss the criticism in depth, and highlight what I agree and disagree with.

**Continued in [Buying Vegetarians: Addressing Criticism](http://www.everydayutilitarian.com/essays/buying-vegetarians-addressing-criticism/)**

-

**[1]:** Cost effectiveness in amount of days prevented per dollar = (People Reached / Dollar + (People Reached / Dollar * Additional People Reached / Direct Reach * Response Bias * Desirability Bias)) * Years Spent Reducing * (((Percent Increasing Beef * Increase Value) + (Percent Staying Same with Beef * Staying Same Value) + (Percent Decreasing Beef Slightly * Decrease Slightly Value) + (Percent Decreasing Beef Significantly * Decrease Significantly Value) + (Percent Eliminating Beef * Elimination Value) + (Percent Never Ate Beef * Never Ate Value)) * Normal Beef Consumption * Beef Elasticity * (Average Beef Lifespan + Days of Suffering from Beef Slaughter)) + (((Percent Increasing Dairy * Increase Value) + (Percent Staying Same with Dairy * Staying Same Value) + (Percent Decreasing Dairy Slightly * Decrease Slightly Value) + (Percent Decreasing Dairy Significantly * Decrease Significantly Value) + (Percent Eliminating Dairy * Elimination Value) + (Percent Never Ate Dairy * Never Ate Value)) * Normal Dairy Consumption * Dairy Elasticity * (Average Dairy Lifespan + Days of Suffering from Dairy Slaughter)) + (((Percent Increasing Pig * Increase Value) + (Percent Staying Same with Pig * Staying Same Value) + (Percent Decreasing Pig Slightly * Decrease Slightly Value) + (Percent Decreasing Pig Significantly * Decrease Significantly Value) + (Percent Eliminating Pig * Elimination Value) + (Percent Never Ate Pig * Never Ate Value)) * Normal Pig Consumption * Pig Elasticity * (Average Pig Lifespan + Days of Suffering from Pig Slaughter)) + (((Percent Increasing Broiler Chicken * Increase Value) + (Percent Staying Same with Broiler Chicken * Staying Same Value) + (Percent Decreasing Broiler Chicken Slightly * Decrease Slightly Value) + (Percent Decreasing Broiler Chicken Significantly * Decrease Significantly Value) + (Percent Eliminating Broiler Chicken * Elimination Value) + (Percent Never Ate Broiler Chicken * Never Ate Value)) * Normal Broiler Chicken Consumption * Broiler Chicken Elasticity * (Average Broiler Chicken Lifespan + Days of Suffering from Broiler Chicken Slaughter)) + (((Percent Increasing Egg * Increase Value) + (Percent Staying Same with Egg * Staying Same Value) + (Percent Decreasing Egg Slightly * Decrease Slightly Value) + (Percent Decreasing Egg Significantly * Decrease Significantly Value) + (Percent Eliminating Egg * Elimination Value) + (Percent Never Ate Egg * Never Ate Value)) * Normal Egg Consumption * Egg Elasticity * (Average Egg Lifespan + Days of Suffering from Egg Slaughter)) + (((Percent Increasing Turkey * Increase Value) + (Percent Staying Same with Turkey * Staying Same Value) + (Percent Decreasing Turkey Slightly * Decrease Slightly Value) + (Percent Decreasing Turkey Significantly * Decrease Significantly Value) + (Percent Eliminating Turkey * Elimination Value) + (Percent Never Ate Turkey * Never Ate Value)) * Normal Turkey Consumption * Turkey Elasticity * (Average Turkey Lifespan + Days of Suffering from Turkey Slaughter)) + (((Percent Increasing Farmed Fish * Increase Value) + (Percent Staying Same with Farmed Fish * Staying Same Value) + (Percent Decreasing Farmed Fish Slightly * Decrease Slightly Value) + (Percent Decreasing Farmed Fish Significantly * Decrease Significantly Value) + (Percent Eliminating Farmed Fish * Elimination Value) + (Percent Never Ate Farmed Fish * Never Ate Value)) * Normal Farmed Fish Consumption * Farmed Fish Elasticity * (Average Farmed Fish Lifespan + Days of Suffering from Farmed Fish Slaughter)) + (((Percent Increasing Sea Fish * Increase Value) + (Percent Staying Same with Sea Fish * Staying Same Value) + (Percent Decreasing Sea Fish Slightly * Decrease Slightly Value) + (Percent Decreasing Sea Fish Significantly * Decrease Significantly Value) + (Percent Eliminating Sea Fish * Elimination Value) + (Percent Never Ate Sea Fish * Never Ate Value)) * Normal Sea Fish Consumption * Sea Fish Elasticity * Days of Suffering from Sea Fish Slaughter) * Response Bias * Desirability Bias

**[2]:** Feel free to check the formula for accuracy and also check to make sure the calculator implements the formula correctly.  I worry that the added accuracy from the complex calculator is outweighed by the risk that the formula is wrong.
