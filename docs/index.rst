`GoFish`
=========

``GoFish`` is a set of Python tools to exploit the known rotation of a protoplanetary disk to shift all emission to a common line center in order to stack them, increasing the signal-to-noise of the spectrum, detecting weaker lines, or super-sampling the spectrum to better resolve the line profile.

Background
^^^^^^^^^^

The method was first described in `Yen et al. (2016)`_, although other groups were using similar methods, such as `Teague et al. (2016)`_ and `Matra et al. (2017)`_ with varying applications. By exploiting the known rotation structure of the disk we can:

* Extract previously undetected line emission.

* Azimuthally average spectra to get a significant boost in the SNR.

* Super-sample the spectra to boost the spectral resolution of the data.

Details of the above examples can be found in the tutorials.

In `Teague et al. (2018a)`_ and `Teague et al. (2018b)`_, this method was inverted to use bright line emission to infer the rotation profile of the gas. You can use the functionality of ``GoFish`` with that of ``eddy`` (`Teague 2019`_) to perform similar analyses.

.. note::

    This documentation was written with a view to being used with ALMA data. However, this method works equally well with any PPV data obtained with any IFU instrument.

Installation
^^^^^^^^^^^^

Simply use PyPI with:

.. code-block:: bash

    pip install gofish

which should install the necessary dependencies. If you have any trouble installing, please `raise an issue`_.

If the installation went to plan you should be able to run the tutorial notebooks.

Fishing in *uv* Space
^^^^^^^^^^^^^^^^^^^^^

``GoFish`` works in the image plane, which allows the user flexibility in masking certain spatial regions. However, with this comes the complication of complex spatial correlations due to the highly non-linear imaging process.

We would strongly recommend using ``VISIBLE`` (`Loomis et al. 2017`_), which is a match-filtering approach to finding weak line emission. This has the significant advantage of not requiring any imaging as it works directly on the measurement sets and avoids any issues with correlated noise.

Citation
^^^^^^^^

If you use `GoFish` as part of your research, please cite the `JOSS article`_:

.. code-block:: tex

    @article{GoFish,
        doi = {10.21105/joss.01632},
        url = {https://doi.org/10.21105/joss.01632},
        year = {2019},
        month = {sep},
        publisher = {The Open Journal},
        volume = {4},
        number = {41},
        pages = {1632},
        author = {Richard Teague},
        title = {GoFish: Fishing for Line Observations in Protoplanetary Disks},
        journal = {The Journal of Open Source Software}
    }

as well as any of the above referenced papers for the method.

Community Guidelines
^^^^^^^^^^^^^^^^^^^^

`GoFish` is being actively developed on `GitHub`_. If you find any bugs, or want to suggest any improvements, please follow the `contributing guide`_ and open an issue.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   user/api
   user/fishing_coordinates
   user/fishing_basics
   user/fishing_advanced
   user/fishing_masking
   user/fishing_residuals

.. General operations for integrated spectra help

.. References ..
.. _contributing guide: https://github.com/richteague/gofish/blob/master/CONTRIBUTING.md
.. _GitHub link: https://github.com/richteague/eddy
.. _GitHub: https://github.com/richteague/gofish
.. _JOSS article: https://doi.org/10.21105/joss.01632
.. _Loomis et al. 2017: https://ui.adsabs.harvard.edu/abs/2018AJ....155..182L
.. _Matra et al. (2017): https://ui.adsabs.harvard.edu/abs/2017ApJ...842....9M
.. _raise an issue: https://github.com/richteague/gofish/issues
.. _Teague et al. (2016): https://ui.adsabs.harvard.edu/abs/2016A%26A...592A..49T
.. _Teague et al. (2018a): https://ui.adsabs.harvard.edu/abs/2018ApJ...860L..12T
.. _Teague et al. (2018b): https://ui.adsabs.harvard.edu/abs/2018ApJ...868..113T
.. _Teague 2019: https://ui.adsabs.harvard.edu/abs/2019JOSS....4.1220T
.. _tutorial notebooks: https://github.com/richteague/gofish/tree/master/docs/user
.. _Yen et al. (2016): https://ui.adsabs.harvard.edu/abs/2016ApJ...832..204Y
