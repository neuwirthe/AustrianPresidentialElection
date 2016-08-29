# AustrianPresidentialElection

This project holds data and code for a paper about statistical analyses 
of possible manipulations of the results of the Austrian Presidential Election 2015

[ChartsAndProbabilities.html](ChartsAndProbabilities.html) 
will not be displayed from Github, but you can download it and
display it locally.

Among other things, we compute a probability
for the election having a result which would make Hofer the winner
(Hofer lost by 30863 votes).

The base for our charts and a computations are the counts of the
mail votes and the ballot votes for the 117 Austrian election districts.

Plots of the percentages of ballot and votes for candidate Hofer 
clearly display a strong linear relationship
between the results.

The Constitutional Court declared 11 districts as "contaminated"
because of violations of the rules for counting procedure.

Therefore, we compute a linear model for 106 districts considered "clean"
by the constitutional court.

Using this model, we can compute a prediction interval for the the total
result in the 11 contaminated districts for any given confidence level.

We need something slightly different: the probability of the official result
for Hofer being large enough to make Hofer the winner. 

To compute this predicion interval probability,
we compute a prediction interval for 95% level using
the classical prediction estimator for linear models build into R
(which uses a rescaled t-disribution),
extract the value by which the t-distribution for this prediction has been rescaled,
and use this scale value to compute the probability for the prediction interval with
the "winning target value" at the upper limit. From this, we can easily compute
the probability of "Hover wins" result, assuming that our lieanr model describes
the statistical relationship fore ballot and mail votes in all the districts
(which is definitely supported by the plots).



