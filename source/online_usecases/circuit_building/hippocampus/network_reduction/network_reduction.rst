#################
Network Reduction
#################


This notebook is intended for applying a neuron reduction algorithm by Oren
Amsalem to a neuronal circuit in SONATA format.

Principle:
----------
A complex neuron morphology is reduced to a simple one as described on the image
below. We have the leftmost original morphology that becomes the rightmost
reduced morphology. We apply this algorithm to all neurons with morphologies
in a given neuronal circuit.

      .. image:: images/principle.png

More examples of reduced morphologies:

      .. image:: images/examples.png

References:
-----------
For details on the algorithm refer to https://doi.org/10.1038/s41467-019-13932-6
and https://github.com/orena1/neuron_reduce. For details on neuronal circuits
in SONATA format refer to https://github.com/AllenInstitute/sonata.
