# Empirical_Bayes_Demo

## Introduction
This project explores a simple application of the empirical Bayes method and compares it to typical frequentist A/B testing methods. The project simulates an experiment that compares a number of test subjects (typically more than two) where each subject can be used interchangeably and the success or failure of the subject is an independant Bernoulli trial with parameter p. For example each subject could be a headline on an article link. In this simulation the true value of p for each subject is known and the purpose is to see how effective the empirical Bayes method is at identifying the subject with the greatest true p parameter, that is, the best test subject.

The method process is: -
1.	Each subject is assigned a Beta distribution where the parameters are the number of successes and failures. The initial parameter values are chosen to reflect the conversion rate of the current or control subject.
2.	For each trial a random value is sampled from the subject distributions and the subject corresponding to the greatest sample value is selected.
3.	The trial is run (or simulated in this case) with the selected subject and the distribution parameters are updated accordingly.
4.	An elimination metric is used to measure the current belief that a particular subject may be the optimal subject. If an elimination metric drops below a threshold value that subject is eliminated from the test.
5.	Steps 2, 3 and 4 are repeated until only one subject remains or the maximum number of trials is reached.

## Conclusions
This method is preferable to the frequentist A/B approach where; there are more than 2 subjects, faster results are required, the solution is applicable for only a short time and you wish to exploit the results during the test by eliminating the worst subjects quickly.
This method is not appropriate where; a false positive result would have serious implications in cost or time, a defined end point is required, updating the subject distributions during the test would be impractical. All these issues could be addressed to some degree by modifications to the method.
Overall the method performed well compared to a frequentist A/B test in the situation where there was a 20% difference between the control and the best treatment. For a smaller sample size (average 3037), greater power (88% versus 80%) was achieved.




 
