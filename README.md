Object Detection Sample on Jetson
======================================
Please get the requirements installed first.
</br>
</br>

## Pipeline-1: TensorFlow Object Detection API
**Dependency**
```C
$ sudo apt-get install git protobuf-compiler python-pil python-lxml python-tk
```

**Object Detection API**

```C
$ git clone https://github.com/tensorflow/models.git
$ cd models/research/
$ protoc object_detection/protos/*.proto --python_out=.
$ export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
$ cd ../../
```

**Download SSD Model**
```C
$ wget http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz
$ tar -xvzf ssd_mobilenet_v1_coco_2017_11_17.tar.gz 
```
** 其它模型 **
https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md
download the model: faster_rcnn_inception_resnet_v2_atrous_coco
这个模型我之前测试识别手机，很准确

**Test Pipeline 1**
```C
$ python object_detection-1.py
```

note: maybe change the camera 
line 110：  gst = "v4l2src device=/dev/video0 ! video/x-raw, ...."

</br>
</br>
</br>
</br>
</br>
