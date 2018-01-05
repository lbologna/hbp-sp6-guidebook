.. _multi_crb_gc_collab:

#################################################################
Multi compartmental Cerebellar Granule cell running on the collab
#################################################################

Multi compartmental cerebellar granule cell optimized with BluePyOpt.

The granule cells are the most abundant type of neuron in the cerebellum and, togheter with the Golgi cells, form the granule cell layers. 
During the last two decades many granule cell models were built to explore their physiological properties. 

The Python notebook contains the code to optimize, with BluePyOpt, a multi compartmental cerebellar granule cell, using the computational resources provided on the collab.
The notebook contains a step by step description of each notebook cell starting with the morphology, to the definition of custom section lists for the axon, the voltage dependent ionic channels and the optimization parameters. 

The ionic channels mechanisms, passive properties, morphology were taken and adapted from a previous published granule cell model (Diwakar et al., 2006) (https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835) and used in the automatic reconstruction and its validation. 
The models were originally obtained using the BBP Optimizer Framework (Masoli et al., 2017) but it later adapted to BluePyOpt with identical results. 

Information about how to convert a morphology type, for example neuron to SWC or neurolucida, to be used in the optimization procedure, can be found in the previosly mentioned paper.

(Code and testing - Stefano Masoli PhD)
