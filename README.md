# psenet.tf2

基于tensorflow2.0框架实现的psenet算法，应用场景：图像文本检测，发票文本检测等，内含数据集制作过程。



## Introduction

渐进尺度扩展网络（PSENet）是一种性能很好地检测自然场景图像下任意形状文本的文本检测器。

## Requirements

- python3.+
- tensorflow2.+
- opencv-python 

## Datasets

### 1.文本标注

文本标注用的是labelme工具，安装方法：

`pip install labelme`

标注样本示例：



[20191204_113515.json](./assets/20191204_113515.json)

> Notes: 标注检测执行：python find_no_mark.py

### 2.label转txt

json文件转换txt：

`python json_to_txt.py`

> Notes：对于标记的高像素图片会自动等比缩小到1280尺寸范围内

### 3.生成训练集

生成训练集格式：

`python gen_dataset.py`

> Notes: 会生成.npy文件

## Train

`python train_fpn_resnet.py`

训练日志：

```verilog
[1 / 100] Mean train loss: 0.6657321453094482
Model saved to ./models/ckpt-1
[1 / 100] Mean val loss: 0.5044912695884705
[1 / 100] validate accuracy: 0.69
[2 / 100] Mean train loss: 0.656245768070221
[3 / 100] Mean train loss: 0.6406785845756531
[4 / 100] Mean train loss: 0.5442641973495483
[5 / 100] Mean train loss: 0.561597466468811
[6 / 100] Mean train loss: 0.5449378490447998
[7 / 100] Mean train loss: 0.5977850556373596
[8 / 100] Mean train loss: 0.6664490103721619
[9 / 100] Mean train loss: 0.6052213311195374
[10 / 100] Mean train loss: 0.5618180632591248
[11 / 100] Mean train loss: 0.4806675612926483
Model saved to ./models/ckpt-11
[11 / 100] Mean val loss: 0.43124115467071533
[11 / 100] validate accuracy: 0.69
[12 / 100] Mean train loss: 0.5546953082084656
[13 / 100] Mean train loss: 0.5975295305252075
[14 / 100] Mean train loss: 0.4971678853034973
[15 / 100] Mean train loss: 0.5755234360694885
[16 / 100] Mean train loss: 0.4832138419151306
[17 / 100] Mean train loss: 0.5258355140686035
[18 / 100] Mean train loss: 0.43701183795928955
[19 / 100] Mean train loss: 0.48522889614105225
[20 / 100] Mean train loss: 0.4596312940120697
[21 / 100] Mean train loss: 0.49073970317840576
Model saved to ./models/ckpt-21
[21 / 100] Mean val loss: 0.40604159235954285
[21 / 100] validate accuracy: 0.69
[22 / 100] Mean train loss: 0.5642364621162415
[23 / 100] Mean train loss: 0.47535616159439087
[24 / 100] Mean train loss: 0.5432898998260498
[25 / 100] Mean train loss: 0.4748782515525818
[26 / 100] Mean train loss: 0.48887956142425537
[27 / 100] Mean train loss: 0.4593651294708252
[28 / 100] Mean train loss: 0.6143687963485718
[29 / 100] Mean train loss: 0.546301543712616
[30 / 100] Mean train loss: 0.45350968837738037
[31 / 100] Mean train loss: 0.4532185196876526
Model saved to ./models/ckpt-31
[31 / 100] Mean val loss: 0.3846419155597687
[31 / 100] validate accuracy: 0.69
[32 / 100] Mean train loss: 0.5158385634422302
[33 / 100] Mean train loss: 0.40427166223526
[34 / 100] Mean train loss: 0.5479483604431152
[35 / 100] Mean train loss: 0.47138839960098267
[36 / 100] Mean train loss: 0.5481606721878052
[37 / 100] Mean train loss: 0.6242001056671143
[38 / 100] Mean train loss: 0.5254454612731934
[39 / 100] Mean train loss: 0.424477219581604
[40 / 100] Mean train loss: 0.4655992388725281
[41 / 100] Mean train loss: 0.4868990480899811
Model saved to ./models/ckpt-41
[41 / 100] Mean val loss: 0.5365992784500122
[41 / 100] validate accuracy: 0.71
[42 / 100] Mean train loss: 0.5739839673042297
[43 / 100] Mean train loss: 0.4786255955696106
[44 / 100] Mean train loss: 0.5203943848609924
[45 / 100] Mean train loss: 0.5740344524383545
[46 / 100] Mean train loss: 0.5413140058517456
```



## Tensorboard

![train](assets/psenet.bmp)

## Test

查看模型效果：



## Paper Link

- https://arxiv.org/abs/1903.12473

- https://arxiv.org/abs/1806.02559