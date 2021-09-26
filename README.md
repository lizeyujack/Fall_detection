# Fall_detection
## Dataset:
|  |数据集1 |     数据集2 |
| :----- | :--: | :------- |
| 地址|  http://falldataset.com/ | http://fenix.univ.rzeszow.pl/~mkepski/ds/uf.html |
| 优点 |  数据集为室内，有每张图像的标签，数据集已经被整理，可以直接打包下载| 数据集含有多角度的图像 |
| 缺点 |  数据集没有标注人类的box。只有每个图像的坐标。  | 数据集同样没有标注人类的box。只有每个图像的坐标。有每张图片的标签。下载不是很方便，批量下载会导致网站无响应。 |
| 图片的预览|http://falldataset.com/data/489/rgb/rgb_0001.png |http://fenix.univ.rzeszow.pl/~mkepski/ds/data/fall-01-cam0.mp4|
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

