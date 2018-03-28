.. _efel_gui:

###########################################
Feature Extraction Graphical User Interface
###########################################

********
Overview
********

.. container:: bsp-container-left

    .. image:: images/spikesEfel.png
        :scale: 90%
        :align: right



The Feature Extraction Graphical User Interface (GUI) is a web application that
allows users to extract an ensemble of electrophysiological properties from
voltage traces recorded upon electrical stimulation of neuronal cells (see
figure on the left). The application main outcome is the generation of two files
- *features.json* and *protocol.json* - that the user will be able to use for
later model parameter optimizations.

With respect to the data selection, three scenarios are possible: 1) Based on
her/his data permissions (see :ref:`electrophys-data-label`), the user select
voltage traces from the Human Brain Project (HBP) database; 2) The user selects
the voltage traces from the data files she/he uploaded through the "Upload"
utility of the GUI; 3) The user select traces from both the HBP database and
her/his own uploaded file(s).

The application leverages the Python Electrophys Feature Extract Library (`eFEL
<http://bluebrain.github.io/eFEL/index.html>`_) and provides a friendly
interface to select voltage traces (individually or collectively, based on the
stimulus current applied) and features to be extracted.

.. _electrophys-data-label:

*************************
Electrophysiological data
*************************
The feature extraction exclusively applies to voltage traces recorded during a
step current stimulation protocol (see :ref:`feature-description-label`). The
HBP data available through the application for public use fulfill this
requirement and the user will only be allowed to upload data files of the same
type (see :ref:`hbp-data-label`). Below you will find a brief description of the
data formats currently in use.

.. _hbp-data-label:

============
HBP database
============
The data publicly available to the user consist in electrophysiological traces
provided by contributing laboratories internal and external to HBP (the
contributors are displayed to the user after data selection, see
:ref:`trace-selection-label`). Each data file is associated with a list of
"authorized collabs", following the indications of the contributors. An
"authorized collab" is a collab whose team members have read access to the data.
Regardless of the collab from which they are executing the Feature Extraction
web app, users who are members of, at least, one collab authorized for a set of
data, have read access to those data. Data for which the users have no
authorization will not be displayed.


Contributed raw data files are in the Axon Binary Format (`.abf
<https://mdc.custhelp.com/euf/assets/content/ABFHelp.pdf>`_) or the Igor Binary
Format (`.ibw <https://www.wavemetrics.com/index.html>`_) and each file is
accompanied by a *metadata.json* file in which the contributors describe cell
and protocol properties (e.g. *cell_id*, *brain_region*, *brain_structure*,
*stimulus_duration*, ...) used for data processing and visualization. The data
are read through the `neo <https://pypi.python.org/pypi/neo/>`_ and `igorpy
<https://pypi.python.org/pypi/igor.py/0.9.1>`_ python packages and converted
into value arrays before use. The *metadata.json* files relative to the selected
traces will be downloadable in a future release of the web app.

If you would like to contribute with your own data to the Feature Extraction GUI
application, please send an email to *bsp-support AT humanbrainproject.eu* to
receive further detailed information on the data format and the *metadata.json*
template to fill before data submission.


.. _user-data-label:

====================
User's uploaded data
====================
Users can also upload and visualize their own data, which can be selected, for
processing, independently or together with traces from the HBP dataset.

At the moment only the (`.abf
<https://mdc.custhelp.com/euf/assets/content/ABFHelp.pdf>`_) format (Version 2
and above), produced with `Molecular Devices
<http://mdc.custhelp.com/app/home>`_ instruments is supported for upload.
Additionally, to make sure that the recorded traces represent the outcome of a
step current stimulation experiment, the header of the file is checked for
compatibility. The upload is denied in case the file do not fulfill the
requirements.

Below we report an example of a permitted protocol header extracted from a
representative `.abf <https://mdc.custhelp.com/euf/assets/content/ABFHelp.pdf>`_
file with the `neo <https://pypi.python.org/pypi/neo/>`_ package. In this
example, the stimulus consisted of three periods of duration 500, 10000 and 500
respectively (the time unit is *ms*) and amplitude initially zero. During the
central period, though, the stimulus amplitude is increased by 10.0 at every
recording sweep, as indicated in the **lEpochLevelInc** parameter (current unit
is *nA*).

.. code-block:: json

     {"dictEpochInfoPerDAC": {"0": {"0": {  "fEpochInitLevel": 0.0,
                                            "fEpochLevelInc": 0.0,
                                            "lEpochDurationInc": 0,
                                            "lEpochInitDuration": 500,
                                            "lEpochPulsePeriod": 0,
                                            "lEpochPulseWidth": 0,
                                            "nDACNum": 0,
                                            "nEpochNum": 0,
                                            "nEpochType": 1,
                                         },
                                    "1": {  "fEpochInitLevel": 0.0,
                                            "fEpochLevelInc": 10.0,
                                            "lEpochDurationInc": 0,
                                            "lEpochInitDuration": 10000,
                                            "lEpochPulsePeriod": 0,
                                            "lEpochPulseWidth": 0,
                                            "nDACNum": 0,
                                            "nEpochNum": 1,
                                            "nEpochType": 1,
                                         },
                                    "2": {  "fEpochInitLevel": 0.0,
                                            "fEpochLevelInc": 0.0,
                                            "lEpochDurationInc": 0,
                                            "lEpochInitDuration": 500,
                                            "lEpochPulsePeriod": 0,
                                            "lEpochPulseWidth": 0,
                                            "nDACNum": 0,
                                            "nEpochNum": 2,
                                            "nEpochType": 1,

                                          }
                                    }
                                }
    }

.. _feature-description-label:

==================
Feature extraction
==================

The feature extraction process is preparatory to the generation of the
*features.json* and *protocol.json* files, which are used for model parameter
optimization performed through the `BluePyOpt
<https://github.com/BlueBrain/BluePyOpt>`_ software tool (please refer to the
BluePyOpt `documentation <http://bluepyopt.readthedocs.io/en/latest/>`_ for
detailed explanations).

The features the user can select for extraction are described at this `link
<http://bluebrain.github.io/eFEL/index.html>`_ as well as the eFEL software
package used to process the data. See also :ref:`Hippocampal Neurons <hippocampal-neurons>` in this guidebook.


Features are computed for every trace of the chosen recordings, where a trace
correponds to a given stimulus current amplitude (indicated to the user when
data are displayed).
Once the extraction finalized, the values of a feature obtained from traces
belonging to an individual cell and corresponding to the same stimulation
amplitude are averaged.
The averages computed for all the cells, are averaged a second time
by stimulus amplitude.
This will generate two result files (i.e. *features.json* and  *protocol.json*)
per cell plus two supplementary files with the global averages.

While the `eFEL <http://bluebrain.github.io/eFEL/index.html>`_ extracts the
features of interest from single traces (individually selected or grouped) it
does not take into account any information on the cell properties, such as the
*cell_id* needed to group the results for the generation of the above mentioned
*features.json* and *protocol.json*. To perform this wrapping we used a custom
python code (please contact `bsp-support AT humanbrainproject.eu` for further
information).


************************
Graphical User Interface
************************

The GUI guides the user through the feature extraction process in a friendly
way. The web application homepage shows a brief tutorial on the usage of the
interface. After the user has read (or skipped) the howto she/he is requested to
accept the Terms&Conditions for the use of the public data (see figure below).



.. container:: bsp-container-center

    .. image:: images/termsconds.png
        :width: 500px
        :align: right

|

In what follows we give a description of the feature extraction process.

.. _trace-selection-label:

===============
Trace selection
===============

Once entered in the trace selection page the user can filter the data from the
HBP dataset, by choosing, from five dropdown menu, the properties of the cell:
1) Species; 2) Brain structure; 3) Region; 4) Type; 5) Electrical type (`eType
<https://bbp.epfl.ch/nmc-portal/glossary>`_). If any of the field is
missing (e.g. the eType of the cell is not know), the "unknown" label is
displayed.

After the data are loaded, the traces contained in each file are showed and data
files are grouped by cell id (see figure below). The user can select individual
traces by clicking on the corresponding amplitude or she/he can select/deselect
all the traces in a single file. Additionally, all the files (and then all the
traces) referring to a single cell can be selected.

.. container:: bsp-container-center

    .. image:: images/traceselect.png
        :width: 500px
        :align: right

|

Alternatively, or concurrently, users can upload their own data (see
:ref:`user-data-label`) by browsing their local storage and using the upload
button (see figure below). The traces will be displayed for selection together
with the ones selected from the HBP dataset (if any).

.. container:: bsp-container-center

    .. image:: images/upload.png
        :width: 500px
        :align: right


=================
Feature selection
=================

Once the trace selection approved, the feature selection page is displayed.
Features are grouped by type -spike event features, spike shape features,
voltage features- and can be selected individually or collectively through the
select/deselect buttons. Given the high number of features, the three types are
grouped in toggle boxes (see figure below). Upon selection approval, the feature
extraction process takes place as described in
:ref:`feature-description-label`).


.. container:: bsp-container-center

    .. image:: images/featureselect.png
        :width: 500px
        :align: right


=======
Results
=======

Finally, a success message is displayed and results are made available to
download. The application output consists of a **features.json** and **protocols.json** files which are generated for both individual cells and the entire ensemble. These files contain the feature value averages (computed as outlined in the above section "Feature extraction") and the protocols adopted for the experimental recordings. These files are intended to be used for the data-driven optimization step of the Hodgkin-Huxley Neuron Builder workflow, made available to the user through the Brain Simulation Platform at the `Highly Integrated Workflows <https://collab.humanbrainproject.eu/#/collab/1655/nav/66898>`_ page.


.. container:: bsp-container-center

    .. image:: images/download.png
        :width: 500px
        :align: right
