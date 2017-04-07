.. _validation_framework:

#################################
HBP Validation Framework Platform
#################################

.. _vfp-overview:

********
Overview
********

At current stage of development of the `HVF platform <https://validation.brainsimulation.eu/>`_, the framework is accessible via client and it will be possible to access through an app in the future. Therefore, this quick-guide will demonstrate how a user can access from a client (python client or jupyter notebook). The jupyter notebook will be used to illustrate this. 

|

**Purpose**

A user visits the HVF platform (see figure below). The user then choses :ref:`a model <choosing-loading-model>` to validate and the :ref:`desired validation test <choosing-loading-test>`. After this the user :ref:`runs <running-validation-test>` the validation test. The data of the test result is :ref:`stored <storing-data-results>`. The result and the data location is :ref:`registered <registering-validation-test>` in the HVF database.

|

.. container:: bsp-container-center

    .. image:: images/vuc_home.png
                :width: 650px 
                :align: right

|

**Background**

Before diving into the steps, one necessary condition is to install the HVF platform. This is done as follows (see also video below) 

**!pip install https://github.com/apdavison/hbp-validation-client/archive/master.zip**

|

.. container:: bsp-container-center

    .. image:: images/installhbpvalidframework.gif
                :width: 650px 
                :align: right

|
|

.. _choosing-loading-model:

********************************************************
Choosing and loading a model from the HVF Model Catalog
********************************************************

|

**Purpose**

In the HVF, user checks out the model catalog containing the list of currently available models for validations. The user then picks a model (see video below). 

|

.. container:: bsp-container-center

    .. image:: images/HVF_Model.gif
                :width: 650px 
                :align: right

|

**Background**

The platform has metadata about the model. For example, the model CA_Bianchi a pyramidal cell model of hippocampus CA1 region. The model is versioned and is located in https://github.com/apdavison/hippocampus_CA1_pyramidal.

To proceed let's say our

    * **chosen model: CA1_Bianchi**
    * **model location: https://github.com/apdavison/hippocampus_CA1_pyramidal**

**How to.**

The user will need to load the CA1_Bianchi that he/she intends to validate. To load the model, it must be first cloned into a directory. In the jupyter notebook this is done with the command

**>> !git clone https://github.com/apdavison/hippocampus_CA1_pyramidal**

This will create a subdirectory. The user then goes into this directory and import the models.

This additional step is not essential to run the validation test. But if the user wants to confirm that the chosen CA1_Bianchi model is available in the module, this is done as follows (see also the video below):

**>> import inspect**

**>> [m[0] for m in inspect.getmembers(models, inspect.isclass) if m[1].__module__ == "models"]**

|

.. container:: bsp-container-center

    .. image:: images/loadModel.gif
                :width: 650px 
                :align: right

|
|

.. _choosing-loading-test:

**********************************************
Choosing and loading a desired Validation Test
**********************************************

**Purpose**

The user has chosen a model. From a list of validation tests, the user then chooses a validation test.

|

.. container:: bsp-container-center

    .. image:: images/HVF_Test.gif
                :width: 650px 
                :align: right

|

**Background**

The platform has metadata about what family of models the test is suitable for, the location of the experimental data against which the model will be validated and the repository location of the test.

A test definition in the HVF comprises:

     * **location of the coded test function**
     * **location of the experimental data**

Test definitions can be obtained through the test URI (preferably JSON form).

For the chosen CA1_Bianchi model let's say we have the following: 

    * **desired test: Depolarization Block test**
    * **location: https://github.com/apdavison/hippounit**


**How to.**


The chosen model is a hippocampus CA1 pyramidal cell model. Therefore based on the metadata we should be able to run our desired depolarization block test.

As with loading the model, the user loads the desired validation test. That is, load the test definition from the URI (JSON form). This is done as follows (see also the video below):

**>> desired_test_uri = "https://validation.brainsimulation.eu/tests/1"**

**>> from hbp_validation_framework import ValidationTestLibrary**

**>> test_library = ValidationTestLibrary(username="lungsi")**

**>> test = test_library.get_validation_test(desired_test_uri)**

|

.. container:: bsp-container-center

    .. image:: images/loadTest.gif
                :width: 650px 
                :align: right

|
|

.. _running-validation-test:

*******************************************************
Running the desired Validation Test on the chosen model
*******************************************************

|

**Purpose**

Run the desired validation test on the chosen model.

|

**How to.**

To run the following:

   * **desired validation test: Depolarization block test**
   * **chosen model: Bianchi CA1 pyramidal cell**

the command is typed as follows (see also the videos below):

**>> score = test.judge(getattr(models, 'Bianchi')(), deep_error=True)**

|

.. container:: bsp-container-center

    .. image:: images/runTest.gif
                :width: 650px 
                :align: right

|

.. container:: bsp-container-center

    .. image:: images/runTest2.gif
                :width: 650px 
                :align: right

|
|

.. _storing-data-results:

***********************************************
Storing the data of the Validation Test Results
***********************************************

|

**Purpose**

Store the data of the results after running the desired validation test on the chosen model. 

|

**How to.**

To store the results data of our test run on the collab storage do the following (see also the video below):

**>> from hbp_validation_framework.datastores import CollabDataStore**

**>> collab_storage = CollabDataStore(username="lungsi", collab_id="1655", base_folder="VUC_Bianchi_DepolTest_results")**

|

.. container:: bsp-container-center

    .. image:: images/storeResults.gif
                :width: 650px 
                :align: right

|

The above command stores the results files in the directory named VUC_Bianchi_DepolTest_results of BSP collab (1655 id) storage. This is shown in the video below. 

|

.. container:: bsp-container-center

    .. image:: images/storeResultsCollab.gif
                :width: 650px 
                :align: right

|
|

.. _registering-validation-test:

**************************************
Registering the Validation Test Result
**************************************

|

**Purpose**

Register the results data. 

|

**How to.**

It is recommended that the results data are registered. To register the data do (see also video below):

**>> test_library.register(score, collab_storage)**

|

.. container:: bsp-container-center

    .. image:: images/registerResults.gif
                :width: 650px 
                :align: right

|

Below we illustrate the result being registered in the test results database of the framework. 

|

.. container:: bsp-container-center

    .. image:: images/HVF_Results.gif
                :width: 650px 
                :align: right

|
|

.. _all-preceding-steps:

************************************
All the preceding steps in a script
************************************

|

**Purpose**

Run the desired validation on the chosen model from a script.

|

**How to.**

There are various ways of writing a script. Here is one version of a python script.

**import argparse**

**import inspect**

**import models**

**from hbp_validation_framework import ValidationTestLibrary**

**from hbp_validation_framework.datastores import CollabDataStore**

**#**

**# Parses command line arguments**

**parser = argparse.ArgumentParser("Process model to be validated against the URI of the v-test.")**

**parser.add_argument ( "--modelName", help="A model name from hippocampus_CA1_pyramidal", choices= [m[0] for m in inspect.getmembers(models, inspect.isclass) if m[1].__module__ == 'models'])**

**parser.add_argument("--testURI", help="local path to the v-test")**

**parser.add_argument("--userName", default="lungsi", help="Give a username (default: lungsi)") parser.add_argument("--collabID", default="1655", help="The number of the collab (default: 1655)")**

**parser.add_argument("--folderName", default="VUC_modelName_testName_results", help="Give the folder name (default: VUC_modelName_testName_results)")**

**args = parser.parse_args()**

**#**

**# Load the model**

**model = getattr(models, args.modelName)()**

**#**

**# Load the test**

**desired_test_uri = args.testURI test_library = ValidationTestLibrary(username = args.userName) test = test_library.get_validation_test(desired_test_uri, show_plot=True) score = test.judge(model, deep_error=True)**

**#**

**# Store the results**

**collab_storage = CollabDataStore(username = args.userName, collab_id = args.collabID, base_folder = args.folderName)**

If you are working from a terminal, to copy-paste the below code you first need to have a .py file (here runTests.py). One way to do this in jupyter notebook is

**>> %%writefile runTests.py -a**

|

.. container:: bsp-container-center

    .. image:: images/writeScript.gif
                :width: 650px 
                :align: right

|
 

To run this runTests.py script from the jupyter notebook you can use the help feature.

**>> %run runTests.py -h**

You can than run the depolarization block test on the chosen CA1_Bianchi model as shown below

**>> %run runTests.py --modelName Bianchi --testURI https://valiation.brainsimulation.eu/tests/1**

|

.. container:: bsp-container-center

    .. image:: images/runScript.gif
                :width: 650px 
                :align: right

|
