# Exoplanet ML 

Machine learning models and utilities for exoplanet science. This repo was ran on AMD's ROCm. Using the following docker image: [rocm/tensorflow:rocm4.0.1-tf1.15-dev](https://hub.docker.com/layers/rocm/tensorflow/rocm4.0.1-tf1.15-dev/images/sha256-2cbb5e6fdfb86120e900b60d1001f87c4ac04cb1bc27ce4ab43bd59186352b36?context=explore).

## Code Author

Chris Shallue: [@cshallue](https://github.com/cshallue)

## Walkthrough

You can jump straight to the [AstroNet walkthrough](exoplanet-ml/astronet/README.md#walkthrough).

Otherwise, click through to the desired directory as outlined below.

## Directories

[astronet/](exoplanet-ml/astronet/)

* A neural network for identifying exoplanets in light curves. Contains code for:
  * Downloading and preprocessing Kepler light curves.
  * Building different types of neural network classification models.
  * Training and evaluating a new model.
  * Using a trained model to generate new predictions.

[astrowavenet/](exoplanet-ml/astrowavenet/)

* A generative model for light curves.

[light_curve/](exoplanet-ml/light_curve)

* Utilities for operating on light curves. These include:
  * Reading Kepler data from `.fits` files.
  * Applying a median filter to smooth and normalize a light curve.
  * Phase folding, splitting, removing periodic events, etc.
* [light_curve/fast_ops/](exoplanet-ml/light_curve/fast_ops) contains optimized
C++ light curve operations.

[tf_util/](exoplanet-ml/tf_util)

* Shared TensorFlow utilities.

[third_party/](exoplanet-ml/third_party/)

* Utilities derived from third party code.


# Setup

## Required Packages

* **TensorFlow** ([instructions](https://www.tensorflow.org/install/))
* **Pandas** ([instructions](http://pandas.pydata.org/pandas-docs/stable/install.html))
* **NumPy** ([instructions](https://docs.scipy.org/doc/numpy/user/install.html))
* **SciPy** ([instructions](https://scipy.org/install.html))
* **AstroPy** ([instructions](http://www.astropy.org/))
* **PyDl** ([instructions](https://pypi.python.org/pypi/pydl))
* **Bazel** ([instructions](https://docs.bazel.build/versions/master/install.html))
* **Abseil Python Common Libraries** ([instructions](https://github.com/abseil/abseil-py))

## Run Unit Tests

Verify that all dependencies are satisfied by running the unit tests:

```bash
cd exoplanet-ml  # Bazel must run from a directory with a WORKSPACE file
bazel test astronet/... astrowavenet/... light_curve/... tf_util/... third_party/... --test_arg=--test_srcdir=/root/exoplanet-ml/exoplanet-ml/
```

# Citation

If you find this code useful, please cite our paper:

Shallue, C. J., & Vanderburg, A. (2018). Identifying Exoplanets with Deep
Learning: A Five-planet Resonant Chain around Kepler-80 and an Eighth Planet
around Kepler-90. *The Astronomical Journal*, 155(2), 94.

Full text available at [*The Astronomical Journal*](http://iopscience.iop.org/article/10.3847/1538-3881/aa9e09/meta).

# Disclaimer

This is not an official Google product.
