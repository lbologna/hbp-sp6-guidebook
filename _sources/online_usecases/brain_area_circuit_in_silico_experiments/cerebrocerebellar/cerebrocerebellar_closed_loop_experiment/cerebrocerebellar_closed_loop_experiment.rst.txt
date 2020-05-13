############################################################################
Closed-loop modelling and validation of large scale cerebro-cerebellar loops
############################################################################


This Use Case shows a modeling effort of whole brain functionalities by 
leveraging the existing cerebellar models. We model and simulate the forward 
and inverse controller functions of the cerebrocortical-cerebellar loops in a 
closed-loop setting, emulating error-based learning and action prediction.

The cerebellum model, made of single-point neurons with non-linear dynamics, 
leverages the scaffold developed in Task 6.2.2 (see Use Cases on Cerebellum 
models) and is embedded with long-term synaptic plasticity rules for implicit 
learning.

The Use Case can be found in *Online Use Cases/Brain area circuit in silico experiments/Cerebro-Cerebellar loops/Cerebro-Cerebellar closed loop experiment*.



**Simulation description:**

The cerebellum models are split into two modules, one operating in feed-forward 
mode (receiving motor command, i.e. the efference copy, and generating a 
sensory error prediction) and the other operating in inverse mode (receiving 
the sensory information of the desired target and generating compensatory motor 
commands). The two modules are connected as depicted in the following figure:

     .. image:: images/NEST_loop.png
        :width: 800px 

The model is used to simulate a specific sensorimotor task in closed-loop. 
We emulate a pointing task perturbed by prismatic glasses. The cerebellar 
modules allow to achieve complementary processing able to predict a sensory 
discrepancy and compensatory motor commands. Therefore, the cerebellum works 
as a general-purpose massive predictive machine in whole-brain modular systems.


**Inputs:**

•	One hdf5 file (saved in /storage) containing network topology data, i.e. cell positions and connections.
•	One json file (/storage/scaffold_network_BSP_static.json) representing a network without plasticity, with fixed synaptic weights between the different neural populations.
•	One json file (/storage/scaffold_network_BSP.json) representing a network provided with distributed STDP plasticity mechanisms.



**Output:**

•	Monitoring: evolution of the error of the final position of the robot end-effector (i.e., the fingertip of the arm performing the pointing task) along the trials. The error remains stable when the static cerebellar model is used as a controller, while the error gradually decreases when a plastic cerebellar controller is used.


**Additional information:**

•	The user needs to run the notebooks in the following order:

1) Preparation of the environment
2) Calibration
3) Simulation

•	The whole Use Case should take about 1 hour for a volume base of 400 x 400 µm.
•	The BSP foundation software used in the notebook is pyNEST
