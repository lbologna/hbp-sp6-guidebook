Cerebellum microcircuit: Cell positioning


Expert: Stefano Casali, Elisa Marenzi, Claudia Casellato
Target audience: (medium) Power Users 
Target interface: Notebook 

This usecase places cerebellar neurons (different types: specific simplified geometric features with anisotropic properties and specific density) into a layered-volume of the cerebellum

By a simple GUI, the user can define basic parameters: base sizes (x and z) of the cerebellar volume to be built (the thickness, i.e. y-coordinate, is layer-specific and fixed); Plot option enabling; Save option enabling.
The input parameters are imported from scaffold_params.py

The output of this usecase is an hdf5 file made up of a matrix with 5 columns (saved in /storage):
•	Neuron ID (unique)
•	Neuron type ID (from 1 to 7)
•	3D coordinates (soma center) of each neuron (x, y, and z, respectively)
Moreover, a 3D basic visualization is depicted (somas of each neuron, using a different color for each neuron type).

An a-posteriori analysis of the generated hdf5 file can be done by using monitoring_positioning.py (in /storage), to quantify and display sparseness in the sub-volume by computing distribution of pairwise distances for neuron type

Steps:
•	Running all notebook steps one at a time 
•	Running each step in a sequential order

Additional information:
•	The whole usecase should take about 10 minutes for a volume base of 400 x 400 µm. 
•	No login to any other computer required

Used BBP tools in notebook directly:
•	voxcellview
