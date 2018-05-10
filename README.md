# Atma's notes
## Dask delayed
 - use the load_solutions snippet in talks to hide code cells
 - all derivatives on a `delayed` object are also delayed!!
 - call `.visualize()` off a `delayed` object to see its graph.
 - dask loads data only when needed and you can work on arrays that are larger than memory

## Dask arrays
 - building on `delayed()` is `dask.array`, which can be used on numpy arrays.

## Dask series and dataframes
 - mirror Pandas series and dataframes. Most functions on pd dataframes are available in dask dataframes
 - derivatives of dask dataframe are also delayed

## Implementation
 - dask uses threaded arrays instead of processes, because multiple libs are now good with releasing GIL

## Distributed Dask
 - so far, all of Dask delayed evals were happening on the same machine
 - however, dask can work on distributed clusters as well (PySpark??) People have run this on 1000-10,000 cores.
 
Scott M's original talk about derivatives and delayed evals are similar to what Dask is about.

https://www.surveymonkey.com/r/M8QRPJ9

# Parallel Data Analysis with Dask

Materials for the [Dask tutorial at PyCon 2018](https://us.pycon.org/2018/schedule/presentation/47/).

## First Time Setup

If you don't have `git` installed, you can download a ZIP copy of the repository using the green button above.
Note that the file will be called `dask-tutorial-pycon-2018-master`, instead of `dask-tutorial-pycon-2018`.
Adjust the commands below accordingly.


[Install Miniconda](https://conda.io/miniconda.html) or ensure you have Python 3.6 installed on your system.

```
# Update conda
conda update conda

# Clone the repository. Or download the ZIP and add `-master` to the name.
git clone https://github.com/TomAugspurger/dask-tutorial-pycon-2018

# Enter the repository
cd dask-tutorial-pycon-2018

# Create the environment
conda env create

# Activate the environment
conda activate dask-pycon

# Download data
python prep_data.py

# Start jupyterlab
jupyter lab
```

If you aren't using conda

```
# Clone the repository. Or download the ZIP and add `-master` to the name.
git clone https://github.com/TomAugspurger/dask-tutorial-pycon-2018

# Enter the repository
cd dsak-tutorial-pycon-2018

# Create a virtualenv
python3 -m venv .env

# Activate the env
# See https://docs.python.org/3/library/venv.html#creating-virtual-environments
# For bash it's
source .env/bin/activate

# Install the dependencies
python -m pip install -r requirements.txt

# Download data
python prep_data.py

# Start jupyterlab
jupyter lab
```

## Connect to the Cluster

We have a [pangeo](https://github.com/pangeo-data/pangeo) deployment running that'll provide everyone with their own cluster to try out Dask on some larger problems.
You can log into the cluster by going to:
