# Fall_detection
## Dataset:
|  |数据集1 |     数据集2 | Le2i|
| :----- | :--: | :------- |:------- |
| 地址|  http://falldataset.com/ | http://fenix.univ.rzeszow.pl/~mkepski/ds/uf.html |https://pan.baidu.com/s/1m9jMiqIM6mYjtbH1OMwh_Q 提取码：qghr|
| 优点 |  数据集为室内，有每张图像的标签，数据集已经被整理，可以直接打包下载| 数据集含有多角度的图像 |未知|
| 缺点 |  数据集没有标注人类的box。只有每个图像的坐标。  | 数据集同样没有标注人类的box。只有每个图像的坐标。有每张图片的标签。下载不是很方便，批量下载会导致网站无响应。 |无标注|
| 图片的预览|http://falldataset.com/data/489/rgb/rgb_0001.png |http://fenix.univ.rzeszow.pl/~mkepski/ds/data/fall-01-cam0.mp4|无|
## Idea:
- 主要使用第一个数据集，结合部分第二个数据集，进行训练
训练步骤： 
1. 使用 https://github.com/ayooshkathuria/pytorch-yolo-v3 的（pre_trained）预处理模型，对图片中“人”的目标进行检测。输出“人”的坐标，
进行训练
2. 分割train/test data
3. 通过python脚本将boxes的坐标结合已提供的标签生成可以训练的label
4. 使用这些label进行机器学习的训练
5. 检验模型

## RGB to IR
- https://github.com/eneserdo/RGB-to-IR-Translation-with-GAN
- ICCV paper:https://github.com/InnovArul/rgb_IR_personreid

## 综述+汇总
- Fall Detection from Human Shape
and Motion History using Video Surveillance: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=4224216

- pretrained modle: https://github.com/sankalpsahu27/yolov3-with-Tensorflow2.0/blob/main/detect.py

## 2021-9-27
- 使用yolo v3官方预训练模型，进行调用，自动识别“人”，并输出图像的位置。
![output](https://github.com/lizeyujack/Fall_detection/blob/main/output.jpg)
## 2021-9-28
- 可以批量将rgb图像转换为IR图像
- https://github.com/lizeyujack/automatic-recolorization
- 原图
![pic](https://github.com/lizeyujack/automatic-recolorization/blob/main/output_images/rgb_0001_recolored_ideepcolor-px-grid_256_10.png)
- 效果
![pic](https://github.com/lizeyujack/automatic-recolorization/blob/main/intermediate_representation/rgb_0001.gray.png)

## 2021-9-29
- 尝试着用yolov3识别人的模型，批量识别图片中的人，并保存box的左上角和右下角坐标。
- https://github.com/lizeyujack/Fall_detection/blob/main/new.csv

# TODO：
- 寻找更加合适，且方便的数据集（RGB+对应标签信息）
- 寻找用于训练的模型ing，初步计划为
- 参考人体骨骼点检测 https://github.com/cwlroda/falldetection_openpifpaf
- tf+RNN https://github.com/chizhanyuefeng/Realtime-Fall-Detection-for-RNN
- yolo v3训练详细模型+代码 https://github.com/anasbadawy/YOLOv3-Object-Detection
- 初学者教程 ： https://blog.csdn.net/qq_33728095/article/details/116331714
