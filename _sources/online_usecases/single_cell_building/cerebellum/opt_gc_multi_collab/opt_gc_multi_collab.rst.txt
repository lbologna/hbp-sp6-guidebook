.. _multi_crb_gc_collab:

#################################################################
Multi compartmental Cerebellar Granule cell optimization
#################################################################

The cerebellum is part of the central nervous system and functions as a highly parallel machine capable of processing sensory and motor information coming from the brain, brain steam and spinal cord. For many years it was recognized critical in motor tasks such as balance and posture but, in recent years, was addressed its importance in higher cognitive functions such as language, cognition and fear responses.
|

.. container:: bsp-container-center

    .. image:: images/cereb_1.JPG
        :width: 1000px
        :align: left

|

The cerebellum is composed by a limited number of neuronal types arranged in three layers: the granular cell layer, the molecular cell layer and the Purkinje cell layer. 

The granule cells are the most abundant type of neurons in the entire central nervous system and they reach the highest density in the cerebellum, where, together with Golgi, Lugaro and UBC neurons, form the granular cell layer. 

From a morphological point of view, the granule cells show a structural simplicity, with a small soma, four short dendrites and a long axon (over 4mm) that splits into two parts to form the parallel fibers. This simplicity is compensate by a complex interaction of many families of ionic channels, a specific calcium buffer and complex synaptic receptors and plasticites.
During the last three decades many models, both simplified and multi-compartmental were built to explore their intrinsic and extrinsic physiological properties. 

The multi compartmental granule cell, contained in the Python notebook, is composed by: four sections for the dendrites, a single section for the soma, Hillock, AIS and Axon and can be optimized with BluePyOpt (https://github.com/BlueBrain/BluePyOpt). This tool, using a genetic algorithm and specific “features” obtained from experiments, can search for the optimal ionic conductances to generate models capable of reproducing the correct behaviors of this kind of cell.
The notebook contains a step by step description of each cell starting with the morphological properties, the voltage dependent ionic channels and the optimization parameters. 

The ionic channels mechanisms, passive properties, morphology were taken and adapted from a previous published granule cell model (Diwakar et al., 2006) (https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835) and used in the automatic reconstruction and its validation.  The models were originally optimized with the BBP Optimizer Framework (Masoli et al., 2017) but were later adapted to BluePyOpt obtaining identical results. 

(Code and testing - Stefano Masoli PhD)
