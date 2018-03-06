.. _sim_pc_multi_collab:

#################################################################
Simulation and validation of a mouse Purkinje cell multicompartmental model
#################################################################

The Purkinje cells are one of oldest and most complex neuron of the entire central nervous system. 
Their purpose is to integrate thousands of synaptic inputs coming from the cerebellar granular layer and the molecular layer interneurons. 
During the last six decades, many Purkinje cell models were built to explore their physiological properties but only in 1994 it was built the first 
multicompartmental model with HH ionic channels and 3D reconstructed morphology. 
That model was rebuilt with new passive, active and axonal properties (Masoli et al., 2015).

Since the computational impact is very high, with each optimization requiring, at least, 30 hours
to complete 256 individuals and 7 generations, it was decided to not include this step into the notebook.

The notebook contains a step by step description of each cell starting from the visualization of the available results, 
to the actual analysis of the voltage/time traces and the definition of a set of parameters to validate the correct physiological results. 
The final step is to test each validated individual for the absence of the Axon Initial Segment (AIS) sodium channels. 
If a cell is still able to generate spontaneous firing, even without sodium channels then is discarded as a non physiological Purkinje cell. 
Only not spiking models, without sodium channels in the AIS, are correct. 

The ionic channel mechanisms, passive properties, morphology were taken 
and adapted from a previous published guinea pig Purkinje cell model (Masoli et al,. 2015; Masoli and D'Angelo, 2017) 
(https://senselab.med.yale.edu/modeldb/ShowModel.cshtml?model=229585) and used in the automatic reconstruction and its validation. 

(Code and testing - Stefano Masoli PhD)
