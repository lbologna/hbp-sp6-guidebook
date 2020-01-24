==========================
Pair Recording application
==========================

Pair Recording application is a web environment for a small circuit
in-silico experiments.

It provides an extended toolset to configure and run simulations of single cell
models as well as multiple connected neurons from a given circuit.
The application's graphical user interface allows user to define in a first
step a small circuit composed of several connected neurons, and in a second
step to experiment on this circuit by defining a stimulation and reporting
protocol.

Usage
=====

The use case can be found in `Online Use Cases` under
`Small Circuit In Silico Experiments` menu in the `Brain Simulation Platform`.
A user can select a base circuit from the list to open Pair Recording
application.

.. image:: images/step_1.png
   :width: 800 px

Usage flow usually consists of:

#. selecting a small circuit of several connected neurons
#. configuring stimulation and reporting protocols
#. running simulation and inspecting its results

When the application has been started (on the initial load it will fetch
necessary circuit information, e.g. circuit info, cell locations and
properties, so this might take some time) an interactive circuit visualisation
will appear with controls facilitating cell selection.

.. image:: images/step_2.png
   :width: 800 px

Cells in the view are colour-coded by one of their's properties, user can
change this property with a `Color by` select on the bottom of the view.
Form to the right consists of various controls and allows user to filter and
select cells. Two types of filters are available: property and connectivity.

Property(display) filters can be used to show only cells with particular
properties (include subtype) or filter out a subset of particular cells based
on their properties. By default, multiple added filters use OR (union) logic to
compose a subset of affected cells, and when required,  user can switch this
mode to use AND (intersection) logic. This applies to both types of filters:
`include` and `exclude`. Connectivity filter can be used to show neurons with
afferent of efferent connections to a selected cell.

Cells can be selected for later simulations by clicking on them in the
interactive view or, if known beforehand, specifying their `gid`s in the form
and click the `Add` button.

.. image:: images/step_3.png
   :width: 800 px

When cell selection is done a user can proceed to simulation configuration by
clicking a corresponding button which will load and render morphologies for
selected cells.

.. image:: images/step_4.png
   :width: 800 px

A user can add stimulation and/or recordings by clicking on sections of
interest and choosing a type of instrument being added (stimulus, recording or
synaptic input - which is available only if clicking on soma). Each added
stimulus and synaptic input can be configured in the right panel.

Available types of stimuli are:

* step current
* ramp current
* pulse current (soma only)
* voltage clamp (soma only, will add current recording automatically)

Synaptic input will provide a cell with a presynaptic spike train of a
given frequency with Poisson distribution for synapses with selected
pre-synaptic cells (filtered by a given pre-synaptic cell property).

.. image:: images/step_5.png
   :width: 800 px

When stimuli and recordings are configured, a user can proceed to start
a simulation with given parameters. This can be done by clicking on the
`Run simulation` button at the top right of the panel. After a simulation
has been initialised, voltage and current recording graphs will appear
according to selected recordings, updating in real-time while a simulation is
running.

.. image:: images/step_6.png
   :width: 800 px

Artefacts of a simulation can be downloaded in CSV format by clicking on
corresponding button in the bottom right of a chart.
