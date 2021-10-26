# Pitch_Recognition_Scores
Pitch Recognition and Aggressiveness Scores For MLB Hitters

Assumptions:

A hitter determines whether or not to swing based on two factors: the hitter’s calculated likelihood of the pitch being a strike at the point at which the hitter must commit to a swing and the count. 
Specifically, a hitter first sets a strike probability at which they’re willing to swing based on the count -- a concept that I’ll call the hitter’s confidence threshold. 
Then, as the pitcher throws his pitch, the hitter assesses the probability of the pitch being in the strike zone before the hitter has to commit to his swing. 
At that point, the hitter compares his calculated probability of the pitch being a strike to his confidence threshold, swings if the pitch’s projected strike likelihood is higher than his confidence threshold, and doesn’t swing if the pitch’s projected strike likelihood is lower than his confidence threshold.

Consider the following example. Imagine that, in an 0-0 count, a hitter has a confidence threshold of 85%. At the point when the hitter must decide whether or not to commit to his swing, he projects that the pitch will be a strike 75% of the time (in other words, his projected strike likelihood is 75%). In this case, the hitter will not swing. 
If instead his confidence threshold was 70% or his projected strike likelihood was 90%, then he would swing.

This is obviously at best a simplification of what happens in a hitter’s mind at the plate. For one, hitters likely consider more than just the count when determining their confidence threshold; factors including baserunners and the game score may come into play, among others. Additionally, hitters likely consider more than just whether or not the pitch will be a strike when determining whether or not to swing; instead of using the strike zone as their reference zone, most hitters likely use some modified zone based on their strengths, the count, and the game situation. Furthermore, it’s not guaranteed that swing decisions function like this at the unconscious level at all; there could be an entirely different process that takes place instead. Nevertheless, the framework is at least plausible, and the assumptions are not unreasonable.

There’s one other assumption that warrants discussion. Namely, I’ve assumed that all MLB hitters can recognize that a middle/middle fastball is a strike at an equal rate.
More specifically, every MLB hitter's projected strike likelihood on middle/middle fastballs (defined by fastballs in zone 5 of Statcast-defined attack zones) can be represented by a normal distribution with a mean of 0.92 and a standard deviation of 0.07.

Sample notes:
All data (besides 2021 leaderboards) is based on 2017-2019 Statcast pitch-by-pitch data.
To qualify for aggressiveness and pitch recognition scores, a hitter must see at least 10 middle/middle fastballs in each count group (hitter's count, pitcher's count, first pitch) and swing at those pitches less than 100% of the time for each count group.
