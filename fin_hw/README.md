## cifar100-classification-with-CNN-and-Transformer（Task1 & Task3）

本次实验使用CeiT作为 CNN + Transformer 的网络模型  
使用 ResNet50 作为相同参数量的CNN对比模型1  
使用 DenseNet201 作为相同浮点数计算量的CNN对比模型2 
分割结果：[链接](https://pan.baidu.com/s/1Ks3TcoZ2XvDp8N6oE0ueHA) 
提取码：v6m5 

### 文件下载
在这里下载checkpoint和log文件  

[CeiT](https://pan.baidu.com/s/1zvmNg50kYrgA9nL-8d2myg)：  
提取码：4aej  

[CNN](https://pan.baidu.com/s/1Y53VkqbLyD9MOciWnZd76w)：  
提取码：kfus   

### Task1(Semantic Segmentation for driving video)
CNN 文件夹中包含两个模型，ResNet50 和 DenseNet201 
 
#### train:
```python
python train.py -net resnet50/densenet201 -gpu
```

#### test：
```python
python test.py -net densenet201 -weights checkpoint/densenet201.pth -gpu
```
checkpoint文件见百度网盘  

### Task3(CeiT)
CNN_Transformer 文件夹中包含CeiT的相关文件 

#### Train :
```
python train.py -c configs/default.yaml --name "name_of_exp"
```

#### test :
```python
python test.py -c configs/defaul.yaml --name "test" -p checkpoint/checkpoint.pyt

```
checkpoint 文件见百度网盘

## Task2(Faster-Rcnn):

### install mmdetetion 
a) random init ResNet50 
```
python tools/train.py configs/amy_config/faster_rcnn_r50_fpn_1x_voc_normal_init.py  --auto-scale-lr
# comment faster_rcnn_r50_fpn_1x_voc_normal_init.py line 6 and configs/_base_/models/faster_rcnn_r50_fpn.py line 13
```
b) COCO init ResNet50 
```
python tools/train.py configs/amy_config/faster_rcnn_r50_fpn_1x_voc_normal_init.py  --auto-scale-lr
# change faster_rcnn_r50_fpn_1x_voc_normal_init.py line 6 checkpoint=mmdet official faster-rcnn coco ckpt
```
c) Mask-Rcnn init ResNet50 
```
python tools/train.py configs/amy_config/faster_rcnn_r50_fpn_1x_voc_normal_init.py  --auto-scale-lr
# change faster_rcnn_r50_fpn_1x_voc_normal_init.py line 6 checkpoint=mask_res50.pth
```
[mask_res50.pth is here](https://pan.baidu.com/s/1HNbPocLiQbDca5H2L7FuoQ) code: cugw 

### Reference:
* [Incorporating Convolution Designs into Visual Transformers](https://arxiv.org/pdf/2103.11816v2.pdf)
* https://github.com/rishikksh20/CeiT-pytorch.git
* https://github.com/weiaicunzai/pytorch-cifar100.git
