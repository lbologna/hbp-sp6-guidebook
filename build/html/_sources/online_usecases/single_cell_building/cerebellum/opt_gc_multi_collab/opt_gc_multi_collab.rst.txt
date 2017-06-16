.. opt_gc_multi_collab:

#############################################################
Multi compartmental Cerebellar Granule cell running on collab
#############################################################

Multi compartmental Cerebellar Granule cell optimization, performed with BluePyOpt, direcly on the collab (Code and testing - Stefano Masoli PhD). 

|

The ionic channels mechanisms, the passive properties and the morphology were taken and adapted from a previous published granule cell model (Diwakar et al., 2006) (https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835) and used in the automatic reconstruction and validation of the granule cells, using the BBP Optimizer Framework (Masoli et al., 2017). Information about the generation of the morphology can be found in the paper.

|

The code is commented, step by step, to define what is done in each ipython cell.


Note - Each notebook cell has two square bracket on the left. 
	1.	When they are empty, it means that the code was never started before.
	2.	When there is an asterisk [*], it means that the code is running.
	3.	When there is a number, it means that the code was run. A progressive numbering scheme defines the order in which the cells were selected.


.. container:: bsp-container-center

    .. image:: images/main.png
        :width: 1000px
        :align: left

|

Fig. 1 – This optimization can be run on the collab but, since the intensive computational power required to run all the simulations, it is better not to use more than 4 individuals and 4 generations. Since this limitation, each run can generate a single model with a different degree of quality. 

|
|

.. container:: bsp-container-center

    .. image:: images/custom.png
        :width: 1000px
        :align: right

|

Fig. 2 - This custom class define the parameters and section to create to built an axon composed by specific sections. It is used to define the temperature, Vinit and the tables used in the MOD files too.

|
|

.. container:: bsp-container-center

    .. image:: images/run.png
        :width: 1000px
        :align: right

|

Fig. 3 – To run the optimization, it is necessary to download some files from the collab storage to the place where the python notebook will run. 
The file downloaded are the neuron morphology and the ionic channels.

|
|

.. container:: bsp-container-center

    .. image:: images/morph.png
        :width: 1000px
        :align: right

|

Fig. 4 – This part of the code defines which morphology to load, if the axon has to be replaced by the previous Class and the locations, where we will insert the channels. The basic sectionlists are somatic, axonal, apical and basal.  It is possible to define custom sections and sectionslists.

|
|

.. container:: bsp-container-center

    .. image:: images/info_passive.png
        :width: 1000px
        :align: right

|

Fig. 5 – This cell contains all the information to place the passive properties, with specific parameters, on the morphological locations defined before. For example: the membrane capacitance on all sections, will have a name cm_all, a param name taken from the mod file, the value, the location and the fact that is not a range (frozen = True)

|
|

.. container:: bsp-container-center

    .. image:: images/ionic_mec.png
        :width: 1000px
        :align: right

|

Fig. 6 - The ionic mechanism are loaded and inserted in the respective sections, defining which is each channel suffix, based on the information taken from the MOD files.

|
|

.. container:: bsp-container-center

    .. image:: images/channel_conduct.png
        :width: 1000px
        :align: right

|

Fig. 7 – Each channel is provided with a conductance range, location and name.

|
|

.. container:: bsp-container-center

    .. image:: images/cell_all.png
        :width: 1000px
        :align: right

|

Fig. 8 – This is the cell in which we put together the morphology, the passive and active properties to generate the cell template.

|
|

.. container:: bsp-container-center

    .. image:: images/el_location.png
        :width: 1000px
        :align: right

|

Fig. 9 – Electrode location, used both to deliver the current and to record the voltage.

|
|

.. container:: bsp-container-center

    .. image:: images/stimuli.png
        :width: 1000px
        :align: right

|

Fig. 10 - Stimuli, recordings location and protocols. For each protocol can be defined a recording location and a stimulus, in this case, both are in the soma

|

The default parameters are the conductances which were known to produce a working model. Here are present to compare the results of the optimization with a reference.

|
|

.. container:: bsp-container-center

    .. image:: images/features.png
        :width: 1000px
        :align: right

|

Fig. 11 – Features name and their parameter. They were obtained, with efel, from traces recorded, in vitro, from mice (Masoli et al., 2017).

|
|

.. container:: bsp-container-center

    .. image:: images/cell_eval.png
        :width: 1000px
        :align: right

|

Fig. 12 – The cell evaluator is in charge of putting together the model template and the parameter we want to search in the optimization.

|
|

.. container:: bsp-container-center

    .. image:: images/opt_gen.png
        :width: 1000px
        :align: right

|

Fig. 13 – The optimization requires and certain number of individual and generation. More individual, more combination will be tested. 

|
|

.. container:: bsp-container-center

    .. image:: images/eval_best.png
        :width: 1000px
        :align: right

|

Fig. 14 – Evaluation of the best individual based on each simulations

|
|

.. container:: bsp-container-center

    .. image:: images/plot_best.png
        :width: 1000px
        :align: right

|

Fig. 15 - Plot of the best individual and the min fitness obtained during the optimization

|
|

