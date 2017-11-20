.. _FS_single_cell_opt_guidebook:

#############################################
Optimise a striatial fast spiking interneuron
#############################################

This use case demonstrates how BluePyOpt can be used to optimised a striatal fast spiking interneuron. The notebook is self contained and runs the first steps of the genetic optimisation. For a production run, the population size as well as the number of iterations needs to be increased.

The notebook starts by downloading the relevant code from the collab storage. This step only needs to be done once. Since we are using neuron we also need to compile the channel mod files. If this step is skipped neuron will complain that the mechanism naf is not found.

The information about the optimisation to be run is stored in config/FS-info.json which refers to additional json files:

- FS-protocols.json
- FS-features-generated.json
- FS-mechanisms.json
- FS-parameters.json

For each set of parameters to be tested a neuron model is instantiated by the Neuron_evaluator. A series of current injections are sent to the neuron while the somatic voltage is recorded. From this voltage trace a number of features are extracted, and compared to the same features extracted from the corresponding experimental data.

**FS-protocols.json** lists the protocols and the stimuli that is associated with it. Each protocol also specifies a holding current. The delay, amplitude, duration and total duration is specified for each current injection.

**FS-features-generated.json** lists the features. Each protocol has their own set of features associated with it. For each feature the mean value and standard deviation (SD) is specified. The SD is used when weighting the feature scores together to get the final score for the model. Each feature also has a set of parameters which modifies it.

**FS-mechanisms.json** lists the mechanisms. Each ion channel has a corresponding mod file which is compiled by nrnivmodl.

**FS-parameters.json** lists all the parameters for the model. These can either be specified as a value, or as a range by giving the upper and lower bounds.
  

The main json file also points to the morphology of the neuron:

- morphology/FSi-E.CNG.swc.

To increase the population size and the number of generations for the genetic algorithm edit the following. Please note that this might increase runtime considerably. For production runs a super computer cluster is recommended.

opt.run(max_ngen=10,offspring_size=10,continue_cp=False,cp_filename='save/FS-notebook-run.pickle')

The post optimisation analysis is done by Neuron_analysis. It displays the top ten individuals that had the best scores and lists their parameters. It also displays the simulated protocols (blue) overlaid on the experimental data (red). The best candidate is displayed in dark blue, the others in light blue. The script also plots how the scores change with successive iterations of the genetic algorithm.


