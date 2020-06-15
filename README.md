# PyTorch-CycleGAN

Disclaimer: Part of codes are borrowed from [aitorzip/Pytorch-CycleGAN](https://github.com/aitorzip/PyTorch-CycleGAN).

## Prerequisites

Code is intended to work with ```Python 3.7``` and ```Torch 1.4.0```. Previous versions are not tested. 

## Training

Example:

```bash
python train.py --dataroot datasets/hand_syn2real --use_mask=1 --cuda
```
```bash
python test.py --dataroot datasets/hand_syn2real --use_mask=1 --cuda
```


### 1. Setup the dataset

To build the dataset for generating photorealistic hand samples from synthetic images, follow the directory structure below:

    .
    ├── datasets                   
    |   ├── <dataset_name>         # i.e. brucewayne2batman
    |   |   ├── train              # Training
    |   |   |   ├── SynHand        # Contains synthetic hand images (i.e. SynthHand Dataset)
    |   |   |   └── RealHand       # Contains captured hand images with blank backgrounds
    |   |   └── test               # Testing
    |   |   |   ├── SynHand        # Contains synthetic hand images (i.e. SynthHand Dataset)
    |   |   |   └── RealHand       # Contains captured hand images with blank backgrounds
    
### 2. Train
```
./train --dataroot datasets/hand_syn2real/ --cuda
```
Both generators and discriminators weights will be saved under the output directory.

## Testing
```
./test --dataroot datasets/hand_syn2real/ --cuda
```
This command will take the synthetic hand images under the *dataroot/test* directory, run them through the generator and generate photorealistic samples.

## License
This project is licensed under the GPL v3 License.
