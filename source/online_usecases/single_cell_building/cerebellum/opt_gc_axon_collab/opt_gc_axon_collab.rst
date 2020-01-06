.. _multi_crb_gc_collab:

#################################################################
Multi compartmental Cerebellar Granule cell (2019) custom axon
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

The "Custom Axon Cerebellar Granule cell" usecase contains the 2019 version
of the multicompartmental granule cell model (Masoli et al, 2019). The model is composed by: 
four dendrites, soma, Hillock, AIS, a custom built multisection Ascending Axon (7 sections)
and two 1mm long Parallel Fibers (over 140 sections each).

The purpose of this usecase is to show that, with custom code, BluePyOpt allows the definition
of custom sectionlists which can be used to increase the morphological complexity of a model. 
This approach can be used to define different locations in the dendritic tree too.

The notebook contains a step-by-step description of each cell, starting with the morphological properties, 
the voltage-dependent ionic channels and the conductances obtained from the optimization. Some of the
cells contain code examples and explanations on how to use and integrate the custom code into the main
optimization code. 

Some of the ionic channels mechanisms, passive properties and morphology were taken from a previously published 
granule cell model (Diwakar *et al.,* 2006) (https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835). 
The custom Ascending Axon, Parallal Fibers were built following published morphological data (Dover et al, 2016).
Some of the ionic channels were taken or modified from (Masoli et al.,2015).

Further information can be found on Biorxiv - https://www.biorxiv.org/content/10.1101/638247v1

(Code and testing - Stefano Masoli PhD)
