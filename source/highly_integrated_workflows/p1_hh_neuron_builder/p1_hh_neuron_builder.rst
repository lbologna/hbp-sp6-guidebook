.. _hh_neuron_builder:

############################# 
Hodgkin Huxley Neuron Builder
#############################

******** 
Overview 
********


The Hodgkin-Huxley Neuron Builder is a web-application that allows the user to
interactively go through the entire cell model building pipeline.  The workflow
consists of three steps: 1) electrophysiological feature extraction from voltage
traces; 2) model parameter optimization; 3) in silico experiments using the
optimized model cell.

The user is provided with a friendly interface enabling to  interact with both
the HBP collaboratory storage and the High Performance Computing (HPC)
resources. The application has been built in a flexible way so as to allow the
user to enter the workflow at any desired step, by either interacting with HBP
resources or uploading his own files.

The web-application homepage (see figure below) allow the user to initiate a new
workflow or select a workflow previously saved in the current collab storage.


|

.. container:: bsp-container-center

    .. image:: images/hhnb_home.png 
        :scale: 30% 
        :align: right

|

After initiating a new workflow, the user is provided with two panels allowing
to go through the processes of "Cell Optimization" and "Single Cell Simulation"
respectively. A third panel, the "Optimization settings", is provided for the
insertion of the optimization parameters (see figure below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_workflows.png
        :scale: 30%
        :align: right

|

*****************
Cell Optimization 
*****************

The cell optimization is made up of two main steps: i) the feature extraction
and ii) the choice of the single cell model to be optimized. An additional
panel, the "Optimization settings" one, is provided for the insertion of the
optimization parameters (see figure below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_opt_empty.png 
        :scale: 45% 
        :align: right

|

* Feature extraction is performed through the Feature Extraction GUI web
  application when clicking the "Extract features" button. This application
  interacts with and is integrated into the Hodgkin Huxley Neuron Builder
  framework (as shown in the figure below) and allows the user to extract
  features of interest from a dataset of electrophysiological traces provided by
  HBP or from data upload by the user himself. For a detailed explanation of the
  Feature Extraction GUI, please refer to the dedicated page of this guidebook
  (:ref:`efel_gui`). Alternatively, the user can upload his own
  **features.json** and **protocols.json** files through the "Upload files"
  button.

|

.. container:: bsp-container-center

    .. image:: images/hhnb_efelg_traces.png 
        :scale: 28% 
        :align: right

|

* The model to be optimized is chosen among a dataset displayed to the user
  after clicking the "Choose from database" button. The dataset is made up of
  `NEURON <https://www.neuron.yale.edu/>`_ based models previously optimized via
  a different set of electrophysiological features. When choosing the model, the
  user is provided with two images representing the reconstructed morphology of
  the neuron and an example of the simulated activity of the model (see figure
  below). Based on the neuron/activity properties the user chooses a model which will be
  optimized by using the features extracted/uploaded in the previous step. The
  model parameters will be optimized via the `BluePyOpt
  <https://github.com/BlueBrain/BluePyOpt>`_ tool via an optimization procedure
  based on genetic algorithm. For a complete reference to the BluePyOpt, please
  refer to the original article at this `link. <https://www.frontiersin.org/articles/10.3389/fninf.2016.00017/full>`_

|

.. container:: bsp-container-center

    .. image:: images/hhnb_opt_select.png 
        :scale: 29% 
        :align: right

|

* Before launching the optimization, the user must set the optimization
  parameters by clicking the "Set parameters/Choose HPC" button of the
  "Optimization settings" panel. A form is presented to the user (see image
  below), to be filled with: i) parameters concerning the genetic algorithm
  namely the maximum number of generation the user want
  to adopt as well as the number of offspring to be considered; ii) system
  parameters for the optimization run, namely the number of node and cores to be
  reserved on the hpc system and the maximum time the process is allowed to be
  running for; iii) the hpc system to be used.

|

.. container:: bsp-container-center

    .. image:: images/hhnb_hpc_param_select.png 
        :scale: 70% 
        :align: right

|

Once the feature files are present in the pipeline, the model chosen and the
parameters set, the "Launch optimization" button is activated and the
optimization can be launched (see figure below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_opt_ready.png 
        :scale: 45% 
        :align: right

|

Upon successfull submission, the flag icon is changed and the submission button disactivated so as to forbid a second
submission with the same workflow id (see figure below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_opt_launched_msg.png 
        :scale: 45% 
        :align: right

|

Both the feature and the optimization files can be removed from the pipeline
and/or downloaded by the user on the local machine through the "Delete" and "Download"
buttons respectively.


**************************
Single Cell Simulation Run 
**************************

After the optimization phase has successfully terminated, the optimized model can
be retrieved and used for simulations. This step is performed through the
"Single Cell Simulation Run" panel (see figure below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_sim_ready.png 
        :scale: 45% 
        :align: right

|


The user can fetch the results from the HPC system of choice through the "Fetch
results" button which allows to select the HPC system the optimization
files reside in and, successively, select the result file of interest (see
figures below).

|

.. container:: bsp-container-center

    .. image:: images/hhnb_fetch_param.png 
        :scale: 80% 
        :align: right

|
|
|

.. container:: bsp-container-center

    .. image:: images/hhnb_storage_fetch.png 
        :scale: 80% 
        :align: right

|



Alternatively, the user can upload a **.zip** package containing the files needed for the
simulation, through the upload button.

Once the model files are integrated into the pipeline, the simulation can be run
by clicking the "Run Simulation" button. The model is fed to the "Neuron As A Service"
web-application, integrated into the neuron builder (see figure below), which
allow the user to set visualize the morphology of the chosen model (both in 3D
and as a dendogram) and set the simulation run parameters.

For further details on the "Neuron As A Service" application, please refer to
the dedicated page of this guidebook (:ref:`single_cell_clamp`).

