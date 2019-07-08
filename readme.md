ijroieh
=======

Forked from the original ijroi code of Tim D. Smith and original implementation of
Louis Pedro Coelho.

The code has been updated to include ellipses and as well as returning the ROI
coodinate information in a numpy array it also returns the type of ROI, ie polygon,ellipse,
line,

.. code:: python

    >>> import ijroieh
    >>> with open("my_roi.roi", "rb") as f:
    ...     roi_type, roi = ijroieh.read_roi(f)
    ...
    >>> isinstance(roi, np.ndarray)
    True
    ...
    ...
    >>> isinstance(roi_type, str )
    True

The original code only returned the coordinate information as numpy array.

Finally, module can read in zipped roi files from imageJ an example is shown below

.. code:: python

    fn = r"RoiSet_square_circle_oval_rectangle_polygon.zip"
    rois = ijroieh.read_roi_zip(fn)

    for roi in rois:
        (roiName,roiShape,coords)=roi

Here the code has been modified to return also the name of each roi in the zipped file together with the type of ROI and the coordinates as a numpy array. This is useful in the context of analysis of MRI data where information about the different ROIs can be kept.

.. code:: python

    >>> import ijroieh
    >>> with open("my_roi.roi", "rb") as f:
    ...     roi = ijroieh.read_roi(f)
    ...
    >>> isinstance(roi, np.ndarray)
    True

read\_roi returns a Nx2 array, where each row is a (row, column) or (y,
x) pair.

Based on `Luis Pedro Coelho <https://github.com/luispedro>`__'s
`readroi.py gist <https://gist.github.com/luispedro/3437255>`__.

License
=======

ijroieh is offered under the MIT license.

