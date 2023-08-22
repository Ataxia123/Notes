

by [Leipzig University](http://www.uni-leipzig.de/en/)
[[MonteCarloNotes]]

![Breakthrough in Monte Carlo computer simulations](https://scx1.b-cdn.net/csz/news/800a/2023/breakthrough-in-monte.jpg "Visualization of the decision process on the new state of the spin (shown in red) of a ferromagnetic system with long-range interactions. Credit: Leipzig University")

Visualization of the decision process on the new state of the spin (shown in red) of a ferromagnetic system with long-range interactions. Credit: Leipzig University

Researchers at Leipzig University have developed a highly efficient method to investigate systems with long-range interactions that were previously puzzling to experts. These systems can be gases or even solid materials such as magnets whose atoms interact not only with their neighbors but also far beyond.

Professor Wolfhard Janke and his team of researchers use Monte Carlo [computer simulations](https://phys.org/tags/computer+simulations/) for this purpose. This stochastic process, named after the Monte Carlo casino, generates random system states from which the desired properties of the system can be determined. In this way, Monte Carlo simulations provide deep insights into the physics of phase transitions.

The researchers have developed a [new algorithm](https://phys.org/tags/new+algorithm/) that can perform these simulations in a matter of days, which would have taken centuries using conventional methods. They have published their new findings in the journal _Physical Review X_.

A physical system is in equilibrium when its macroscopic properties such as pressure or temperature do not change over time. Nonequilibrium processes occur when environmental changes push a system out of equilibrium and the system then seeks a new state of equilibrium.

"These processes are increasingly becoming the focus of attention for statistical physicists worldwide. While a large number of studies have analyzed numerous aspects of nonequilibrium processes for systems with short-range interactions, we are only just beginning to understand the role of long-range interactions in such processes," explains Janke.

## The curse of long-range interactions

For short-range systems whose components interact only with their short-range neighbors, the number of operations needed to calculate the evolution of the entire system over time increases linearly with the number of components it contains. For long-range interacting systems, the interaction with all other components, even distant ones, must be included for each component. As the size of the system grows, the runtime increases quadratically.

A team of scientists led by Professor Janke has now succeeded in reducing this algorithmic complexity by restructuring the algorithm and using a clever combination of suitable data structures. In the case of large systems, this leads to a massive reduction in the required computing time and allows completely new questions to be investigated.

## New horizons opened

The article shows how the new method can be efficiently applied to nonequilibrium processes in systems with [long-range interactions](https://phys.org/tags/long-range+interactions/). One example describes spontaneous ordering processes in an initially disordered "hot" system, in which following an abrupt temperature drop ordered domains grow with time until an ordered equilibrium state is reached.

From our daily lives, we know that when we take a hot shower and there is a cold window nearby, droplets will form on the window. The hot steam cools down quickly and the droplets get larger. A related example are processes with controlled slower cooling rates, where the formation of vortices and other structures is of particular interest as these play an important role in cosmology and in [solid state physics](https://phys.org/tags/solid+state+physics/).

In addition, researchers at the Institute of Theoretical Physics have already successfully applied the algorithm to the process of phase separation, in which, for example, two types of particles spontaneously separate. Such nonequilibrium processes play a fundamental role both in [industrial applications](https://phys.org/tags/industrial+applications/) and in the functioning of cells in biological systems. These examples illustrate the wide range of application scenarios that this methodological advance offers for basic research and practical applications.

Computer simulations form the third pillar of modern physics, alongside experiments and analytical approaches. A large number of issues in physics can only be approached approximately or not at all with analytical methods. With an experimental approach, certain issues are often difficult to access and require complex experimental set-ups, sometimes lasting years. Computer simulations have therefore contributed significantly to the understanding of a broad spectrum of physical systems in recent decades.