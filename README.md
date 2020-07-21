# darkflow_he
根据自己需求改进的darkflow

背景介绍：darkflow是darknet在python上的实现，因为darknet源码是C/C++写的，为了方便，用了darkflow，要去实际工程应用，最好还是用darknet。
darkflow的原码也在文件夹内，可以重新开始使用，说明在文件夹内的.md文件内，注意，在安装的时候，选择第2种方法，即：

Let pip install darkflow globally in dev mode (still globally accessible, but changes to the code immediately take effect)

pip install -e .

本项目在原darkflow项目的基础上实现了相机调用、视频读取并输出结果视频等功能。并调用了yolo_lite的权重文件实现物体识别。

## 改动之处
1.改变了flow文件，使得能够在IED里运行flow（懒得去下一层再修改代码了），推荐pycharm；

2.在darkflow/darkflow/net/文件夹下增加flow_realtimecamera.py和flow_readvideofile.py文件，这两个文件分别实现了调用相机实时显示结果、读取视频文件识别并输出，在使用的时候注意修改相对应设置，大华和海康相机的视频流调用方法均可在网上搜索到。但是在使用的时候要注意应该把文件名命名为flow.py才能调用，使用哪个就修改哪个；

3..darkflow/文件夹下的label文件是调用相应weights所需要的标签名字文件，当调用的weights数据是由coco数据集训练出来时，应该用labels_coco.txt文件，当weights文件是由voc数据集训练出来的，用labels_voc.txt文件，使用的时候均要将其重命名为labels.txt。

4.darkflow/cfg/文件夹下是一些训练出来的权重文件，来源于yolo-lite项目。
