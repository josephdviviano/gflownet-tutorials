

I would start with explaining how a set of constraints can be turned into our famiilar squared loss of log ratios making it possible to learn both a sampler and its marginalizer (the partition function) with an off-policy style (i.e., a training policy that can be different from the currently learned sampler). In my mind this should really be the starting point even before we talk about trajectories, flows and all that. A demo could show first the unconditional case (sampling something that can be done autoregressively, i.e., there is no need for a PF/PB, just a sampler Q is enough). Then I would show the conditional case, which illustrates how to obtain a conditional sampler and a marginalizer (a conditional partition function).

Then only I would explain the more tricky case where there are many ways to sample the object of interest (such as a set or a graph) and we need to introduce a notion of trajectory tau as well as a backward transition policy PB. I would start by showing the extension of the above loss in that case, where Q is replaced by PF/PB and you basically get TB.

Then I would explain the notion of flow and illustrate it with DB, and explain the relation between DB and TB (in particular how the DB constraints when plugged together give rise to the TB constraint (and thus the TB loss), with the flows disappearing from the required parametrization.

At this point, I would go into demos illustrating some of the "tricks of the trade" in terms of optimization, such as how to choose the training policy (so far), why a separate learning rate tends to work better for log Z (or even use a different kind of average - since the SGD update on log Z amounts to an exponential moving average of the other terms inside the square).

Then we may have other demos to illustrate some of the more advanced losses, such as subTB and FL-GFN.

Then I would have a demo for GFN-EM and another for EB-GFN, along with optimization tricks that have turned out useful for them.


