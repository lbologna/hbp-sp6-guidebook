.. _syn_events_fit:

#######################
Synaptic events fitting
#######################

This use case allows a user to fit synaptic events using data and model from the Neuroinformatics Platform (NIP).

Selecting this use case, two Jupyter Notebooks are cloned in a private existing/new collab.
The cloned Notebooks are:

********************************
Synaptic events fitting - Config
********************************

It allows the user to:

1. Select, download and visualize experimental data from the Neuroinformatics Platform (NIP). The user may then select the data to fit

.. container:: bsp-container-center
    
     .. image:: images/data_selection.png
         :width: 700px
         :align: center
        
|

A configuration file corresponding to the experimental file chosen is downloaded from the collab storage. The file includes: the number of traces in the experimental file, the protocol (voltage clamp amplitude and reversal potential of the synapse), the name of the parameters to be fitted, their initial values and allowed range of variation, exclusion rules, and an optional set of dependencies for other parameters
 
|

2. Select a default or a local mod file

.. container:: bsp-container-center

    .. image:: images/mod_selection.png
        :width: 300px
        :align: center

|

Of course, we assume that the user knows what we are talking about here, and that the uploaded mod file has been already tested by the user in preliminary simulations. The program does not make any check, from this point of view. An invalid file will result in errors at NEURON compilation time

When a local mod file is chosen, a form with the values needed to write a corresponding configuration file is opened. The number of traces in the experimental file and the protocol (voltage clamp amplitude and reversal potential of the synapse) are by default filled with the values corresponding to the chosen experimental file. The name of the parameters to be fitted, their initial values and allowed range of variation, exclusion rules, and an optional set of dependencies for other parameters must be filled by the user. Typical values are shown in the figures below:

|

.. container:: bsp-container-center

    .. image:: images/local_mod.png
        :width: 300px
        :align: center
        
|

.. container:: bsp-container-center

    .. image:: images/local_mod_values.png
        :width: 300px
        :align: center
 
|       

.. container:: bsp-container-center

    .. image:: images/local_mod_values_params.png
        :width: 500px
        :align: center
        
|

   
All the other parameters that are not fitted have their default value as defined in the mod file.

|

3. Configure the parameters of the optimization job: number of nodes, number of cores and runtime. Run the fitting procedure using UNICORE authentication on JURECA or MARCONI, or on the NSG, and check the status of the job

On JURECA the number of nodes, number of CPUs per node and runtime are set by default to 2, 24 and 10m respectively
   
|
   
On MARCONI the number of nodes, number of CPUs per node and runtime are set by default to 2, 36 and 10m respectively
   
|
   
The user needs to be aware of the limitations imposed by each HPC system on resources

|
    
On the NSG the number of nodes, number of cores and runtime are set by default to 2, 24 and 0.5 (hours) respectively. The maximum number of nodes available per job is 72. If you require more than 72 nodes please contact nsghelp@sdsc.edu. The maximum number of cores required per node is 24

.. container:: bsp-container-center

    .. image:: images/hpc_selection.png
        :width: 300px
        :align: center
        
|

.. container:: bsp-container-center

    .. image:: images/run_all_traces.png
        :width: 150px
        :align: center
        
|
 
.. container:: bsp-container-center

 .. image:: images/set_cores_nodes.png
     :width: 300px
     :align: center
        
|
 
.. container:: bsp-container-center

 .. image:: images/login.png
     :width: 300px
     :align: center
        
|
 
.. container:: bsp-container-center

 .. image:: images/job_submitted.png
     :width: 300px
     :align: center
    
|

Note that when the job is submitted through UNICORE, the user can specify a title for the job and the account to use for submitting the job on the HPC.

|
 
.. container:: bsp-container-center

 .. image:: images/unicore.png
     :width: 300px
     :align: center
    
|

Note that when the job is submitted through NSG, next to the status of the job, the user may see the submission date converted to CET time. It will be useful in the analysis notebook in order to fetch the job.

|
 
.. container:: bsp-container-center

 .. image:: images/NSGstatus.png
     :width: 300px
     :align: center
    
|

The user can choose to fit all the experimental traces 100 times, a single trace 20 times or a demo version where a trace is fitted 5 times. For the single trace and the demo version the user can choose the number of the trace to be fitted.

|

Once the job is completed, the output files will be in the collab storage under different directories, according to the system used.

JURECA: results are saved under the results/output_submissionTime folder.

MARCONI: results are saved under the resultsMarconi/output_submissionTime folder.

NSG results are saved under the resultsNSG/output_submissionTime folder.

|


4. If you are interested in looking at the code, click on “Click here to toggle on/off the source code” button

.. container:: bsp-container-center

    .. image:: images/toggle_button.png
        :width: 300px
        :align: center
        
|

5. If you want to start a new fitting from the beginning, click on “Click here to to start a new fit” button.

.. container:: bsp-container-center

    .. image:: images/Restart.png
        :width: 600px
        :align: center
        
|

**********************************
Synaptic events fitting - Analysis
**********************************

.. include:: ../syn_events_fit_analysis/syn_events_fit_analysis.rst
