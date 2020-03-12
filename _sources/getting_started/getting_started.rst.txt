.. _getting_started:

###############
Getting started
###############

The Brain Simulation Platform (BSP) is organized around several “Online Use Cases” and “Model Collabs”. From these Use Cases, you will be guided in a few clicks to specific practical ways to use the BSP and to be almost immediately productive.

Access to advanced functionalities may be subject to certain conditions. This is due to the early state of the Platform, and to the fact that it relies on limited resources, such as supercomputers.
Please see the table at the end of this section on the services the Brain Simulation Platform (BSP) provides to different user classes at this point in time.

First, a short overview is given on working with "Collabs" and on the organization of Use Cases:

.. _working-with-collabs:

********************
Working with Collabs
********************

The central scientific working place in the Brain Simulation Platform are the "Collabs" (from "Collaboration"). A Collab is an area in which one or more scientists can work on different/multiple tasks.
An user can create a new Collab, use an existing one, add Use Cases to this Collab, and invite colleagues from the scientific community to collaborate.

Usually, when an user chooses an Use Case to work on, the following screen is presented to let the user select an existing Collab or to create a new Collab:

.. image:: images/collab_select.png
    :scale: 90%
    :align: right



Here you can enter the name of an existing Collab; any matching Collab will be listed and can be selected. Alternatively, you can select 'Create new Collab' which will lead to the following screen:


.. image:: images/collab_new.png
    :scale: 90%
    :align: right

If you select a Collab in which the chosen Use Case is already present, a dialog will appear that asks if you want to replace the existing content or be redirected to the old Use Case.

.. image:: images/replace.png
    :scale: 90%
    :align: right


Creating a new Collab is easy:


1. Select an meaningful name for the Collab (example: "Henry CA1 Connectome").
2. Click on "Create" (you can choose if the Collab is visible to anyone (i.e. public), or private. You can change this later anytime).
3. The actual notebook or GUI of the Use Case you initially selected should open up.

|

A new Collab will open with your Use Case(s) and several options:

|

.. image:: images/collab_options.png
    :scale: 90%
    :align: right

|

Here, you have different possibilities to configure the Collab or to see some statistics:

**Overview**
  Will display recent activities in the Collab.

**Team**
  Here you can invite a colleague to collaborate

**Storage**
  Here you can see what data and files are in the Collab-storage. You can upload and download files to/from that storage space.

**Settings**
  Here you can change the privacy of the Collab and rename it, if required.


*********************
Use Case Organization
*********************

.. container:: bsp-container-left

    .. image:: images/bsp_scheme.png
        :scale: 60%
        :align: right


A schematic organization of the Use Case workflow is shown in the figure on the left. An important aspect of the workflow is that it is open to the entire neuroscience community. This means that it does not matter if you belong to an HBP partner Institution, an external Laboratory/Company, or if you are just a curious student, in all cases you can be invited to get a HBP account to have access to the Use Cases. The only restriction will be on the type of data you will able to work with, and the resources that you can use.

|

Start your own project with these simple typical steps:

1. Navigate the Use Cases list and select the most appropriate one, depending on your purposes; the system will show what is already available in some detail, based on your account accreditation
2. Upon selection of a Use Case, the Platform will guide you to create a new Collab (or to add the Use Case to one of your existing Collabs) - all code and HBP-generated experimental data and models needed to execute the Use Case will be copied there, in several cases you can also upload your own data and work with them
3. Use your own imagination, collaborate with your team, use available tools or create new ones to pursue your scientific goal
4. Once you are satisfied with the results, you can download them and/or make your work available to other users by releasing it into the HBP database; our support team can help you to create a new Use Case

|

What you can do with a Use Case depends on your background and expertise. The BSP follows a user-centric development, to enable users with different backgrounds and skill levels to exploit the Platform’s capabilities to pursue scientific goals.
Use Cases are constantly updated, to improve their functionalities and usability, and may require different types of resources. To help you decide if a specific Use Case is appropriate for your expertise, each one is marked with intuitive icons, indicating the expected user experience, the Use Case maturity, and the type of resources required. These icons are shown on the rightmost part of the Use Case buttons, as in the figure below:


.. container:: bsp-container-center

    .. image:: images/usecase_button.png
        :scale: 70%
        :align: right
        :class: bsp-center

|

===============
User experience
===============

.. container:: bsp-container-left

    .. image:: images/everybody_tag.png
        :scale: 70%

**End users:** Users that are interested in using the BSP infrastructure and facilities in the most user-friendly way, for relatively simple collaborative scientific projects using GUIs and public HPC resources, such as a Cloud Computing or the Neuroscience Gateway (NSG). These users are familiar with the electrophysiological mechanisms underlying a neuron’s behavior (ion channels, synaptic and firing properties, etc.) and understand how to run a simple simulation, but they have no experience in programming languages such as Python and/or the NEURON simulation environment.

.. container:: bsp-container-left

    .. image:: images/poweruser_tag.png
        :scale: 70%

**Power users:** Users that are interested in using the BSP infrastructure and facilities for collaborative projects using public resources (such as the NSG), or their own HPC grants for one of the supercomputer centers supporting HBP activities (JSC and CINECA). These users are able to design, implement, run, and analyze models and simulations using the NEURON simulation environment; they understand the information needed to implement and run a simulation of morphologically and biophysically accurate neurons, and they have a working knowledge of Python.

.. container:: bsp-container-left

    .. image:: images/experts_tag.png
        :scale: 70%

**Experts and co-design partners:** Users with a good knowledge of the inner working of Collabs/apps/webservices and/or a substantial expertise in implementing simulations of morphologically and biophysically accurate neurons and networks to model brain functions. These usesr contribute to the development of new Use Cases/models.

.. container:: bsp-container-left

    .. image:: images/developer_tag.png
        :scale: 70%

|

**Code developers:** Designers and early adopters of initial versions of Collabs/apps/webservices/models. These users are top experts in their respective ICT and/or neuroscience field. Use Cases with this icon are usually restricted to Collabs with a team composed of mostly HBP partners, they serve the purpose of developing/testing advanced topics.

|

=================
Use Case maturity
=================

.. container:: bsp-container-left

    .. image:: images/beta_tag.png
        :scale: 50%

|

.. container:: bsp-inline-text

    A service of this maturity level has reached a certain robustness and may be used by early adopters.

.. container:: bsp-container-left

    .. image:: images/experimental_tag.png
        :scale: 50%

|

.. container:: bsp-inline-text

    A service of this maturity level is under heavy development and recommended only for specialists’ use or use for co-design partners.

|

==========
HPC access
==========

.. container:: bsp-container-left

    .. image:: images/hpc_tag.png
        :scale: 50%

.. container:: bsp-inline-text

    Use cases with this icon require a small to medium amount of High-Performance Computing resources. They can be either public, such as those available through the NSG, or provided by the user through a personal grant, such as a PRACE award, on one of the supercomputer centers supporting HBP activities (JSC and CINECA).

.. container:: bsp-container-left

    .. image:: images/byo_tag.png
        :scale: 50%

.. container:: bsp-inline-text

    This type of use cases needs large HPC resources. Typically, use cases showing this icon involve complex simulations of large scale cellular level model of brain areas/regions, that are deployed on JSC and CINECA systems. Subjected to technical compatibility and license agreement, this type of simulations can be delegated to be executed on other HPC systems, outside the BSP.



===============
Video Tutorials
===============

.. container:: bsp-container-left

    .. image:: images/interactive_tutorial.png
        :scale: 20%

|

.. container:: bsp-inline-text

    Use Cases with this icon provide a video tutorial that illustrates how to complete the entire Use Case. 
    The video tutorials allow the user to simulate the entire Use Case execution by clicking *ad-hoc* buttons. 
    They are intended to be used in a point-and-click interactive way, so please do not make use of the video progress bar while playing the videos so as not to disrupt the execution flow.

    There are currently 15 video tutorials available on the BSP. We group them by Use Case topic in the list below. 
    Please click the "Play" button if you want to execute a video tutorial or the "Download" button to download it locally (after downloading a video .zip file, unzip it and double click on the "index.html" file in order to play the video tutorial in your browser).

|

**Trace Analysis**

- Feature extraction (|ta_fe_video_link| - |ta_fe_zip_link|)

.. |ta_fe_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/FeatureExtraction/index.html" target="_blank">Play</a>

.. |ta_fe_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/FeatureExtraction.zip" target="_blank">Download</a>


- Synaptic events fitting (|ta_sef_video_link| - |ta_sef_zip_link|)

.. |ta_sef_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/SynapticEventsFitting/index.html" target="_blank">Play</a>

.. |ta_sef_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/SynapticEventsFitting.zip" target="_blank">Download</a>


- Synaptic events fitting with user model (|ta_sefum_video_link| - |ta_sefum_zip_link|)

.. |ta_sefum_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/SynapticEventsFittingWithUserModel/index.html" target="_blank">Play</a>

.. |ta_sefum_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/SynapticEventsFittingWithUserModel.zip" target="_blank">Download</a>


- Synaptic events fitting with user data (|ta_sefud_video_link| - |ta_sefud_zip_link|)

.. |ta_sefud_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/SynapticEventsFittingWithUserData/index.html" target="_blank">Play</a>

.. |ta_sefud_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/SynapticEventsFittingWithUserData.zip" target="_blank">Download</a>

|

**Morphology Analysis**

- Morphology analysis (|ma_ma_video_link| - |ma_ma_zip_link|)

.. |ma_ma_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/MorphologyAnalysis/index.html" target="_blank">Play</a>

.. |ma_ma_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/MorphologyAnalysis.zip" target="_blank">Download</a>
    

- Morphology visualization (|ma_mv_video_link| - |ma_mv_zip_link|)

.. |ma_mv_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/MorphologyVisualization/index.html" target="_blank">Play</a>

.. |ma_mv_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/MorphologyVisualization.zip" target="_blank">Download</a>

|

**Single Cell Building**

- Hodgkin-Huxley Neuron Builder (|scb_hhnb_video_link| - |scb_hhnb_zip_link|)

.. |scb_hhnb_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/HodgkinHuxleyNeuronBuilder/index.html" target="_blank">Play</a>

.. |scb_hhnb_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/HodgkinHuxleyNeuronBuilder.zip" target="_blank">Download</a>


- Rebuild an existing single hippocampal cell model (|scb_rem_video_link| - |scb_rem_zip_link|)

.. |scb_rem_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/RebuildAnExistingSingleHippocampalCellModel/index.html" target="_blank">Play</a>

.. |scb_rem_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/RebuildAnExistingSingleHippocampalCellModel.zip" target="_blank">Download</a>


- Build your own single hippocampal cell model using HBP data (|scb_byo_video_link| - |scb_byo_zip_link|)

.. |scb_byo_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/BuildYourOwnSingleHippocampalCellModel/index.html" target="_blank">Play</a>

.. |scb_byo_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/BuildYourOwnSingleHippocampalCellModel.zip" target="_blank">Download</a>


- Mono compartmental Cerebellar Granule cell optimization (|scb_mocc_video_link| - |scb_mocc_zip_link|)

.. |scb_mocc_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/MonoCompartmentalCerebellarGranuleCellOptimization/index.html" target="_blank">Play</a>

.. |scb_mocc_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/MonoCompartmentalCerebellarGranuleCellOptimization.zip" target="_blank">Download</a>


- Multi compartmental Cerebellar Granule cell optimization (|scb_mucc_video_link| - |scb_mucc_zip_link|)

.. |scb_mucc_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/MultiCompartmentalCerebellarGranuleCellOptimization/index.html" target="_blank">Play</a>

.. |scb_mucc_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/MultiCompartmentalCerebellarGranuleCellOptimization.zip" target="_blank">Download</a>


- Custom Axon Cerebellar Granule cell simulation (|scb_cac_video_link| - |scb_cac_zip_link|)

.. |scb_cac_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/CustomAxonCerebellarGranuleCellOptimization/index.html" target="_blank">Play</a>

.. |scb_cac_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/CustomAxonCerebellarGranuleCellOptimization.zip" target="_blank">Download</a>


- Simulation and validation of a mouse Purkinje cell multicompartmental model (|scb_svp_video_link| - |scb_svp_zip_link|)

.. |scb_svp_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/SimulationAndValidationOfAMousePurkinjeCellMulticompartmentalModel/index.html" target="_blank">Play</a>

.. |scb_svp_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/SimulationAndValidationOfAMousePurkinjeCellMulticompartmentalModel.zip" target="_blank">Download</a>


- Optimize a striatal fast-spiking interneuron (|scb_osfs_video_link| - |scb_osfs_zip_link|)

.. |scb_osfs_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/OptimiseAStriatalFastSpikingInterneuron/index.html" target="_blank">Play</a>

.. |scb_osfs_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/OptimiseAStriatalFastSpikingInterneuron.zip" target="_blank">Download</a>

|

**Single Cell In Silico Experiments**

- Single cell in silico experiments under current clamp (|sce_sce_video_link| - |sce_sce_zip_link|)

.. |sce_sce_video_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/SingleCellInSilicoExperimentsUnderCurrentClamp/index.html" target="_blank">Play</a>

.. |sce_sce_zip_link| raw:: html  

    <a href="https://object.cscs.ch:443/v1/AUTH_c0a333ecf7c045809321ce9d9ecdfdea/web-resources-bsp/bsp-video-tutorials/zip/SingleCellInSilicoExperimentsUnderCurrentClamp.zip" target="_blank">Download</a>

|

.. _service_account:

===============
Service Account
===============

The Service Account is a REST API service allowing developers to submit jobs,
on behalf of HBP Collaboratory users, to remote HPC systems.

For a thourough explanation on how to use the service, please refer to the
|sa_doc_link|

.. |sa_doc_link| raw:: html  

    <a href="https://humanbrainproject.github.io/hbp-bsp-service-account/" target="_blank">BSP Service Account documentation</a>.



.. _nsg:

==========================
Neuroscience Gateway (NSG)
==========================

The Neuroscience Gateway (NSG) portal https://www.nsgportal.org/ facilitates access and use of National Science Foundation (NSF) High Performance Computing (HPC) resources by neuroscientists. Computational modeling of cells and networks has become an essential part of neuroscience research, and researchers are using models to address problems of ever increasing complexity, e.g. large-scale network models and optimization or exploration of high dimensional parameter spaces. The NSG catalyzes such research by lowering or eliminating the administrative and technical barriers that currently make it difficult for researchers to use HPC resources. It offers free computer time to neuroscientists acquired via the supercomputer time allocation process managed by the Extreme Science and Engineering Discovery Environment (XSEDE) Resource Allocation Committee (XRAC). The portal provides access to the popular computational neuroscience tools installed on various HPC resources. It also provides a community mailing list for neuroscientists to collaborate and share ideas.

The NSG is accessible through a simple web portal, or programmatically using RESTful services. The NSG provides an administratively and technologically streamlined environment for uploading models, specifying HPC job parameters, querying running job status, receiving job completion notices, and storing and retrieving output data. The NSG transparently distributes user jobs to appropriate XSEDE HPC resources.

For Use Cases referring to hippocampal cells, the NSG will be accessed programmatically using RESTful services.

Successful job submission returns a message at each major processing point, as well as when problems are encountered. Each message has a timestamp, processing stage, and textual description. A job progresses through the following stages:

-	QUEUE - The job has been validated and placed in NSG's queue.
-	COMMANDRENDERING - The job has reached the head of the queue and NSG has created the command line that will be run.
-	INPUTSTAGING - The NSG has created a temporary working directory for the job on the execution host and copied the input files over.
-	SUBMITTED - The job has been submited to the scheduler on the execution host.
-	LOAD_RESULTS - The job has finished running on the execution host and NSG has begun to transfer the results.
-	COMPLETED - Results have successfully been transferred and are available.


S Sivagnanam, A Majumdar, K Yoshimoto, V Astakhov, A Bandrowski, M. E. Martone, and N. T. Carnevale. "Introducing the Neuroscience Gateway", IWSG, volume 993 of CEUR Workshop Proceedings, CEUR-WS.org, 2013.


*********************
Service Accessibility
*********************


.. list-table::
    :header-rows: 1

    * - Class
      - Who?
      - What?
      - Terms
      - Support
    * - ANONYMOUS
      - anyone
      - * Download open source software from GitHub accounts of SP6 partners
      - * license terms of respective software
      - * support through channels indicated with the respective software
        * community support through HBP Forum
    * - HBP IDENTITY
      - anyone with an HBP Identity Account
      - * Browse BSP Use Case Collabs
        * Browse BSP model Collabs
        * Can be added to private Collabs by Collab owners
        * Restricted access to apps: limited functionality or limited access
      - * license terms of respective software
        * HBP Collaboratory or Platform Terms of Service for accessible services
      - * Best effort support
        * send inquiries to bsp-support@humanbrainproject.eu
    * - PROJECT ACCESS
      - anyone who belongs to an HBP Partnering Project (or similar agreement)
      - * All rights of HBP Identity class
        * Access to the online functionality of the Brain Simulation Platform if requested in the Partnering Project agreement
        * Access to HBP models in the Brain Simulation Platform if requested in the Partnering Project agreement
        * HPC resources (*)
      - * license terms of respective software
        * HBP Collaboratory or Platform Terms of Service for accessible services
        * Terms of the Partnering Project agreement (or similar agreement)
      - * Full support according to terms of Partnering Project agreement
        * send inquiries and support requests to bsp-support@humanbrainproject.eu
    * - HBP MEMBERS
      - Anyone who belongs to an HBP partner institution and is granted accreditation to a particular HBP Subproject
      - * All rights of HBP Identity class
        * Access to the online functionality of the Brain Simulation Platform
        * Access to HBP models in the Brain Simulation Platform
        * HPC resources (*)
      - * HBP Consortium Agreement
      - * Full support
        * send inquiries and support requests to bsp-support@humanbrainproject.eu

|

(*) Note that access to HPC resources is subject to independent peer review by the HPC Platform. During the partnering project accession process, application to required resources will be coordinated. More information on HPC accounts and allocations can be found on the `HPC Platform <https://collab.humanbrainproject.eu/#/collab/264/nav/3304>`_. For an overview of accessibility of services from other platforms, please look `here <https://collab.humanbrainproject.eu/#/collab/19/nav/6601>`_.
