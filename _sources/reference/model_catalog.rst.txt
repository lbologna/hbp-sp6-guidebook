#################
Model Catalog app
#################

The HBP Model Catalog contains information about models developed and/or used within the ecosystem of tools
provided by the HBP platforms.

The Model Catalog app can be installed in any collab workspace, and can be used:

- to search for models of a given brain region, cell type, modelling scale, etc.
- to provide information/metadata about a model
- to register a model and obtain a unique identifier for use with other tools and workflows, such as model validation


Adding the app to your collab
-----------------------------

As shown in the screenshot below, click on the "ADD" button in the left-hand navigation bar,
then search for "model catalog", and click on "Add to Navigation" to install the app.

.. image:: images/model_catalog_add_to_navigation.png
   :width: 569
   :align: center

Choose which models to view
---------------------------

When you first click on "Model Catalog" in the navigation bar, you will see a configuration screen with a group of drop-down lists.
This allows you to filter the catalog, and show only the model(s) that is/are relevant to your collab.

.. image:: images/model_catalog_configure.png
   :width: 429
   :align: center

When you are finished, click "Save", and then click the "X" icon to close the configuration view.
This then shows a list of the models corresponding to the criteria you have selected.
These models can be further filtered dynamically using the drop-down lists at the top of the model list.

.. image:: images/model_catalog_hippocampus_models.png
   :width: 680
   :align: center

Viewing an individual model
---------------------------

Clicking on a single model in the list brings up a detailed view of that model,
including a potentially detailed description, metadata about the brain region, cell type, etc., being modelled,
and references to different versions of the model (which may be versions in a Git repository, ModelDB entries,
zip archives, etc.)

.. image:: images/model_catalog_model_detail_kali_freund.png
   :width: 538
   :align: center

Editing a model
---------------

For access-control purposes, each model is associated with a "home" collab.
If you are a member of that collab you can edit the model's details.

Note that the model description field accepts Markdown_ syntax for adding sub-headings, lists, italics, bold text,
hyperlinks, images, etc.

Models may also be marked as public or private.
Private models may only be viewed by people who are members of the model's home collab.

.. image:: images/model_catalog_model_edit_kali_freund.png
   :width: 519
   :align: center

Adding a model to the Catalog
-----------------------------

At the upper-left of the model list is a "New model" button,
which opens a form allowing any user to register a model with the Catalog.

The collab in which the model is first created is the "home" collab of the model,
and only members of that collab can subsequently edit the model.

When you create a model, it receives a unique ID, a long hexadecimal string
which is used to identify the model in some other tools and workflows in the HBP platforms.
To save having to type this long, difficult-to-remember, ID each time,
you can also create a short alias for the model.


.. image:: images/model_catalog_model_create.png
   :width: 531
   :align: center


.. _Markdown: https://daringfireball.net/projects/markdown/syntax