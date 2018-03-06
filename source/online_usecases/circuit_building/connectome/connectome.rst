###################################
Cerebellum microcircuit: Connectome
###################################

Expert: Stefano Casali, Elisa Marenzi, Claudia Casellato
Target audience: (medium) Power Users 
Target interface: Notebook 

This use case can be used to connect cerebellar neurons. The potential connections are created by imposing geometric constraints (based on the anisotropic simplified geometric features of the pre- and post-synaptic neuron types). Then, if needed, a selection (pruning) is carried out by defining convergence or/and divergence ratios and applying them by distance-dependent probability.

The main input is the placement matrix (hdf5) generated into the usecase “Cell positioning”. 
By a simple GUI, the user can decide whether enabling the metrics computation Option.


The output of this usecase is the updating of the associated hdf5 file generated from “positioning” (saved in /storage). Indeed a new key “/connections” is added. It contains multiple items, one for each connection (13 types). Each of them is made up of a matrix with 2 columns (PRE Neuron ID and POST Neuron ID). 
For each connection type, effective convergence and divergence ratios and pairwise distances among connected neurons are computed and printed.
As an example, a 3D basic visualization about the connection from Glomeruli to Golgi cells is displayed. One PRE Neuron ID is selected, and all the POST neurons receiving its outward connections are plotted (Divergence). Also, one specific POST Neuron ID is selected, and all the PRE neurons sending connections to it are plotted (Convergence).

Moreover, an a-posteriori analysis of the generated hdf5 file can be done by using monitoring_probConn.py (in /storage), to quantify and display probability of connection dependent on inter-soma distance between connected neurons.
Steps:

•	Running all notebook steps one at a time 

•	Running each step in a sequential order

Additional information:

•	The whole usecase should take about 4 minutes for a volume base of 400 x 400 µm. If enabled, the computation of the metrics for each connection type adds about 15 minutes for such network size.

•	No login to any other computer required

Used BBP tools in notebook directly:

•	None
