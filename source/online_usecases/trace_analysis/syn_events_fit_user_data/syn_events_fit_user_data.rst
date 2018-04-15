.. _syn_events_fit_user_data:

#####################################
Synaptic events fitting (user’s data)
#####################################

This use case allows a user to fit synaptic events data with model from NeuroInformatics Platform.

Selecting this use case, two Jupyter Notebooks are cloned in a private existing/new collab.
The cloned Notebooks are:

***********************************************
Synaptic events fitting with user data - Config
***********************************************

It allows the user to:

1. Select a local experimental file

.. container:: bsp-container-center

     .. image:: images/select_exp.png
         :width: 400px
         :align: center
        
|
 
At this time, the only accepted format for the experimental file is a text file with time in the first column and individual traces in successive columns. All columns must be of the same length.

|


2. Fill the form with the values needed to write a configuration file: the number of traces in the experimental file, the protocol (voltage clamp amplitude and reversal potential of the synapse). The name of the parameters to be fitted, their initial values and allowed range of variation, exclusion rules, and an optional set of dependencies for other parameters are by default those corresponding to the model from NeuroInformatics Platform

.. container:: bsp-container-center

    .. image:: images/fill_form.png
        :width: 400px
        :align: center
        
|
   
.. container:: bsp-container-center

    .. image:: images/fitting_params.png
        :width: 600px
        :align: center
        
|
   
.. container:: bsp-container-center

    .. image:: images/dependencies.png
        :width: 500px
        :align: center
        
|

3. Configure the parameters of the optimization job: number of nodes, number of cores and runtime. Run the fitting procedure on JURECA or on MARCONI using UNICORE authentication, or on the NSG and check the status of the job

On JURECA the number of nodes, number of CPUs per node and runtime are set by default to 2, 24 and 10m respectively
   
|
   
On MARCONI the number of nodes, number of CPUs per node and runtime are set by default to 2, 36 and 10m respectively
   
|
   
The user needs to be aware of the limitations imposed by each HPC system on resources
   
|
   
On the NSG the number of nodes, number of cores and runtime are set by default to 2, 24 and 0.5 respectively. The maximum number of nodes available per job is 72. If you require more than 72 nodes please contact nsghelp@sdsc.edu. The maximum number of cores required per node is 24. 
   
|

.. container:: bsp-container-center

    .. image:: images/select_hpc.png
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
  :width: 400px
  :align: center
        
|
 
.. container:: bsp-container-center

 .. image:: images/login.png
     :width: 400px
     :align: center
        
|
 
.. container:: bsp-container-center

 .. image:: images/job_submitted.png
  :width: 400px
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
   
|
   
JURECA: results are saved under the results/output_submissionTime folder;
   
|
   
MARCONI: results are saved under the resultsMarconi/output_submissionTime folder; 
   
|
   
NSG results are saved under the resultsNSG/output_submissionTime folder.

|


4. If you are interested in looking at the code, click on “Click here to toggle on/off the source code” button

.. container:: bsp-container-center

    .. image:: images/toggle_button.png
        :width: 300px
        :align: center
        
|

*************************************************
Synaptic events fitting with user data - Analysis
*************************************************

.. include:: ../syn_events_fit_analysis/syn_events_fit_analysis.rst
