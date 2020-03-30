.. _scise_cxsys2:

=======================================================================================
Configure and run a simplified cortical circuit with the CxSystem2 simulation framework
=======================================================================================

CxSystem2 is a simulation framework for cortical networks which uses |brian2| 
as main simulation backend. Simulations can be run in native Python code, which is
most productive for development and small circuits. For longer and heavier simulations  
CxSystem2 supports automatic compilation to a c++ device. For very long single model 
simulations you can also use |genn| device which allows GPU-acceleration.

In the BSP we provide a user-friendly GUI to configure and run simplified 
cortical circuits, visualize and download the simulation results.
In order to run the tool in your own Collab, please go to the |sc_uc| Use Case list, 
click on the *Configure and run a simplified cortical circuit with the CxSystem2 simulation framework* 
panel and follow the instructions provided in the :ref:`working-with-collabs` section of this Guidebook. 

The CxSystem2 includes Neurodynlib, a set of jupyter notebooks, which allows the
exploration of single-neuron models behavior before incorporating them into a network. 
The jupyter notebooks are publicly available in this |jnotebooks| under the |jntutorial| item.

In order to learn how to use this Use Case, please refer to the following 
|cxsys2_tutorial|.

A complete documentation on CxSystem2 can be found |cxsys2_rtd|.

The CxSystem2 code is available on |cxsys2_code|.



.. |brian2| raw:: html  

    <a href="https://briansimulator.org/" target="_blank">Brian</a>

.. |genn| raw:: html  

    <a href="http://genn-team.github.io/genn/" target="_blank">GeNN</a>

.. |jnotebooks| raw:: html  

    <a href="https://collab.humanbrainproject.eu/#/collab/67332/nav/457373" target="_blank">collab</a>

.. |jntutorial| raw:: html  

    <a href="https://collab.humanbrainproject.eu/#/collab/67332/nav/457379" target="_blank">Tutorial</a>


.. |cxsys2_rtd| raw:: html  

    <a href="https://cxsystem2.readthedocs.io/en/latest/index.html" target="_blank">here</a>

.. |cxsys2_tutorial| raw:: html  

    <a href="https://cxsystem2.readthedocs.io/en/latest/tutorials.html" target="_blank">tutorial</a>

.. |cxsys2_code| raw:: html  

    <a href="https://github.com/VisualNeuroscience-UH/CxSystem2" target="_blank">github</a>

.. |sc_uc| raw:: html  

    <a href="https://collab.humanbrainproject.eu/#/collab/1655/nav/66855" target="_blank">Small Circuit In Silico Experiments</a>

