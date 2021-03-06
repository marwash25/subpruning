# Data-Efficient Structured Pruning via Submodular Optimization

Code to reproduce results of the paper [Data-Efficient Structured Pruning via Submodular Optimization](https://arxiv.org/abs/2203.04940)

## Installation

To install dependencies:

```bash
# Create a python virtualenv or conda env and activate it
# With conda
conda install --file requirements.txt -y

# With pip
pip install -r requirements.txt 

#  add the path to subpruning folder to your `PYTHONPATH`.  For example:
export PYTHONPATH="$PYTHONPATH:$HOME/subpruning/"
```

To install the submodular maximization package from https://github.com/sbuschjaeger/SubmodularStreamingMaximization (code already included in SubmodularStreamingMaximization folder)

```bash
cd subpruning/SubmodularStreamingMaximization/
pip install --upgrade pip
pip install --upgrade setuptools
pip install cmake
pip install -e .
```

To download data and pretrained weights:
```bash
# Install git lfs: https://git-lfs.github.com/ then fetch data and weights
git lfs fetch --all
```

# Test installation

```bash
cd subpruning/shrinkbench/scripts
python test.py
```

# To reproduce results in the paper

- run one layer pruning script (used for perlayer budget selection): subpruning/shrinkbench/scripts/lay_pruning_job.sh 
- run script for multiple layers pruning (to reproduce all results in the paper): subpruning/shrinkbench/scripts/pruning_job.sh 
- plot results using subpruning/shrinkbench/jupyter/visualize_results.ipynb notebook

Note: make sure to adapt the PYTHONPATH in both lay_pruning_job.sh and pruning_job.sh, and the one layer pruning job ids in pruning_job.sh

# To cite our paper
```
@misc{elhalabi2022dataefficient,
      title={Data-Efficient Structured Pruning via Submodular Optimization}, 
      author={Marwa El Halabi and Suraj Srinivas and Simon Lacoste-Julien},
      year={2022},
      eprint={2203.04940},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```
# Acknowledgements

- Our code builds on the open source ShrinkBench library: https://github.com/JJGO/shrinkbench
- We use the Greedy algorithm code from https://github.com/sbuschjaeger/SubmodularStreamingMaximization, with some modifications
- Our implementation of the LayerSampling pruning method is adapted from the original code provided in https://github.com/lucaslie/torchprune
- We use the implementation of VGG11 provided in https://github.com/huyvnphan/PyTorch_CIFAR10/tree/v3.0.1
- We use a progress bar from https://github.com/gipert/progressbar
