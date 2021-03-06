.. _intro:

Getting Started
===============

The main class of PyMeshLab is the :ref:`meshset` class. It represents the current state of MeshLab (containing a set of meshes, rasters...). See the documentation of the :ref:`meshset` class for more details.

After installing PyMeshLab through pip:

.. code-block:: python

   import pymeshlab as ml
   ms = ml.MeshSet()

You can load, save meshes and apply MeshLab filters:

.. code-block:: python

   ms.load_new_mesh('airplane.obj')
   ms.apply_filter('convex_hull')
   ms.save_current_mesh('convex_hull.ply')

You can list all the available filters and theirs parameters:

.. code-block:: python

   ms.print_filter_list()
   ms.print_filter_parameter_list('surface_reconstruction_screened_poisson')

And apply filters with your parameters:

.. code-block:: python

   ms.apply_filter('noisy_isosurface', resolution=128)

To run the tests:

.. code-block:: shell

   pip3 install pytest
   pytest --pyargs pymeshlab
