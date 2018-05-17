.. _FS_single_cell_opt_guidebook:

#############################################
Optimise a striatial fast-spiking interneuron
#############################################

This use case demonstrates how BluePyOpt can be used to optimise a striatal fast-spiking interneuron. The notebook is self-contained and runs few steps of the genetic optimisation. For a production run, the population size as well as the number of iterations need to be increased as commented in the notebook.

The notebook starts by downloading the relevant code from the collab storage and setting up the simulation and graphical environment. Since we are using Neuron we also need to compile the channel mod files.

The information about the optimisation to be run is stored in `config/` directory:

- `protocols.json`
- `features.json`
- `mechanisms.json`
- `parameters.json` and `parameters-demo.json`

For each set of parameters to be tested a neuron model is instantiated by `evaluator`. A series of current injections are sent to the neuron while the somatic voltage is recorded. From this voltage trace a number of features are extracted, and compared to the same features extracted from the corresponding experimental data.

`protocols.json` lists the protocols and the stimuli that is associated with it. Each protocol also specifies a holding current. The delay, amplitude, duration and total duration is specified for each current injection.

`features.json` lists the features. Each protocol has their own set of features associated with it. For each feature the mean value and standard deviation (SD) is specified. The SD is used when weighting the feature scores together to get the final score for the model. Each feature also has a set of parameters which modifies it.

`mechanisms.json` lists the mechanisms. Each ion channel has a corresponding mod file which is compiled by nrnivmodl.

`parameters.json` lists all the parameters for the model. These can either be specified as a value, or as a range by giving the upper and lower bounds.
  

Morphology of the neuron is located in `morphology/` directory:

- `morphology/BE37A-rep-cor-reg15.swc`

.. container:: bsp-container-center

  .. image:: images/fs-morpho.png

Optimisation phase is followed by the post optimisation analysis within
the same notebook.  The script plots the evolution of the error scores
with successive iterations of the genetic algorithm (generations).

.. container:: bsp-container-center

  .. image:: images/log.png

It displays the top ten individuals that had the best scores and lists
the feature names.

.. container:: bsp-container-center

  .. image:: images/feature_scores.png

It also displays the simulated protocols (blue) overlaid on the
experimental data (grey) for the best individual.

.. container:: bsp-container-center

  .. image:: images/responses.png

Finally, errors for each feature of the best individual are shown and
also a mean error score is calculated. Typically the mean score is about
3 standard deviations.

.. container:: bsp-container-center

  .. image:: images/best_scores.png

It is possible to inspect any of the 10 candidate individuals as shown above
for the best individual. Corresponding instructions are given in the
notebook.
