# GBFFNet
This repository is an official PyTorch implementation of our paper " A guided bilateral feature fusion network for real-time semantic segmentation". 

## Installation

```
cuda == 10.2
Python == 3.6.4
Pytorch == 1.8.0+cu101
cycler==0.10.0
kiwisolver==1.1.0
matplotlib==3.1.1
numpy==1.15.0
Pillow>=6.2.2
pyparsing==2.4.2
python-dateutil==2.8.1
pytz==2018.4
six==1.12.0
torch==1.1.0
torchvision==0.3.0
torchsummary==1.5.1


```

## Train

```
# cityscapes
python train.py --dataset cityscapes --train_type train --max_epochs 484 --lr 1e-2 --batch_size 12

# camvid
python train.py --dataset cityscapes --train_type train --max_epochs 200 --lr 1e-3 --batch_size 8
```



## Test

```
# cityscapes
python test.py --dataset cityscapes --checkpoint ./checkpoint/cityscapes/GBFFNetbs12gpu1_train/model_484.pth

# camvid
python test.py --dataset camvid --checkpoint ./checkpoint/camvid/GBFFNetbs6gpu1_trainval/model_200.pth
```

## Predict
only for cityscapes dataset
```
python predict.py --dataset cityscapes 
```

## Results

- Please refer to our article for more details.

  ### Cityscapes:

|  Methods  | Input Size | mIoU(%)(val) | mIoU(%)(test) | FPS  |
| :-------: | :--------: | :----------: | :-----------: | :--: |
| GBFFNet-R18 | 2048x1024  |     78.8     |     78.7      | 51.6 |
| GBFFNet-T | 2048x1024  |     78.3     |     77.8      | 86.7 |
| GBFFNet-B | 2048x1024  |     79.2     |     79.0      | 72.3 |

### CamVid:

|  Methods  | pre-trained | Input Size | mIoU(%) |  FPS  |
| :-------: | :---------: | :--------: | :-----: | :---: |
| DBBGNet-R18 |     yes     |  960x720   |  78.2   | 122.4 |
| DBBGNet-T |     yes     |  960x720   |  77.4   | 179.6 |
| DBBGNet-B |     yes     |  960x720   |  78.9   | 142.1 |





## Thanks && Refer

```bash
@misc{Efficient-Segmentation-Networks,
  author = {Yu Wang},
  title = {Efficient-Segmentation-Networks Pytorch Implementation},
  year = {2019},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/xiaoyufenfei/Efficient-Segmentation-Networks}},
  commit = {master}
}
@article{xu2023lightweight,
  title={Lightweight Real-Time Semantic Segmentation Network With Efficient Transformer and CNN},
  author={Xu, Guoan and Li, Juncheng and Gao, Guangwei and Lu, Huimin and Yang, Jian and Yue, Dong},
  journal={IEEE Transactions on Intelligent Transportation Systems},
  year={2023},
  publisher={IEEE}
}
```
