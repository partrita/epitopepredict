Introduction
============

epitopepredict provides a standardized programmatic and command line interface for executing multiple MHC binding prediction methods.
The results from each method can then be processed and visualized in a consistent manner.

Installation
============

This software has been tested on Linux which is highly recommended. Windows is not supported. If you use windows you can simply install a linux virtual machine and run from there. You can then run the command line interface or use in python. Install on pip using::

    pip install epitopepredict

**Snap package**

You can install as a snap which will usually be the latest version and will include everything needed. This option is recommended for it's convenience. Snaps are ubuntu based but supported on most major linux distributions. Install snapd with your package manager and then run::

    sudo snap install epitopepredict

**Python dependencies**

* numpy
* pandas
* matplotlib
* biopython
* tornado
* bokeh
* wtforms

Prediction algorithms
---------------------

There are now multiple MHC binding prediction algorithms available freely online. Often the problem is determining how to use them and which alleles they support. The 'state of the art' algorithms are probably those based on neural networks such as netMHC class I and II routines. These are packaged in the IEDB suite of tools. These programs can be installed freely on your system. Some of the algorithms below are included in the snap package so you don't have to install them separately.

**Supported algorithms**

+---------------------+-------------------------------------------------------------+---------------+
| name                | description                                                 | snap package  |
+---------------------+-------------------------------------------------------------+---------------+
| tepitope            | implements the TEPITOPEPan method, built in                 | yes           |
+---------------------+-------------------------------------------------------------+---------------+
| netMHCIIpan         | http://www.cbs.dtu.dk/services/NetMHCIIpan/                 | no            |
+---------------------+-------------------------------------------------------------+---------------+
| IEDB MHC-I and II   | http://tools.immuneepitope.org/mhci/download/               | no            |
+---------------------+-------------------------------------------------------------+---------------+
| mhcflurry           | MHC-I predictor https://github.com/openvax/mhcflurry        | yes           |
+---------------------+-------------------------------------------------------------+---------------+
| mhcnuggets          | MHC-I predictor https://github.com/KarchinLab/mhcnuggets    | yes           |
+---------------------+-------------------------------------------------------------+---------------+

Installing IEDB MHC tools
-------------------------

The distributions 'IEDB_MHC*.tar.gz' contain a collection of peptide binding prediction tools for Major Histocompatibility Complex (MHC) class I and II molecules. The collection is a mixture of pythons scripts and linux 32-bit environment specific binaries. Linux environment is required. Under ubuntu (if not using the snap package) you should also install tcsh and gawk::

    sudo apt install tcsh gawk

Download from http://tools.iedb.org/mhci/download/. Unpack the tar.gz files. Run the 'configure' script to set up path variables for trained models. e.g. For MHC-I tools::
```
  $ tar -zxvf IEDB_MHC_I-*.*.*.tar.gz
  $ cd mhc_i
  $ ./configure.py
```

Submit Bugs
===========

This software is under active development particularly with a view to improve the command line tools. Please use the github project page to submit bugs or suggestions: http://dmnfarrell.github.io/epitopepredict

References
==========

* Zhang, L., Chen, Y., Wong, H.-S., Zhou, S., Mamitsuka, H., & Zhu, S. (2012). TEPITOPEpan: extending TEPITOPE for peptide binding prediction covering over 700 HLA-DR molecules. PloS One, 7(2), e30483. http://doi.org/10.1371/journal.pone.0030483

* Nielsen, M., Lund, O., Buus, S., & Lundegaard, C. (2010). MHC class II epitope predictive algorithms. Immunology, 130(3), 319–28. http://doi.org/10.1111/j.1365-2567.2010.03268.x

* Karosiene, E., Rasmussen, M., Blicher, T., Lund, O., Buus, S., & Nielsen, M. (2013). NetMHCIIpan-3.0, a common pan-specific MHC class II prediction method including all three human MHC class II isotypes, HLA-DR, HLA-DP and HLA-DQ. Immunogenetics, 65(10), 711–24. http://doi.org/10.1007/s00251-013-0720-y

* Chaves, F. a, Lee, A. H., Nayak, J. L., Richards, K. a, & Sant, A. J. (2012). The utility and limitations of current Web-available algorithms to predict peptides recognized by CD4 T cells in response to pathogen infection. Journal of Immunology (Baltimore, Md. : 1950), 188(9), 4235–48. http://doi.org/10.4049/jimmunol.1103640