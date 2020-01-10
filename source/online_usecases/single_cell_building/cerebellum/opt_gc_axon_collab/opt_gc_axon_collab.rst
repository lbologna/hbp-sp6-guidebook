.. _opt_gc_axon_collab:

##############################################
Custom Axon Cerebellar Granule cell simulation
##############################################

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

Granule cells (5) are the most abundant type of neurons in the entire central 
nervous system and they reach the highest density in the cerebellum, where they
form the granular cell layer (3) together with Golgi (6), Lugaro (9) and UBC neurons (8). 
They receive excitatory synaptic inputs from the mossy fibers (1) and inhibitory inputs from
Golgi (6) and Purkinje cells (PC).

From a morphological point of view, granule cells show a structural 
simplicity, with a small soma, four short dendrites and a long axon (over 4mm) 
that splits into two parts to form the parallel fibers (4). This simplicity is 
compensated by a complex interaction of many families of ion channels, a 
specific calcium buffer and complex synaptic receptors and plasticity.
During the last three decades many models, both simplified and 
multi-compartmental were built to explore their intrinsic and extrinsic 
physiological properties [1]. 

The "Custom Axon Cerebellar Granule cell" usecase contains the 2019 version
of the multicompartmental granule cell model. The model is composed by: four dendrites, soma, Hillock, 
AIS, a custom built multisection Ascending Axon (7 sections) and two 1mm long Parallel Fibers (over 140 sections each) [2].

The purpose of this usecase is to show that, with custom code, BluePyOpt allows the definition
of custom sectionlists which can be used to increase the morphological complexity of a model. 
This approach can be used to define different locations in the dendritic tree too.

The notebook contains a step-by-step description of each cell, starting with the morphological properties, 
the voltage-dependent ionic channels and the conductances obtained from the optimization. Some of the
cells contain code examples and explanations on how to use and integrate the custom code into the main
optimization code. 

Some of the ionic channels mechanisms, passive properties and morphology were taken from a previously published 
granule cell mode [3]. 
The rest of the ionic channels were taken from a published Purkinje cell model [4]. 
The custom Ascending Axon, Parallel Fibers and FHF nav1.6 sodium channel were built following experimental data obtained from granule cell [5][6].

|

**Bibliography**

[1] D’Angelo, E., Antonietti, A., Casali, S., Casellato, C., Garrido, J. A., Luque, N. R., … Ros, E. (2016). 
Modeling the Cerebellar Microcircuit: New Strategies for a Long-Standing Issue. Frontiers in Cellular Neuroscience, 10, 176.

[2] Masoli, S., Tognolina, M., & Angelo, D. (2019). Parameter tuning differentiates granule cell
subtypes enriching the repertoire of retransmission properties at the cerebellum input stage.

[3] Diwakar, S., Magistretti, J., Goldfarb, M., Naldi, G., & D’Angelo, E. (2009). Axonal Na+ channels 
ensure fast spike activation and back-propagation in cerebellar granule cells. Journal of Neurophysiology, 101(2), 519–532.

[4] Masoli, S., Solinas, S., & D’Angelo, E. (2015). 
Action potential processing in a detailed Purkinje cell model reveals a critical role for axonal compartmentalization. 
Frontiers in Cellular Neuroscience, 9(February), 1–22.

[5] Dover, K., Solinas, S., D’Angelo, E., & Goldfarb, M. (2010). Long-term inactivation particle for voltage-gated sodium channels. 
The Journal of Physiology, 588(Pt 19), 3695–3711.

[6] Dover, K., Marra, C., Solinas, S., Popovic, M., Subramaniyam, S., Zecevic, D., … Goldfarb, M. (2016). 
FHF-independent conduction of action potentials along the leak-resistant cerebellar granule cell axon. 
Nature Communications, 7, 12895. 

(Code and testing - Stefano Masoli PhD)
