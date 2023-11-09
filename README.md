# PACE - Applications of Machine Learning

### OnDemand Website
Once connected to the VPN, go to the [PACE Open OnDemand ICE](https://ondemand-ice.pace.gatech.edu/) website using your GT credentials.

### Submit Interactive Jupyter Job to ICE Cluster
Submit an Interactive Jupyter job to the PACE-ICE default queue on the PACE Open OnDemand ICE website:
- (For CPU Environment)
  - Start a Jupyter notebook job. Click on Interactive Apps (dropdown menu) -> Jupyter
  - Select Anaconda Module: Anaconda 3 - 2022.05
  - Select Quality of Service: pace-ice
  - Select Node Type: Intel CPU<br>
- (For GPU Environment)
  - Start a Jupyter notebook job. Click on Interactive Apps (dropdown menu) -> Jupyter
  - Select Anaconda Module: Anaconda 3 - 2022.05
  - Select Quality of Service: pace-ice
  - Select Node Type: NVIDIA GPU V100 16GB
 
<p>2. This will submit an Interactive Jupyter job to the scheduler. Click on your Interactive Sessions tab, click on "Connect to Jupyter" once your job is running.</p>

### Environment Preparation
## Prepare an Environment (in Terminal)
Once the Jupyter job has started, run the following commands in a Terminal to prepare an environment.
1. Open a Terminal Session. To open Terminal in Jupyter, click on New (dropdown menu in the upper right corner) -> Terminal.
  - (For CPU Environment):
    - `conda create -y -n PACE-ML-CPU-env python=3.10 ipykernel`
    - `conda activate PACE-ML-CPU-env`
    - `pip install intel-tensorflow-avx512==2.9.1 matplotlib pandas seaborn scikit-learn`
    - `python -m ipykernel install --user --name PACE-ML-CPU-env`
  - (For GPU Environment):
    - `conda create -y -n PACE-ML-GPU-env python=3.10 ipykernel`
    - `conda activate PACE-ML-GPU-env`
    - `pip install tensorflow[and-cuda] matplotlib pandas seaborn scikit-learn`
    - `python -m ipykernel install --user --name PACE-ML-GPU-env`
3. Clone this repo to your home directory and change directory:
  - `git clone https://github.com/jeffvaldez/PACE-Apps-of-ML.git`
4. From the main notebook dashboard in Jupyter, launch the notebook:
  - (For CPU Environment):
    - Open "PACE-Apps-of-ML/PACE-App_of_ML-CPU.ipynb"
  - (For GPU Environment):
    - Open "PACE-Apps-of-ML/PACE-App_of_ML-GPU.ipynb"



## Limited Space in Home (Terminal)
If there not enough space in home folder, you could alternatively create the environment in the temporary Scratch running the below commands before conda create (no prefix): 
  - `mkdir ${TMPDIR}/.conda`
  - `ln -s ${TMPDIR}/.conda ${HOME}/.conda`

## Save Environment
*If you want to save your environment, you can run commands like `conda env export` or `conda env export --from-history` or `pip freeze`*
