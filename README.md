# PatchCleanser
PatchCleanser, which provides certifiable robustness against adversarial patches for any image classifier. 


## Requirements

The code is tested with PyTorch 1.7.0 and timm 0.4.12. The complete list of required packages are available in `requirement.txt`, and can be installed with `pip install -r requirement.txt`. The code should be compatible with newer versions of packages.

## Files

```shell
├── README.md                        #this file 
├── requirement.txt                  #required package
├── example_cmd.sh                   #example command to run the code
| 
├── pc_certification.py              #PatchCleanser: certify robustness via two-mask correctness 
├── pc_clean_acc.py                  #PatchCleanser: evaluate clean accuracy and per-example inference time
| 
├── vanilla_clean_acc.py             #undefended vanilla models: evaluate clean accuracy and per-example inference time
├── train_model.py                   #train undefended vanilla models for different datasets
| 
├── utils
|   ├── setup.py                     #utils for constructing models and data loaders
|   ├── defense.py                   #utils for PatchCleanser defenses
|   └── cutout.py                    #utils for masked model training
|
├── misc
|   ├── reproducibility.md           #detailed instructions for reproducing paper results
|   ├── pc_mr.py                     #script for minority report (Figure 9)
|   └── pc_multiple.py               #script for multiple patch shapes and multiple patches (Table 4)
| 
├── data   
|   ├── imagenet                     #data directory for imagenet
|   ├── imagenette                   #data directory for imagenette
|   ├── cifar                        #data directory for cifar-10
|   ├── cifar100                     #data directory for cifar-100
|   ├── flower102                    #data directory for flower102
|   └── svhn                         #data directory for svhn
|
└── checkpoints                      #directory for checkpoints
    ├── README.md                    #details of checkpoints
    └── ...                          #model checkpoints
```

## Datasets

- [ImageNet](https://image-net.org/download.php) (ILSVRC2012)
- [ImageNette](https://github.com/fastai/imagenette) ([Full size](https://s3.amazonaws.com/fast-ai-imageclas/imagenette2.tgz))
- [CIFAR-10/CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html)
- [Oxford Flower-102](https://www.robots.ox.ac.uk/~vgg/data/flowers/102/)
- [SVHN](http://ufldl.stanford.edu/housenumbers/)

## Usage

- See **Files** for details of each file. 
- Download data in **Datasets** to `data/`.
- (optional) Download checkpoints from Google Drive [link](https://drive.google.com/drive/folders/1Ewks-NgJHDlpeAaGInz_jZ6iczcYNDlN?usp=sharing) and move them to `checkpoints`.
- (optional) Download pre-computed two-mask predictions for ImageNet from Google Drive [link](https://drive.google.com/drive/folders/1Ewks-NgJHDlpeAaGInz_jZ6iczcYNDlN?usp=sharing) and move them to `dump`. Computing two-mask predictions for other datasets shouldn't take too long.
- See [`example_cmd.sh`](example_cmd.sh) for example commands for running the code.
- See [`misc/reproducibility.md`](./misc/reproducibility.md) for instructions to reproduce all results in the main body of paper.


