.. _sim_pc_multi_collab:

###########################################################################
Simulation and validation of a mouse Purkinje cell multicompartmental model
###########################################################################

Purkinje cells are part of the oldest and most complex neurons of the entire 
central nervous system. Their function is to integrate thousands of synaptic 
inputs coming from the cerebellar granular layer and the molecular layer 
interneurons. 
During the last six decades, many Purkinje cell models were built to explore 
their physiological properties. Only in 1994, the first 
multicompartmental model with HH ionic channels and a 3D reconstructed 
morphology was built. 
This model was rebuilt with new passive, active and axonal properties (Masoli 
*et al.,* 2015).

The computational impact is very high, as each optimization requires at least
30 hours to complete 256 individuals and 7 generations. Therefore, this step is
not included in the notebook.

The notebook contains a step-by-step description of each cell, starting with 
the visualization of the available results, to the actual analysis of the 
voltage/time traces and the definition of a set of parameters to validate the 
physiological results. 
The final step is to test each validated individual cell for the absence of the 
Axon Initial Segment (AIS) sodium channels. 
If a cell is still able to generate spontaneous firing, even without sodium 
channels, it is discarded as a non-physiological Purkinje cell. 
Only not-spiking models, without sodium channels in the AIS, are considered as 
correct. 

The ionic channel mechanisms, passive properties and morphology were taken 
and adapted from a previously published guinea pig Purkinje cell model (Masoli 
*et al,.* 2015; Masoli and D'Angelo, 2017) 
(https://senselab.med.yale.edu/modeldb/ShowModel.cshtml?model=229585) and used 
for the automatic reconstruction and its validation. 

(Code and testing - Stefano Masoli PhD)
