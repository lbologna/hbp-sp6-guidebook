.. _rebuild_scm:

#################################################
Rebuild an existing single hippocampal cell model
#################################################

This use case allows a user to configure the BluePyOpt to re-run an optimization with his/her own choices for the parameters range. The current version allows to select models obtained in previous optimizations.

Selecting this use case, 3 Jupyter Notebooks are cloned in a private existing/new collab.  The cloned Notebooks are:

1. “BluePyOpt One” – it allows users to:

   1.1.	Visualize the electrophysiological features, for the chosen model, that will be used as a reference by the optimization process (“Features” tab); they cannot be changed

   .. container:: bsp-container-center

        .. image:: images/visualize_feat.png
            :width: 700px
            :align: right

   |

   1.2. Visualize and change parameters of an existing optimization (“Parameters” tab). The user can change the values and “Save new parameters”
    
   |
    
   1.3. Configure the BluePyOpt optimization algorithm, by defining the offspring size and the max number of generations; they are set by default to 10 and 2 respectively
    
   |
    
   1.4. “Create zip file” will generate the zip file needed to run the new optimization

   .. container:: bsp-container-center

        .. image:: images/visualize_params.png
            :width: 700px
            :align: right

   |
   
   1.5. Login to NSG (Neuroscience Gateway) by inserting your username and password and clicking on the “Login NSG” button

   .. container:: bsp-container-center

        .. image:: images/login.png
            :width: 400px
            :align: right

   |

   1.6. Configure the parameters of the optimization job: number of nodes, number of cores and runtime. They are set by default to 2, 10 and 0.5 respectively. The maximum number of nodes available per job is 72. If you require more than 72 nodes please contact nsghelp@sdsc.edu. The maximum number of cores required per node is 24
    
   |

   1.7. Run the optimization by clicking on the “Run NSG simulation”

   |

   1.8. The job has been submitted when you see
    
   .. container:: bsp-container-center

        .. image:: images/ job_submitted.png
            :width: 400px
            :align: right

   |

   You may check the job status by clicking on the “Check NSG simulation”. The status may be: QUEUE, COMMANDRENDERING, INPUTSTAGING, SUBMITTED, LOAD_RESULTS or COMPLETED;
   Once the job is COMPLETED, results are saved in the collab storage, under the BluePyOptOne/resultsNSG/username/foldername (foldername is the name of the old optimization, where date and time are changed with the current date and time)

   |

   1.9. If you are interested in looking at the code, click on “Click here to toggle on/off the source code” button
    
   .. container:: bsp-container-center

        .. image:: images/toggle_button.png
            :width: 300px
            :align: right
   

