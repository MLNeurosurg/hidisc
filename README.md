# Hierarchical Discriminative (HiDisc) Learning Improves Visual Representations of Biomedical Microscopy

Companion code for HiDisc, paper in CVPR 2023.

[**HiDisc Website**](https://hidisc.mlins.org) /
[**arXiv** (Coming soon)](https://github.com/MLNeurosurg/hidisc) /
[**MLiNS Lab**](https://mlins.org) /
[**OpenSRH**](https://opensrh.mlins.org)

## Installation

1. Clone HiDisc github repo
   ```console
   git clone git@github.com:MLNeurosurg/hidisc.git
   ```
2. Install miniconda: follow instructions
    [here](https://docs.conda.io/en/latest/miniconda.html)
3. Create conda environment
    ```console
    conda create -n hidisc python=3.10
    ```
4. Activate conda environment
    ```console
    conda activate hidisc
    ```
5. Install package and dependencies
    ```console
    <cd /path/to/hidisc/repo/dir>
    pip install -e .
    ```

## Directory organization
- hidisc: the library for training HiDisc using OpenSRH
    - datasets: PyTorch datasets to work with OpenSRH
    - losses: HiDisc loss functions with contrastive learning
    - models: PyTorch models for training and evaluation
    - train: training and evaluation scrpits
- README.md
- LICENSE

# Training / evaluation instructions

The code base is written using PyTorch Lightning, with custom network and
datasets for OpenSRH.

To train HiDisc on the OpenSRH dataset:

1. Download OpenSRH - request data [here](https://opensrh.mlins.org).
2. Update the sample config file in `train/config/train_hidisc.yaml` with
    desired configurations.
3. Change directory to `train` and activate the conda virtual environment.
4. Use `train/train_hidisc.py` to start training:
    ```console
    python train_hidisc.py -c=config/train_hidisc_patient.yaml
    ```

To evaluate with your trained model:
1. Update the sample config file in `train/config/eval.yaml` with
    the checkpoint path and other desired configurations.
2. Change directory to `train` and activate the conda virtual environment.
3. Use `train/train_hidisc.py` for knn evaluation:
    ```console
    python eval_knn.py -c=config/eval.yaml
    ```
