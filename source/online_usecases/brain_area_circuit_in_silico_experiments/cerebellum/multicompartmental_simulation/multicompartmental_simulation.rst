###############################################
Multicompartmental simulation of the cerebellum
###############################################


This use case creates a scaffold model of a piece of 150 by 150 micrometer of 
cerebellar cortex. Inputs arrive through the afferent mossy fibers onto the 
glomeruli which excite the granule cells.

The simulation includes Multicompartmental models of the granule cell, 
Golgi cell, Purkinje cell, stellate cell and basket cell.

The use case walks you through the creation of a network architecture, 
an HDF5 file with the positions of neurons and connections between them. 
Some plots are provided to inspect the generated network architecture.

This network architecture can be used to run simulations and the use case 
provides a small interface to set the input stimulus.

After simulation the results can be plotted in a raster plot and the membrane 
potential of one of each cell type's neurons can be viewed.

The use case itself contains step by step explanations and code cells that 
guide you through the network construction, simulation and analysis.

Inputs
------

- A configuration file that describes the network architecture and simulation components.
- A morphology repository containing descriptions of the cell models.

After running the code cell under the ``Configuring the input`` section the 
user can specify the start, number and interval for the mossy fiber input onto 
the glomeruli.


Outputs
-------

- A result HDF5 file containing the spike times and some membrane potential recordings.
- Plots: a spike raster plot, membrane potential plot and a boxplot that shows the
  average firing rate of the cell populations during the input stimulus.
