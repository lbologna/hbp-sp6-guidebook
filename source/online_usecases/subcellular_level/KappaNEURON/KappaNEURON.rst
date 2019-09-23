=============
 KappaNEURON
=============

KappaNEURON is a python package that integrates the NEURON simulator
with the SpatialKappa simulator of rule-based models. Rule-based
models allow interactions between the combinatorially large number of
protein complexes in the postsynaptic proteome to be expressed
straightforwardly.

Scientific motivation
=====================

Synaptic plasticity depends on the interaction between electrical
activity in neurons and the synaptic proteome, the collection of over
1000 proteins in the post-synaptic density (PSD) of synapses.

Currently the largest dynamic models of synaptic plasticity contain
around 40 distinct proteins, second messengers and ions [Heil2018]_.
These proteins often have multiple binding sites, allowing large
numbers of distinct complexes (combinations of bound proteins) to
form. For example, calcium can bind to four sites on calmodulin
molecule, and calmodulin bound with varying numbers of calcium ions
can bind to many combinations of sites on CaMKII dodecamers. This
quickly leads to a combinatorial explosion in the number of complexes
that can form in a synapse.

Rule-based models allow specification and simulation of proteins and
protein complexes with combinatorially large numbers of states which
arise from protein-protein interactions, post-translational
modifictions and conformational changes [Stefan2014]_. Second
generation rule-based languages such as Kappa and BNGL have a
well-defined syntax for *rules*, generalized reactions which express
binding between sites and modifications such as phosphorylation.
Simulations of rule-based models are stochastic and thus can deal with
small copy numbers. Rule-based are thus suited to modeling the large
number (order of 100s) of distinct proteins in postsynaptic proteome
many of which exist in small numbers (often <100) due to the
restricted space of the spine head.

In synapses there is an intimate coupling between the molecular and
electrical aspects of neurons: the calcium current entering the
synapse depends both on the membrane potential in the spine head,
which controls the conductance of NMDAR receptors, but also on the
free intracellular calcium, since this influences the I-V relationship
of the channel, which can be modeled using the GHK equations. This
coupling motivated the development of the `KappaNEURON`_ package
[Sterratt2015]_, which integrates `NEURON`_ 7.4 and the `SpatialKappa`_ kappa
simulator. It allows for detailed synaptic models to be simulated in
the context of the electrical activity of the cell, as illustrated
below.

.. image:: images/system.png
   :width: 600 px
           
Example of a rule-based model
=============================

The first use case in the `KappaNEURON use case`_ is a simple
demonstration of using `KappaNEURON`_, a python module, to model a calcium pump. It
demonstrates the principle of how KappaNEURON works, though in
practice there is not particular advantage in using KappaNEURON for
such a simple situation; the second use case gives a more realistic
example in which the benefits of KappaNEURON are apparent.

The Kappa code for a simple calcium pump, which we can imagine as
being in a spine head, is shown below:

.. code:: python  
   :number-lines:
   
   ## File caPump.ka - Simple calcium pump
   ## Agent declarations, showing the agent names and binding sites
   %agent: ca(x) # Calcium with binding site
   %agent: P(x) # Pump molecule with binding site
   
   ## Variable declarations
   %var: ’vol’ 1 # Volume of spine head in um3
   %var: ’NA’ 6.02205E23 # Avogadro’s constant 
   %var: ’agconc’ 1E18/(’NA’ * ’vol’) # Concentration of one agent (in mM) in the volume 
   
   # Rate constants in /mM-ms or /ms, depending on the number of complexes on LHS of rule
   %var: ’k1’ 0.001 # /mM-ms
   %var: ’k2’ 1 # /ms

   ## Rules
   # Note the scaling of the rate constant of the bimolecular reaction
   ’ca binding’ ca(x), P(x) -> ca(x!1), P(x!1) @ ’k1’ * ’agconc’
   ’ca release’ ca(x!1), P(x!1) -> P(x) @ ’k2’

   ## Initialisation of agent numbers
   # Overwritten by NEURON but needed for SpatialKappa parser
   %init: 1000 ca(x)
   %init: 10000 P(x)

   ## Observations
   %obs: ’ca’ ca(x) # Free Ca
   %obs: ’P-Ca’ ca(x!1), P(x!1) # Bound Ca-P
   %obs: ’P’ P(x) # Free P

This model description can be interpreted by Kappa simulators such as
`SpatialKappa`_ or `KaSim`_ version 3, which simulate the model using
a method based on Gillespie's method, in which transitions (here
calcium-pump binding and unbinding events) are simulated one-by-one.
The time between events is random - there is no fixed dt.

A brief description of how this file works is in the `KappaNEURON use
case`_. KappaNEURON allows the user to use this file in place of a NEURON mod
file. NEURON is responsible for telling the Kappa model how much
calcium should be created as a result of ion channels or receptors.

|

   Kappa syntax

   There is a short description of Kappa syntax in Section 2.1 of the
   `SpatialKappa manual`_. A full description of version 3 of the
   Kappa language can be found in chapters 4 and 6 of the `KaSim 3.5
   manual`_. SpatialKappa differs from KaSim 3 in that it adds spatial
   extensions (not used in KappaNEURON) and does not implement the
   perturbation language (Chapter 6 of the `KaSim 3.5 manual`_) fully.
   The syntax of version 4 of the Kappa language is different from
   version 3, used by SpatialKappa. This may be updated in the future.
   
|

Principle of integration
========================

.. image:: images/integration.png
   :width: 400 px

|

   Implementation 

   KappaNEURON is a python module. It links NEURON and SpatialKappa
   via the ``rxd`` (reaction diffusion) subystem of NEURON 7.4 and the
   python interface to SpatialKappa, which in turn depends on the py4j
   module to link the Java core of SpatialKappa with python.

|

KappaNEURON integrates the NEURON and SpatialKappa parts of the
simulations by running them alternately every NEURON Δt (typically
25μs), and synchronizing at every timestep so that the charge in the
Kappa simulation is consistent with the membrane potential.
           
The procedure KappaNEURON uses to update the time from t to t + Δt is:

1. Pass all relevant variables from NEURON to Kappa, e.g. conductances
   and voltages needed to compute the membrane current through
   channels.

2. Run the rule-based simulator from t to t + Δt.
   
3. Compute the net change in the total number of each bridging species
   S (including in any complexes) over the time step and convert back
   to a current, which is then passed to NEURON.

4. Run NEURON forward by Δt.

For full details of the integration see [Sterratt2015]_.


Demonstration
=============

The use case in the `KappaNEURON use case`_ demonstrates and documents the python
code required to run the example simulation.

References
==========

|

.. [Heil2018] Heil K. F., Wysocka. E., Sorokina, O., Kotaleski, J. H.,
              Simpson, T. I., Armstrong, J. D., Sterratt, D. C.
              (2018). ‘Analysis of proteins in computational models of
              synaptic plasticity’.
              `doi:10.1101/254094 <https://doi.org/10.1101/254094>`_.
              `bioRxiv:254094
              <https://www.biorxiv.org/content/early/2018/01/28/254094>`_

.. [Stefan2014] Stefan M. I., Bartol T. M., Sejnowski, T. J.,
                Kennedy M. B. (2014). 'Multi-state Modeling of
                Biomolecules' PLOS Comp. Biol. 10.
                `doi:10.1371/journal.pcbi.1003844
                <https://doi.org/10.1371/journal.pcbi.1003844>`_
              
.. [Sterratt2015] Sterratt, D. C., Sorokina, O. and Armstrong, J. D.
                  (2015). ‘Integration of rule-based models and
                  compartmental models of neurons’. In O. Maler, Á.
                  Halász, T. Dang and C. Piazza, eds., Hybrid Systems
                  Biology: Second International Workshop, HSB 2013,
                  Taormina, Italy, September 2, 2013 and Third
                  International Workshop, HSB 2014, Vienna, Austria,
                  July 23-24, 2014, Revised Selected Papers, vol. 7699
                  of Lecture Notes in Bioinformatics, pp. 143–158.
                  Springer International Publishing, Cham. `doi:
                  10.1007/978-3-319-27656-4_9
                  <https://doi.org/10.1007/978-3-319-27656-4_9>`_.
                  Preprint at `arXiv:1411.4980
                  <http://arxiv.org/abs/1411.4980>`_

.. _KappaNEURON: https://github.com/davidcsterratt/KappaNEURON
.. _SpatialKappa: https://github.com/davidcsterratt/SpatialKappa
.. _SpatialKappa manual: https://github.com/davidcsterratt/SpatialKappa/blob/master/docs/manual/SpatialKappaManual-v2.1.0.pdf
.. _KaSim 3.5 manual: https://github.com/davidcsterratt/SpatialKappa/blob/master/docs/manual/KaSim_manual_v3.5.pdf                       
.. _KappaNEURON use case: https://collab.humanbrainproject.eu/#/collab/2184/nav/204920
.. _KaSim: https://github.com/Kappa-Dev/KaSim
.. _NEURON: https://neuron.yale.edu/neuron/

..  LocalWords:  KappaNEURON PSD Sterratt CaMKII BNGL GHK px caPump
..  LocalWords:  SpatialKappa ka agconc mM LHS init KaSim dt Heil rxd

..  LocalWords:  dodecamers generalized modeled subystem py
..  LocalWords:  BSP Collab Wysocka Sorokina Kotaleski bioRxiv Maler
..  LocalWords:  Halász HSB Taormina Springer Cham doi Preprint
