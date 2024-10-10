
# 🔧 Session with 'tmux'

### 1. Start terminal session with `tmux`
| Action            | Command                             |
|-------------------|-------------------------------------|
| New session       | `tmux new -s session_name`          |
| Attach            | `tmux attach -t session_name`       |
| Detach            | `Ctrl + b`, then `d`                |
| List running tmux | `tmux ls`                           |

---

### 2. Activate Environment
- Run the command:
  ```bash
  mamba activate hghimire
  ```

### 3. Submit the SLURM file:
- Run the SLURM job:
  ```bash
  sbatch torchJupyter.slurm
  ```

### 4. Check if the SLURM job is running:
- Use the following command:
  ```bash
  squeue -u $USER
  ```

### 5. Check Logs:
- To view the logs, run:
  ```bash
  cat *.log
  ```

### 6. Port Forwarding:
- Copy the command from the log file and run it in the local Windows command prompt to perform port forwarding from the HPC cluster to local.

### 7. Detach the tmux session:
- Use the following keyboard shortcut:
  ```bash
  CTRL + B, then D
  ```

---

### 🔗 Once Jupyter Notebook is loaded in `localhost:8888`, the next step is to...

---

### 🔍 Additional Checks:
- **Check if NVIDIA GPU is loaded**:
  Run in terminal:
  ```bash
  nvidia-smi
  ```
- **Check if CUDA is loaded**:
  Run in terminal:
  ```bash
  nvcc --version
  ```
