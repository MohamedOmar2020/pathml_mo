<img src=https://raw.githubusercontent.com/Dana-Farber-AIOS/pathml/master/docs/source/_static/images/logo.png width="300"> 

<img src=https://raw.githubusercontent.com/Dana-Farber-AIOS/pathml/master/docs/source/_static/images/overview.png width="750"> 

A toolkit for computational pathology and machine learning.

![tests](https://github.com/Dana-Farber-AIOS/pathml/actions/workflows/tests-conda.yml/badge.svg)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

* [Installing](#installing)
   * [Requirements](#requirements)
   * [Installation](#installation)
   * [Generate Documentation](#generate-documentation)
   * [Tests and Code Coverage](#tests-and-code-coverage)
* [Getting Started](#getting-started)
* [Contributing](#contributing)
* [Contact](#contact)

# Installing

*Note: these instructions are for Linux. Commands may be different for other platforms.*

0. Requirements
    * Set up Conda environment
        * Download Miniconda [here](https://docs.conda.io/en/latest/miniconda.html)
        * Create conda environment
            ````
            conda create --name pathml python=3.8 numpy=1.8.15
            conda activate pathml
            ````
    * Install external dependencies
        ````
        sudo apt-get install openslide-tools g++ gcc libblas-dev liblapack-dev
        ````
    * Install conda dependencies [OpenJDK](https://openjdk.java.net/)
        ````
        conda install openjdk==8.0.152
        ````
    * [Optional]: Install CUDA. This step only applies if you want to use GPU acceleration for model training or other tasks. This guide should work, but for the most up-to-date instructions, refer to the [official PyTorch installation instructions](https://pytorch.org/get-started/locally/).
        - Check the version of CUDA:
            ````
            nvidia-smi
            ````
        - Install correct version of `cudatoolkit`:
            ````
            # update this command with your CUDA version number
            conda install cudatoolkit=11.0
            ````
    
1. Install PathML:
    ````
    pip install pathml
    ```` 

2. Optionally verify PyTorch installation with GPU support: 
   ````
   python -c "import torch; print(torch.cuda.is_available())"
   ````


## Generate Documentation

This repo is not yet open to the public. Once we open source it, we will host documentation online.
Until then, you must build a local copy of the documentation yourself.

````
# first install packages for generating docs
pip install ipython sphinx nbsphinx nbsphinx-link sphinx-rtd-theme  
cd docs         # enter docs directory
make html       # build docs in html format
````

Then use your favorite web browser to open ``pathml/docs/build/html/index.html``

## Tests and Code Coverage 

You may optionally run the test suite to verify installation. 

To run tests:  
````
conda install pytest    # first install pytest package
python -m pytest        # run test suite
````
Note that because the testing suite tests all parts of the code base, 
this may require installing additional packages as well. 
(e.g. installation of java is required for some functionality).

You may also optionally measure code coverage, i.e. what percentage of code is covered in the testing suite.

To run tests and check code coverage, install all dependencies (including dependencies for multiparametric images), then:
```
conda install coverage  # install coverage package for code coverage
coverage run            # run tests and calculate code coverage
coverage report         # view coverage report
coverage html           # optionally generate HTML coverage report
```

# Getting Started

The [example notebooks](examples) are a good place start with `PathML`.

# Contributing

``PathML`` is an open source project. Consider contributing to benefit the entire community!

There are many ways to contribute to PathML, including:

* Submitting bug reports
* Submitting feature requests
* Writing documentation and examples
* Fixing bugs
* Writing code for new features
* Sharing workflows
* Sharing trained model parameters
* Sharing ``PathML`` with colleagues, students, etc.

See [contributing](CONTRIBUTING.rst) for more details.

# Contact

Questions? Comments? Suggestions? Get in touch!

[PathML@dfci.harvard.edu](mailto:PathML@dfci.harvard.edu)

<img src=https://raw.githubusercontent.com/Dana-Farber-AIOS/pathml/master/docs/source/_static/images/dfci_cornell_joint_logos.png width="750"> 
