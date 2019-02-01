pygame_plot
===========

.. image:: https://img.shields.io/pypi/v/pygame_plot.svg
    :target: https://pypi.python.org/pypi/pygame_plot
    :alt: Latest PyPI version


Quick visualization of data using pygame with a matplotlib style

Usage
-----
To look at some random noise.

.. code-block:: python

    import numpy as np
    import pygame_plot

    data = np.random.rand(10, 10, 500, 500)
    pygame_plot.pcolor(data)


This will bring up a window showing a 500x500 grid of the array 'data' (data[0, 0, :, :]).

To navigate the data use the up/down keys to increase/decrease the zeroth index and the left/right keys to increase/decrease the first index.

The colour scaling will be set by the minimum and maximum values in the set of data initially displayed. This can also be set explicitly through the vmin/vmax arguments (as in matplotlib). Also, the cmap argument can set the colorscale using any valid matplotlib colourscale (https://matplotlib.org/examples/color/colormaps_reference.html).

.. code-block:: python

    pygame_plot.pcolor(data, vmin=0, vmax=1, cmap='Greys')


You can also choose which part of the array to display first by specifying the indices 'k' and 't'. This convention is based on the 4d array having three spatial dimensions and one time dimension (i.e. data(t,k,j,i)).

If you have a smaller grid of data to view you can increase the size of the displayed array by setting the 'scale' argument. Currently this can only be an integer.

.. code-block:: python

    data = np.random.rand(10, 10, 50, 50)
    pygame_plot.pcolor(data, vmin=0, vmax=1, cmap='Greys', k=5, t=1, scale=10)


Installation
------------
.. code-block:: bash

    $ pip install pygame_plot

Requirements
^^^^^^^^^^^^
This package requires pygame, matplotlib and numpy to work

Licence
-------
