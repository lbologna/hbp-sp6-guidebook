.. _morphology_analysis:

###################
Morphology Analysis
###################

The `Morphology Analysis <https://collab.humanbrainproject.eu/#/collab/1655/nav/66851>`_ Use Case allows analyzing neuronal morphology with `NeuroM <https://github.com/BlueBrain/NeuroM>`_.

`NeuroM <https://github.com/BlueBrain/NeuroM>`_ is a Python toolkit for the analysis and processing of neuron morphologies. It can be used to:

- quickly extract various morphometrics for one or a population of neurons. Examples of such metrics are the neurite length, the number of bifurcations per neurite or the number of segments. The list of all features can be found in the NeuroM documentation (`here <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.fst.get.html>`_ and `there <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.get.html>`_).
- `check <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.check.html>`_ the validity of morphology files (examples: no missing parent points, no excessively small neurite radii, no missing soma).
- visualize neuron morphologies with the module: `neuron.view <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.viewer.html>`_.
- iterate through morphology parts of a neuron for more advanced Use Cases. One can iterate on neurites, sections (neurite chunk between two successive branching points) or segments (the most fundamental sub-unit of a morphology).


Preview
=======

In this Use Case you will learn how to:

- Load a neuron morphology with NeuroM

- Create visualization plots such as:
     .. image:: images/example_neurom_draw.png
        :width: 400px

- Extract soma and neurite related statistics:
     .. image:: images/neurom_soma_statistics.png

     .. image:: images/neurom_neurite_statistics.png

- Create histograms for a particular feature:
     .. image:: images/neurom_feature_histogram.png


Instructions
============

Here are the steps to open this Use Case:

1. The Use Case can be found under `Online Use Cases/Morphology Analysis 
   <https://collab.humanbrainproject.eu/#/collab/1655/nav/66851>`_:

     .. image:: images/select_morphology_analysis.png
        :width: 700px

2. After you selection of the *Morphology Analysis* Use Case, you are asked to 
   select a single-cell model from the HBP database:

     .. image:: images/select_single_cell_model.png
        :width: 700px

3. Next, you should define a Collab in which you want to perform an analysis on 
   the morphology of the chosen single-cell model. You may choose to add the 
   morphology analysis to an existing Collab, or to create a new Collab (See 
   also :ref:`Working with Collabs <working-with-collabs>`):

     .. image:: images/create_collab.png
        :width: 700px

4. Once you have selected or created a Collab that you plan to work in, a 
   Jupyter notebook will open. This notebook contains all functionalities you 
   need to download the morphology you previously selected and to perform 
   analysis. We encourage you to read the documentation that precedes every 
   notebook cell.

     .. image:: images/morphology_analysis_notebook.png
        :width: 700px
