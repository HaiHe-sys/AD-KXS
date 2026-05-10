# Model for AD/AChE/MAO-A/5-HT6
Screening models for potential AD/AChE/MAO-A/5-HT6 inhibitors based on Chemprope .

###Project Introduction
This project is a code replication of the paper "Deep learning-based drug screening for the discovery of potential therapeutic agents for Alzheimer's disease" <https://www.sciencedirect.com/science/article/pii/S2095177924001199>.

This project leverages a directed message passing neural network (D-MPNN) to capture the relationship between molecular structures and biological activities, enabling the prediction of molecules with desired properties.

The repository is dedicated to implementing model training and evaluation for classification tasks, specifically predicting whether a molecule exhibits potential inhibitory activity against AD/AChE/MAO-A/5-HT6.

It includes comprehensive scripts for data preprocessing, model construction, training, and evaluation, along with illustrative training examples based on the DRD1 dataset.

Virtual environment installation
`Installing from PyPi`
`conda create -n DRD1 python=3.8`
`conda activate chemprop`
`conda install -c conda-forge rdkit`
`pip install git+https://github.com/bp-kelley/descriptastorus`
`pip install chemprop`

Data
Training data
Training data must include molecules (as SMILES strings) along with their known target values.For specific examples, please refer to input

Testing data
Testing data must include molecules (as SMILES strings) For specific examples, please refer to input

Hyperparameter Optimization

`chemprop_hyperopt --data_path <training_data_path> --dataset_type classificiation --num_iters 20 --config_save_path <hyperparameter_save_path>`

Training

`chemprop_train --data_path <training_data_path> --dataset_type classificiation --save_dir <model_save_path> --num_folds 10 --confi_path <hyperparameter_save_path>`

Predicting

`chemprop_predict --test_path <testing_data_path> --checkpoint_dir <model_save_path> --preds_path <predicting_save_path>`
