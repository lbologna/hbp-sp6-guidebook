#################
Network Reduction
#################


This notebook is intended for applying a neuron reduction algorithm by Oren
Amsalem [:ref:`1 <net_red_1>`][:ref:`2 <net_red_2>`] to a neuronal circuit in 
SONATA [:ref:`3 <net_red_3>`] format.

Principle
---------
A complex neuron morphology is reduced to a simple one as described on the image
below. We have the leftmost original morphology that becomes the rightmost
reduced morphology. We apply this algorithm to all neurons with morphologies
in a given neuronal circuit.

      .. image:: images/principle.png

More examples of reduced morphologies:

      .. image:: images/examples.png

References
----------
.. _net_red_1:

    [1] https://doi.org/10.1038/s41467-019-13932-6

.. _net_red_2:

    [2] https://github.com/orena1/neuron_reduce

.. _net_red_3:

    [3] https://github.com/AllenInstitute/sonata
