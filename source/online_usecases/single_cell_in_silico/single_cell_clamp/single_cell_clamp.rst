.. _single_cell_clamp:

#############################################################
Single cell in silico experiments under current/voltage clamp
#############################################################

*Single cell in silico experiments under current/voltage clamp* use case provides Web UI to access
**Neuron as a Service** in order to load the single cell models and run model simulations.

#. The use case can be found in the *Online Use Cases/Single Cell In Silico Experiments*:

     .. image:: images/single_cell_in_silico.png
        :width: 700px

#. When you arrive at the *Single cell in silico experiments under current/voltage clamp* use case
   you can select the single cell model from the HBP data:

     .. image:: images/single_cell_in_silico_select.png
        :width: 700px

#. As a result the single cell model will open in a new Browser window within the
   **Neuron as a Service** web application. The following screenshot of the app is annotated with
   red text to guide you through the interface:

     .. image:: images/neuron_as_a_service_ui.png
        :width: 700px

#. Cell morphology can be visualized either in 3D view or 2D Dendrogram view. It is possible to
   zoom/rotate/pan using your mouse/scroll wheel/trackpad.

#. Current clamp can be attached to any section by clicking the segment in the cell 3D/2D Dendrogram
   view and then pressing the *Place current injection* button. Or by selecting the section in the
   tree view on the right and pressing the same button.

#. In order to run the simulation switch to the **Simulation** tab. When in this view you can click
   and select the segments to record the voltage from. They are added to the corresponding list. Up to
   10 segments can be recorded from.

     .. image:: images/neuron_as_a_service_ui_sim.png
        :width: 700px

#. The graph showing the traces recorded from the cell segments can be zoomed in by clicking and dragging
   in order to select the area to zoom in. Double click on the graph will restore the original zoom level.

#. The recorded traces can be downloaded as csv file. The download link should become available at the
   bottom right corner of the graph after the simulation has finished.

   The following jupyter notebook code shows how it can be loaded with pandas for the further analysis:

    .. sourcecode:: python

        import pandas as pd
        %matplotlib inline
        df = pd.read_csv('sim_CA1_int_bAC_011023HP2_20170510120324_2017-06-21_14-36-10_amp-soma_0-0.7nA.csv')
        df.plot.line(x='time', y='soma[0]_0')

