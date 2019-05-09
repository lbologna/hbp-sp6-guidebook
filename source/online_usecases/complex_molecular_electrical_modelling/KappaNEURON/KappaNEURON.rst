=============
 KappaNEURON
=============

Scientific Motivation
=====================

Synaptic plasticity depends on the interaction between electrical
activity in neurons and the synaptic proteome, the collection of over
1000 proteins in the post-synaptic density (PSD) of synapses.

Currently the largest dynamic models of synaptic plasticity contain
around 40 distinct proteins, second messengers and ions [Sterratt
ref]. These proteins often have multiple binding sites, allowing large
numbers of distinct complexes (combinations of bound proteins) to
form. For example, calcium can bind to four sites on calmodulin
molecule, and calmodulin bound with varying numbers of calcium ions
can bind to many combinations of sites on CaMKII dodecamers. This
quickly leads to a combinatorial explosion in the number of complexes
that can form in a synapse. 

Rule-based models allow interactions between the combinatorially large
number of protein complexes in the postsynaptic proteome to be
expressed straightforwardly. Simulations of rule-based models are
stochastic and thus can deal with the small copy numbers of proteins
and complexes in the PSD. Second generation rule-based languages such
as Kappa and BNGL allow rules (essentially generalised reactions) to
be expressed using a well-defined syntax. Their associated simulators
allow these model definitions to be simulated.

In synapses there is an intimate coupling between the molecular and
electrical aspects of neurons: the calcium current entering the
synapse depends both on the membrane potential in the spine head,
which controls the conductance of NMDAR receptors, but also on the
free intracellular calcium, since this influences the I-V relationship
of the channel, which can be modelled using the GHK equations. This
coupling motivated the development of the KappaNEURON package, which
integrates NEURON and the SpatialKappa kappa simulator. It allows for
detailed synaptic models to be simulated in the context of the
electrical activity of the cell, as illustrated below.

.. image:: images/system.png
   :width: 600 px
           
Example of a rule-based model
=============================

The first use case in the collab (currently at
https://collab.humanbrainproject.eu/#/collab/2184/nav/204920) is a
simple demonstration of using KappaNEURON to model a calcium pump. It
demonstrates the principle of how KappaNEURON works, though in
pracitice there is not particular advantage in using KappaNEURON for
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

This file could be interpreted by Kappa simulators such as
SpatialKappa or KaSim, and simulated using a method based on
Gillespie's method, in which transitions (here calcium-pump binding
and unbinding events) are simulated one-by-one. The time between
events is random - there is no fixed dt.

KappaNEURON allows the user to use this file in place of a NEURON mod
file. NEURON is responsible for telling the Kappa model how much
calcium should be created as a result of ion channels or receptors.

.. sidebar:: Comment
   
   Should I describe this kappa file in more depth? It's covered to an
   extent in the python notebook.
  
Principle of integration
========================

.. image:: images/integration.png
   :width: 400 px

KappaNEURON integrates the NEURON and SpatialKappa parts of the
simulations by running them alternately every NEURON Δt (typically
25μs), and synchronising at every timestep so that the charge in the
Kappa simulation is consistent with the membrane potential.
           
The procedure KappaNEURON uses to update the time from t to t + Δt
(Fig. 2) is:

1. Pass all relevant variables from NEURON to Kappa, e.g. conductances
   and voltages needed to compute the membrane current through
   channels.

2. Run the rule-based simulator from t to t + Δt.
   
3. Compute the net change in the total number of each bridging species
   S (including in any complexes) over the time step and convert back
   to a current, which is then passed to NEURON.

4. Run NEURON forward by Δt.
           
Demonstration
=============

The use case in the BSP collab demonstates and documents the python
code required to run the example simulation.

   
..  LocalWords:  KappaNEURON PSD Sterratt CaMKII BNGL GHK px caPump
..  LocalWords:  SpatialKappa ka agconc mM LHS init KaSim dt
