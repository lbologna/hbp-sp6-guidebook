.. _multi_crb_gc_collab:

#################################################################
Multi compartmental Cerebellar Granule cell optimization
#################################################################

The cerebellum is part of the central nervous system and functions as a highly 
parallel machine capable of processing sensory and motor information coming 
from the brain, brain steam and spinal cord. For many years it was recognized 
to be critical for motor tasks such as balance and posture. More recently,  
its importance in higher cognitive functions, such as language, cognition and 
fear responses, was recognized.

|

.. container:: bsp-container-center

    .. image:: images/cereb_1.JPG
        :width: 1000px
        :align: left

|

The cerebellum is composed by a limited number of neuronal types arranged in 
three layers: the granular cell layer, the molecular cell layer and the 
Purkinje cell layer. 

Granule cells are the most abundant type of neurons in the entire central 
nervous system and they reach the highest density in the cerebellum, where they
form the granular cell layer together with Golgi, Lugaro and UBC neurons. 

From a morphological point of view, granule cells show a structural 
simplicity, with a small soma, four short dendrites and a long axon (over 4mm) 
that splits into two parts to form the parallel fibers. This simplicity is 
compensated by a complex interaction of many families of ion channels, a 
specific calcium buffer and complex synaptic receptors and plasticity.
During the last three decades many models, both simplified and 
multi-compartmental were built to explore their intrinsic and extrinsic 
physiological properties. 

The multi compartmental granule cell, contained in the Python notebook, is 
composed by: four sections for the dendrites, a single section for the soma, 
Hillock, AIS and Axon and can be optimized with BluePyOpt 
(https://github.com/BlueBrain/BluePyOpt). This tool, using a genetic algorithm 
and specific “features” obtained from experiments, can search for the optimal 
ionic conductances to generate models capable of reproducing the correct 
behaviors of this cell type.
The notebook contains a step-by-step description of each cell, starting with 
the morphological properties, the voltage-dependent ionic channels and the 
optimization parameters. 

The ionic channels mechanisms, passive properties and morphology were taken and 
adapted from a previously published granule cell model (Diwakar *et al.,* 2006) 
(https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835) and used 
for the automatic reconstruction and its validation. The models were originally 
optimized with the BBP Optimizer Framework (Masoli *et al.,* 2017) but were 
later adapted to BluePyOpt with identical results. 

(Code and testing - Stefano Masoli PhD)
