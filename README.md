# PACE - Applications of Machine Learning

### OnDemand Website
Once connected to the VPN, go to the [PACE Open OnDemand ICE](https://ondemand-ice.pace.gatech.edu/) website and log in using your GT credentials.

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
  - Select: Node Type: NVIDIA GPU (first available)
 
<p>2. This will submit an Interactive Jupyter job to the scheduler. Click on your Interactive Sessions tab, click on "Connect to Jupyter" once your job is running.</p>

### Environment Preparation
## Prepare an Environment (in Terminal)
Once the Jupyter job has started, run the following commands in a Terminal to prepare a virtual environment.
1. Open a Terminal Session. To open Terminal in Jupyter, click on New (dropdown menu in the upper right corner) -> Terminal.
  - (For CPU Environment; 1.7 GB):
    - `python3 -m venv PACE-ML-CPU-venv`
    - `source PACE-ML-CPU-venv/bin/activate`
    - `pip install --upgrade pip`
    - `pip install ipykernel matplotlib pandas seaborn scikit-learn tensorflow-cpu`
    - `python -m ipykernel install --user --name PACE-ML-CPU-venv`
  - (For GPU Environment; 5.2 GB):
    - `python3 -m venv PACE-ML-GPU-venv`
    - `source PACE-ML-GPU-venv/bin/activate`
    - `pip install --upgrade pip`
    - `pip install matplotlib pandas seaborn scikit-learn ipykernel tensorflow[and-cuda]`
    - `python -m ipykernel install --user --name PACE-ML-GPU-venv`
3. Clone this repo to your home directory and change directory:
  - `git clone https://github.com/jeffvaldez/PACE-Apps-of-ML.git`
4. From the main notebook dashboard in Jupyter, launch the notebook:
  - Open "PACE-Apps-of-ML/PACE-App_of_ML.ipynb"
  - (For CPU Environment):
    - Select: Kernel -> Change Kernel -> PACE-ML-CPU-venv
  - (For GPU Environment):
    - Select: Kernel -> Change Kernel -> PACE-ML-GPU-venv

## Limited Space in Home (in Terminal)
If there not enough space in home folder, you could alternatively create the environment in the scratch folder. Before executing the commands listed above, go to your scratch storage: 
  - `cd ~/scratch`
Then, create the virtual environment as described above. 

