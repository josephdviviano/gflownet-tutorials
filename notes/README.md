

I would start with explaining how a set of constraints can be turned into our famiilar squared loss of log ratios making it possible to learn both a sampler and its marginalizer (the partition function) with an off-policy style (i.e., a training policy that can be different from the currently learned sampler). In my mind this should really be the starting point even before we talk about trajectories, flows and all that. A demo could show first the unconditional case (sampling something that can be done autoregressively, i.e., there is no need for a PF/PB, just a sampler Q is enough). Then I would show the conditional case, which illustrates how to obtain a conditional sampler and a marginalizer (a conditional partition function).

Then only I would explain the more tricky case where there are many ways to sample the object of interest (such as a set or a graph) and we need to introduce a notion of trajectory tau as well as a backward transition policy PB. I would start by showing the extension of the above loss in that case, where Q is replaced by PF/PB and you basically get TB.

Then I would explain the notion of flow and illustrate it with DB, and explain the relation between DB and TB (in particular how the DB constraints when plugged together give rise to the TB constraint (and thus the TB loss), with the flows disappearing from the required parametrization.

At this point, I would go into demos illustrating some of the "tricks of the trade" in terms of optimization, such as how to choose the training policy (so far), why a separate learning rate tends to work better for log Z (or even use a different kind of average - since the SGD update on log Z amounts to an exponential moving average of the other terms inside the square).

Then we may have other demos to illustrate some of the more advanced losses, such as subTB and FL-GFN.

Then I would have a demo for GFN-EM and another for EB-GFN, along with optimization tricks that have turned out useful for them.

---

I like the idea of presenting TB before DB as the latter also involves the flow function!

I think the following structure may have the potential to enhance readers' understanding of GFNs by incorporating empirical success alongside mathematical concepts.

- Introduction:
Starting from introducing GFN and amortized marginalization, the basic notions, the 3 basic flow consistency constraints at different levels (FM, TB, DB), and corresponding implementation considerations (e.g., larger lr for learning Z)

- Advancements:
After we have covered the basics, we can introduce more advanced design aspects, e.g., long-horizon planning, sparser rewards, and other relevant considerations. I think we can also talk about the extensions of the formulations to continuous and stochastic cases here.

- Connection to variational methods and RL:
After we have introduced the fundamentals of GFNs, I think it would be beneficial for discussing their relationship with other approaches for readers to better connect them. We can explore its connections to variational methods and RL here.

- Fruitful Applications:
We can finally discuss fruitful applications that have emerged from GFN research, which will highlight the practical importance and wide-ranging possibilities that GFN offers.

I think it will enable readers to have a better understanding of GFN's power and potential by combining the theoretical concepts, recent empirical successes, implementation and codebases, and its fruitful applications.

