.. opt_gc_single_collab:

################################################################
Mono compartmental Cerebellar Granule cell running on the collab
################################################################

The model is an adaptation of a mono compartmental granule cell NEURON model (D'Angelo et al., 2001)

https://senselab.med.yale.edu/modeldb/showModel.cshtml?model=116835

|

INFO

Since the intensive computational power required to run all the simulations, this optimization can be run on the collab with a max of 4 individuals for only 4 generations.

The results can go from not acceptable models to good results, depending on the optimization.

Each notebook cell has two square brackets on the left. When there is a number it means that the cell can be started. When, instead, an asterisk [*] is present it means that the code in that cell is running.

|
|

.. container:: bsp-container-center

    .. image:: images/opt_run_param.png
        :width: 1000px
        :align: left

|

Fig. 1 – This optimization can be run on the collab but, given the intensive computational power required to run all the simulations, it is better not to use more than 4 individuals and 4 generations. Because of this limitation, each run can generate a single model with a different degree of quality.

|
|

.. container:: bsp-container-center

    .. image:: images/custom.png
        :width: 1000px
        :align: left

|

Fig. 2 - This custom class defines the parameters and section to create to build an axon composed by specific sections. It is used to define the temperature, Vinit and the tables used in the MOD files too.

|
|

.. container:: bsp-container-center

    .. image:: images/files.png
        :width: 1000px
        :align: left

|

Fig. 3 – To run the optimization, it is necessary to download some files from the collab storage to the place where the python notebook will run. 
The file downloaded are the neuron morphology and the ionic channels.

|
|

.. container:: bsp-container-center

    .. image:: images/morph.png
        :width: 1000px
        :align: left

|

Fig. 4 – This part of the code defines which morphology to load, if the axon has to be replaced by the previous Class and the locations, where we will insert the channels. The basic sectionlists are somatic, axonal, apical and basal.  It is possible to define custom sections and sectionslists.


|
|

.. container:: bsp-container-center

    .. image:: images/info_passive.png
        :width: 1000px
        :align: left

|

Fig. 5 – This cell contains all the information to place the passive properties, with specific parameters, on the morphological locations defined before. For example: the membrane capacitance on all sections, will have a name cm_all, a param name taken from the mod file, the value, the location and the fact that is not a range (frozen = True)

|
|

.. container:: bsp-container-center

    .. image:: images/ionic_mec.png
        :width: 1000px
        :align: left

|

Fig. 6 - The ionic mechanisms are loaded and inserted in the respective sections, defining which is each channel suffix, based on the information taken from the MOD files.


|
|

.. container:: bsp-container-center

    .. image:: images/channel_conduct.png
        :width: 1000px
        :align: left

|

Fig. 7 – Each channel is provided with a conductance range, location and name

|
|

.. container:: bsp-container-center

    .. image:: images/cell_all.png
        :width: 1000px
        :align: left

|

Fig. 8 – This is the cell in which we put together the morphology, the passive and active properties to generate the cell template.

|
|

.. container:: bsp-container-center

    .. image:: images/el_location.png
        :width: 1000px
        :align: left

|

Fig. 9 – Electrode location, used both to deliver the current and to record the voltage.

|
|

.. container:: bsp-container-center

    .. image:: images/stimuli.png
        :width: 1000px
        :align: left

|

Fig. 10 - Stimuli, recordings location and protocols. For each protocol can be defined a recording location and a stimulus, in this case, both are in the soma.

|

The default parameter are the conductances which were known to produce a working model. Here are present to compare the results of the optimization with a reference.

|
|

.. container:: bsp-container-center

    .. image:: images/features.png
        :width: 1000px
        :align: left

|

Fig. 11 – Features name and their parameter. They were obtained, with efel, from traces recorded, in vitro, from mice (Masoli et al., 2017).

|
|

.. container:: bsp-container-center

    .. image:: images/cell_eval.png
        :width: 1000px
        :align: left

|

Fig. 12 – The cell evaluator is in charge of putting together the model template and the parameter we want to search in the optimization.

|
|

.. container:: bsp-container-center

    .. image:: images/opt_gen.png
        :width: 1000px
        :align: left

|

Fig. 13 – The optimization requires and certain number of individual and generation. More individual, more combination will be tested.

|
|

.. container:: bsp-container-center

    .. image:: images/eval_best.png
        :width: 1000px
        :align: left

|

Fig. 14 – Evaluation of the best individual based on each simulation.

|
|

.. container:: bsp-container-center

    .. image:: images/plot_best.png
        :width: 1000px
        :align: left

|

Fig. 15 - Plot of the best individual and the min fitness obtained during the optimization
