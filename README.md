# fair-land-use-change

Exploring the climate response to land use change with the fair emulator

## Getting started guide

We are using dvc to manage data and uv to manage python packages. 

1. If you do not already have DVC installed, follow the [official instructions](https://dvc.org/doc/install). On MacOS with[homebrew](https://brew.sh/) you can use: 
```sh
brew install dvc
```

2. UV is used to manage your python environment. Follow the [official instructions](https://docs.astral.sh/uv/getting-started/installation/) to install it. On MacOS with[homebrew](https://brew.sh/) you can use: 
 ```sh
 brew install uv
 ```

3. Once DVC is installed, run the following command from the same directory as `dvc.yaml` to download the [fair calibration data](https://zenodo.org/records/10566813) (~12GB)
```sh
dvc repro
```
Note: this takes about 5 minutes

4. Use `uv` to install the required packages and create a virtual environment:
```sh
uv sync
```
This will install all dependencies listed in `pyproject.toml` and create a `.venv/` directory for the virtual environment.

5. You're now ready to explore the FAIR emulator!! We encourage you to read [introduction in the documentation](https://docs.fairmodel.net/en/latest/intro.html) to get familiar with how it works

## Directory Structure


```
├── LICENSE           # Project license
├── README.md         # top-level documentation
├── data/             # calibration data (downloaded via dvc)
│   └── calibration/
├── dvc.lock          # DVC tracking file (auto-managed, do not edit)
├── dvc.yaml          # Workflow configuration for DVC
├── notebooks/        # Jupyter notebooks to test out fair
│   ├── README.md
│   └── fair-ssp.ipynb
├── pyproject.toml    # Python dependencies for the project
└── uv.lock           # Lockfile with exact package versions (auto-managed, do not edit)
```
