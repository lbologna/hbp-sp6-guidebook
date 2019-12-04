The ARDOCK service
==================

Scientific Purposes
-------------------

ArDock is a structural bioinformatics web server for the prediction and the visualization of 
potential interaction regions at protein surfaces. Many biological function rely on the 
formation of protein-protein complexes. The identification protein interaction region is 
therefore of critical interest for our understanding of biology. The service is accessible
through a web interface, both for submission and the reporting of results.


How it works ?
--------------
ArDock ranks the surface residues of a protein according to their tendency to form interfaces
in a set of predefined docking experiments between the query protein and a set of arbitrary
protein probes. The ArDock methodology is derived from large scale cross-docking studies where 
it was observed that randomly chosen proteins tend to dock in a non-random way at protein surfaces.
This method is implemented on a computational cluster, where docking calculations run in parallel
and results are aggregated and returned to the web client.


Inputs 
------
- A protein structure in `PDB format <http://www.rcsb.org>`_
- Tokens obtained in previous analysis can be given to the server to restore their results

Outputs
-------
- Interactive and 3D vizualisation of the results on the protein structure
- Interactive scoreboard of the protein residue scores
- Result files available for download in CSV and PDB formats

Targeted audience
-----------------
All scientists working in biology related areas where protein study is relevant with a focus on structural biologists and biochemists.

Additional resources
---------------------
* A `tutorial <https://ardock.ibcp.fr/tutorial>`_ was set up by the Ardock team
* Publications describing `methods <https://www.ncbi.nlm.nih.gov/pubmed/22559010>`_ and `implementations <https://www.ncbi.nlm.nih.gov/pubmed/29905873>`_
* The public database of protein structures is avaible at `the PDB web site <http://rcsb.org>`_
