# rebuttal

Today the review comments of our CVPR paper has come out. The ranking is 335. Since this year the rank has 6 levels, getting accepted is not just a theortical possibility. Get ready for the rebuttal.

## Review 1
His word is really insightful and accurately points out our strengths and weaknesses.

In conclusion, our main problems lie in:
* not able to recover global structure.
* sensitive to parameter choice.
* heavily rely on initial estimation.
* illumination has to be known.

Rebuttal:
* the introduction of global constraint would significantly slow down the efficiency of algorithm.
* algo is quick, so we can search in an interval to find the one with the best performance. AND one dataset we only need to change the \alpha and \beta once.
* our initial estimation is accurate enough.
* we only assume the illumination is known; (when the light condition is simple,) we can subtract the illumination info. using Zheng et al.'s method.

## Review 2
Why not compare the case that takes 8 best bands with that takes PCA? 

(He rised an example about high-resolution downsampling and low-resolution; I am still wonder about the reasonability of this weakness.)

Rebuttal:
* Zheng's method?
* (Is this analogy reasonable?)

## Review 3
* Experiments: hard to interpret; lack enough experiment; fail to overperform peer method; lack persuasiveness since no RGB cases result.
* why not base on most recent work?
* why apply low rank nature in image domain rather than logarithmic domain?
* caption; redefine Esc and Erc; typo.

Rebuttal:
* ... really lack in experiments. Add some in rebuttal. Overperform Chen's algo both in time and accuracy; RGB could not use LR, but ... (more easy to interpret? Maybe)
* Time consuming with minor improvement in performance. Try to reach a trade-off between accuracy and time.
* based on Zheng's, image domain is clear; while the log domain still needs to be proved.
* caption is not wrong; not redefine but reWRITE; typos... yes, there are some typos

## Task
* database needs posting on the web.
* more persuasive experiments.

