.. _morphology_analysis:

###################
Morphology Analysis
###################

The *Morphology Analysis* use case provides capability to analyse a neuronal morphology with `NeuroM <https://github.com/BlueBrain/NeuroM>`_.

`NeuroM <https://github.com/BlueBrain/NeuroM>`_ is a Python toolkit for the analysis and processing of neuron morphologies. It can be used to:

- quickly extract various morphometrics for one or a population of neurons. Example of such metrics are the neurite length, number of bifurcation per neurite or the number of segments. The list of all features can be found in the NeuroM documentation (`here <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.fst.get.html>`_ and `there <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.get.html>`_).
- `check <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.check.html>`_ the validity of morphology files (examples: no missing parent points, no excessively small neurite radii, no missing soma).
- visualize neuron morphologies with the module: `neuron.view <http://neurom.readthedocs.io/en/stable/_neurom_build/neurom.viewer.html>`_.
- iterate through morphology parts of a neuron object for more advanced use cases. One can iterate on neurites, sections (neurite chunk between two successive branching points) or segments (the most fundamental sub-unit of a morphology).

Here are the steps to open this use case:

1. The use case can be found under *Online Use Cases/Morphology Analysis*:

     .. image:: images/select_morphology_analysis.png
        :width: 700px

2. After you have selected the *Morphology Analysis* use case, you are asked to select a single-cell model from the HBP database:

     .. image:: images/select_single_cell_model.png
        :width: 700px

3. Next, you should define a Collab in which you want to perform analysis on the morphology of the chosen single-cell model. You may choose to add the morphology analysis to an existing Collab, or create a new Collab:

     .. image:: images/create_collab.png
        :width: 700px

4. Once you have selected or created a Collab that you plan to work in, a Jupyter notebook will open. This notebook contains all functionality you need to download the morphology you previously selected and perform analysis. We encourage you to read the documentation that precedes every notebook cell.

     .. image:: images/morphology_analysis_notebook.png
        :width: 700px

