# Addressing Underestimation Bias in Multi-Label Image Classification

This repository contains code and dataset for our paper in MODEM 2023:

## "Beyond Accuracy: Addressing Underestimation Bias in Multi-Label Image Classification" 
William Blanzeisky, Padraig Cunningham


## Requirements
* Python 3.6+
* PyTorch 1.0+
* h5py
* tensorboardX

## Data Preparation (source: [Effective Strategies for Bias Mitigation](https://github.com/princetonvisualai/DomainBiasMitigation/tree/c432e751632bce2c7467ef22a6ffb44402b88684)
1. Download and unzip the CIFAR-10 and CINIC-10 by running the script `download.sh`
2. Manually download the [CelebA dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html), put `Anno` into `data/celeba/Anno`, `Eval` into `data/celeba/Eval`, put all align and cropped images to `data/celeba/images`

Run the `preprocess_data.py` to generate data for all experiments (this step involves creating h5py file for CelebA images, so would take some time 1~2 hours)

## Run Experiments
To conduct experiments, run `main.py` with corresponding arguments (`experiment` specifies which experiment to run, `experiment_name` specifies a name to this experiment for saving the model and result). For example:

```
python main.py --experiment celeba_baseline --experiment_name e1 --random_seed 1
```

After running, the experiment result will be saved under `record/experiment/experiment_name`


## Our experiments for addressing underestimation bias use the CVPR paper "Effective Strategies for Bias Mitigation" as the baseline to compare our proposed method with. Our base model is saved under models/ResNet_FC_MOPSO. The training procedure for our framework is in runPSO.py.
