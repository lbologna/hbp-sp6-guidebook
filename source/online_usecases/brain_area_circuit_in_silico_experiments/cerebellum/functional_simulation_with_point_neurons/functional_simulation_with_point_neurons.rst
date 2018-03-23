########################################
Functional Simulation with Point Neurons
########################################

Expert: Stefano Casali, Elisa Marenzi, Claudia Casellato
Target audience: (medium) Power Users 
Target interface: Notebook 

This use case can be used to test the functionality of the cerebellar microcircuit, into NEST environment. The network is built based on the positions and connections generated from the other two usecases “Cell positioning” and “Connectome”. Each neuron is created as a spiking neuron using IAF dynamics with conductance-based synapses, with parameters specific for each neuron type. The pairwise connections are created and tuned in a simplified way (weight positive/negative and delay). An input pattern is defined on glomeruli; the simulation runs, and then the spiking activity of all neurons (neuron ID and spike times) is recorded and stored. 

The main input are the placement and the connectome matrices converted into .dat files (loading from storage folders). Into the code, the spike generators are defined.

The output of this usecase are .gdf files (generated for each spike detector and for each computing core), containing all the spike times of the whole built network (local path on HPC). 
Finally, the usecase carries out a “spike analysis”, by compacting all the files into Spike Matrices (one matrix for each neuron type population; the user can select which cell type) and by quantifying and displaying frequency-related parameters (PSTH).
Steps:

•	Running all notebook steps one at a time 

•	Running each step in a sequential order

Additional information:

•	The whole usecase should take about 4.5 hours (with 8192 cores (512 nodes) on Juqueen) for a volume base of 200 x 200 µm, excluding queue-time and excluding the a-posteriori “spike analysis”. 

•	login to HPC resource by UNICORE

Used BBP tools in notebook directly:

•	pyNEST
