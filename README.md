# Official implementation for TransDA
Official pytorch implement for “Transformer-Based Source-Free Domain Adaptation”
## Overview:
<img src="image/overview.png" width="600"/>

## Result:
<img src="image/result_office31.png" width="600"/>
<img src="image/result_officehome.png" width="600"/>


## Prerequisites:
- python == 3.6.8
- pytorch ==1.1.0
- torchvision == 0.3.0
- numpy, scipy, sklearn, PIL, argparse, tqdm

## Prepare pretrain model
we choose R50-ViT-B_16 as our encoder.
```bash root transformerdepth
wget https://storage.googleapis.com/vit_models/imagenet21k/R50+ViT-B_16.npz 
mkdir ./model/vit_checkpoint/imagenet21k 
mv R50+ViT-B_16.npz ./model/vit_checkpoint/imagenet21k/R50+ViT-B_16.npz
```

## Dataset:
- Please manually download the datasets [Office](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0), [Office-Home](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0), [VisDA](https://github.com/VisionLearningGroup/taskcv-2017-public/tree/master/classification), [Office-Caltech](https://www.dropbox.com/sh/vja4cdimm0k2um3/AACCKNKV8-HVbEZDPDCyAyf_a?dl=0) from the official websites, and modify the path of images in each '.txt' under the folder './data/'.
- The script "download_visda2017.sh" in data fold also can use to download visda
## Training
### office-31
    ```python
    sh run_office_uda.sh
    ```
### office-home
    ```python
    sh run_office_home_uda.sh
    ```
### office-VisDA
    ```python
    sh run_visda.sh
    ```
# Reference

[ViT](https://github.com/jeonsworld/ViT-pytorch)

[SHOT](https://github.com/tim-learn/SHOT)
