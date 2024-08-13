# PACE - Applications of Machine Learning

### OnDemand Website
Once connected to the VPN, go to the [PACE Open OnDemand ICE](https://ondemand-ice.pace.gatech.edu/) website using your GT credentials.

### Submit Interactive Jupyter Job to ICE Cluster
Submit an Interactive Jupyter job to the PACE-ICE default queue on the PACE Open OnDemand ICE website:
- (For CPU Environment)
  - Start a Jupyter notebook job. Click on Interactive Apps (dropdown menu) -> Jupyter
  - Select: Anaconda Module: Anaconda 3 - 2023.03
  - Select: Quality of Service: pace-ice
  - Select: Node Type: Intel CPU
- (For GPU Environment)
  - Start a Jupyter notebook job. Click on Interactive Apps (dropdown menu) -> Jupyter
  - Select: Anaconda Module: Anaconda 3 - 2023.03
  - Select: Quality of Service: pace-ice
  - Select: Node Type: NVIDIA GPU V100 16GB
 
<p>2. This will submit an Interactive Jupyter job to the scheduler. Click on your Interactive Sessions tab, click on "Connect to Jupyter" once your job is running.</p>

### Environment Preparation
## Prepare an Environment (in Terminal)
Once the Jupyter job has started, run the following commands in a Terminal to prepare an environment.
1. Open a Terminal Session. To open Terminal in Jupyter, click on New (dropdown menu in the upper right corner) -> Terminal.
  - (For CPU Environment):
    - `conda create -y -n PACE-ML-CPU-env python=3.10 ipykernel`
    - `conda activate PACE-ML-CPU-env`
    - `conda install pip`
    - `pip install intel-tensorflow-avx512==2.9.1 matplotlib pandas seaborn scikit-learn`
    - `python -m ipykernel install --user --name PACE-ML-CPU-env`
  - (For GPU Environment):
    - `conda create -y -n PACE-ML-GPU-env python=3.10 ipykernel`
    - `conda activate PACE-ML-GPU-env`
    - `conda install pip`
    - `pip install tensorflow[and-cuda] matplotlib pandas seaborn scikit-learn`
    - `python -m ipykernel install --user --name PACE-ML-GPU-env`
3. Clone this repo to your home directory and change directory:
  - `git clone https://github.com/jeffvaldez/PACE-Apps-of-ML.git`
4. From the main notebook dashboard in Jupyter, launch the notebook:
  - Open "PACE-Apps-of-ML/PACE-App_of_ML.ipynb"
  - (For CPU Environment):
    - Select: Kernel -> Change Kernel -> Python [conda env:.conda-PACE-ML-CPU-env]
  - (For GPU Environment):
    - Select: Kernel -> Change Kernel -> Python [conda env:.conda-PACE-ML-GPU-env]

## Limited Space in Home (in Terminal)
If there not enough space in home folder, you could alternatively create the environment in the temporary Scratch running the below commands before conda create (no prefix): 
  - `mkdir ${TMPDIR}/.conda`
  - `ln -s ${TMPDIR}/.conda ${HOME}/.conda`

## Save Environment (in Terminal)
*If you want to save your environment, you can run commands like `conda env export` or `conda env export --from-history` or `pip freeze`*
