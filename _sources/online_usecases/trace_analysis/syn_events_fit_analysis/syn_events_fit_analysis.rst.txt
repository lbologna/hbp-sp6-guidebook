.. _syn_events_fit_analysis:

################################
Synaptic events fitting analysis
################################

This Jupyter Notebook allows the user to analyse the optimized parameters.
The user may visualize:

1. The results table (sorted in ascending order by the fitting error).
                        
.. container:: bsp-container-center

     .. image:: images/results_table.png
         :width: 700px
         :align: center
              
|
|
 
2.	The boxplot of the normalized results.
   
.. container:: bsp-container-center

     .. image:: images/results_box.png
         :width: 700px
         :align: center
              
|
|
 
3.	The best fit.
 
.. container:: bsp-container-center

     .. image:: images/results_fit.png
         :width: 700px
         :align: center
   
|

The user may analyse the optimized parameters for a default data and mod file combination or browse through the optimized parameters available in the collab storage and visualize the table data, the box plot and the best fit. Once a collab storage folder is chosen, the user must select a corresponding experimental file (txt file), configuration file (txt file) and a result file (csv file).    

.. container:: bsp-container-center

     .. image:: images/choose_files.png
         :width: 700px
         :align: center
   
|

|


If you are interested in looking at the code, click on “Click here to toggle on/off the source code” button

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
