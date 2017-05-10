.. _syn_events_fit:

#################################################
Synaptic events fitting
#################################################

This use case allows a user to fit synaptic events using data and model from the Neuroinformatics Platform (NIP).

Selecting this use case, one Jupyter Notebook is cloned in a private existing/new collab.  By launching the notebook (Run All from the “Cell” menu), a simple graphical interface will guide the user to:

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

   Once the job is completed, the output files will be in the collab storage under different directories, according to the system used.

   JURECA: results are saved under the results/output_submissionTime folder.

   MARCONI: results are saved under the resultsMarconi/output_submissionTime folder.

   NSG results are saved under the resultsNSG/output_submissionTime folder.

   |

4. Analyse the optimized parameters. The user may visualize:

   4.1. The results table (sorted in ascending order by the fitting error)
                        
   .. container:: bsp-container-center

    .. image:: images/results_table.png
     :width: 700px
     :align: center
              
   |
   |
 
   4.2.	The boxplot of the normalized results
   
   .. container:: bsp-container-center

    .. image:: images/results_box.png
     :width: 700px
     :align: center
              
   |
   |
 
   4.3.	The best fit
 
   .. container:: bsp-container-center

    .. image:: images/results_plot.png
        :width: 700px
        :align: center
        
|


5. If you are interested in looking at the code, click on “Click here to toggle on/off the source code” button

   .. container:: bsp-container-center

       .. image:: images/toggle_button.png
           :width: 300px
           :align: center
        
   |


Warnings
    •	Each notebook cell has two square bracket on the left. 
    
        1.	When are empty, it means that the code was never run before

        2.	When there is an asterisk [*], it means that the code is running
        
        3.	When there is a number, it means that the code was run. A progressive numbering scheme define the order in which the cells were run
        
    •	Each time a notebook is executed, a kernel status symbol is displayed in the top right corner of the notebook
    
        1.	When there is a circle bullet •, it means that the kernel is running and the user have to be sure to not interfere with the code execution
        
        2. When there is an empty circle bullet ○, it means that the kernel is idle and the user can interfere with the notebook
        
        
    
