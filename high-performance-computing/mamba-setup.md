
# 🚀 Setup Stage 

### 1. Install Miniforge
- Get it from: [conda-forge/miniforge: A conda-forge distribution.](https://github.com/conda-forge/miniforge)
    - Download installation files for Miniforge on Linux(the `Releases` part of the github contains the miniforge installer download link. https://github.com/conda-forge/miniforge/releases):
      ```bash
      chmod +x filename.sh
      ./filename.sh
      ```
    - Update the base `mamba`:
      ```bash
      mamba update --all
      ```
      
### 2. Mamba Location
- Mamba is located at:
  ```
  miniforge3/etc/profile.d
  ```

### 3. Create a Mamba Environment with PyTorch & JupyterLab
- Set up the environment:
  ```bash
  mamba create -n hghimire pytorch torchvision torchaudio pytorch-cuda=11.8 jupyterlab -c pytorch -c nvidia
  ```
  Replace `hghimire` with mamba env name
- Follow the updated guidelines from the official sources:
  [Start Locally | PyTorch](https://pytorch.org/get-started/locally/)

### 4. Activate Environment & Install JupyterLab
- Activate the environment:
  ```bash
  mamba activate hghimire
  ```
- Install JupyterLab:
  ```bash
  mamba install jupyterlab
  ```

---

# ⚙️ SLURM Job - Configuration Stage 

> 💡 **Note**: When running Jupyter Notebook as a SLURM batch process, the kernel from the `hghimire` environment may not load if `ipykernel` isn't properly configured.

### 1. Configuring "ipykernel"
- To resolve the kernel issue, run the following:
  ```bash
  mamba activate hghimire
  mamba install ipykernel
  ipython kernel install --user --name=<any_name_for_kernel>
  # For example:
  ipython kernel install --user --name=hghimire
  ```

### 2. Submitting the SLURM Job (`sbatch`):
- Submit the SLURM task:
  ```bash
  sbatch torchJupyter.slurm
  ```
- After submission, set up port forwarding to your local machine:
  ```bash
  ssh -N -L localhost:8888:$(hostname):$port hghimire@jacks.local@Innovator.sdstate.edu
  ```

---

# 🔧 SLURM Configuration 

Here’s the SLURM script file (`torchJupyter.slurm`):

```bash
#!/bin/bash
#SBATCH --export=ALL
#SBATCH --job-name="hghimire"
#SBATCH --nodes=2
#SBATCH --ntasks-per-node=32
#SBATCH --output="hghimire.%j.log"
#SBATCH --time=14-00:00:00
#SBATCH --mem=502G
#SBATCH --partition=gpu
#SBATCH --gres=gpu:2

# Setup environment
ENV_NAME="hghimire"
source ~/.bashrc
mamba activate $ENV_NAME

# Load CUDA module
module load cuda
nvcc --version

# Generate a random port number
port=$(shuf -i 6000-9999 -n 1)
USER=$(whoami)
node=$(hostname -s)

# Output instructions for accessing Jupyter Lab
echo -e "
    Jupyter server is running on: $(hostname)
    Job starts at: $(date)
    Copy/Paste the following command into your local terminal:
    --------------------------------------------------------------------
    ssh -N -L localhost:8888:$(hostname):$port hghimire@jacks.local@Innovator.sdstate.edu
    --------------------------------------------------------------------
    Paste the above command into your local system to perform port forwarding.
    --------------------------------------------------------------------
    --------------------------------------------------------------------
    "

# Start Jupyter Lab
unset XDG_RUNTIME_DIR
if [ "$SLURM_JOBTMP" != "" ]; then
    export XDG_RUNTIME_DIR=$SLURM_JOBTMP
fi

jupyter lab --no-browser --port $port --notebook-dir=$(pwd) --ip=$node --NotebookApp.token='' --NotebookApp.password=''

# Keep SLURM job running while Jupyter Lab is active
wait
```

---

### 🔗 **References**:
- [Running a Jupyter Notebook with Mamba on LANTA HPC - LANTA user guide](https://confluence.atlassian.net)
- [How To Setup Jupyter Notebook In Conda Environment And Install Kernel - Python Engineer](https://python-engineer.com)
