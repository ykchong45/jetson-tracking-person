# Jetson Tracking Project



## Overview

For a practical Jetson use case, TensorRT support for the DL model is a must. As suggested on the Internet, `SSD mobilenet v2`  is [optimized for Jetson](https://github.com/dusty-nv/jetson-inference).

Phase 1: intended to be done for our project. 

Phase 2: to fine tune the model. (Optional)

Phase 3: to deploy the project on the hardware. (Optional)



## Steps

### Phase 1

1. Create a Tensorflow [notebook](https://tfhub.dev/tensorflow/ssd_mobilenet_v2/2) on object detection using pre-trained model.
2. Temporarily disable detection of other object class.
3. Add a pipeline for [live video](https://github.com/IAmSuyogJadhav/Lightning-Fast-Object-Detector) detection.
4. [Reshape](https://github.com/tensorflow/models/issues/3196) recorded video for model input.
5. Format output file and bounding box.



### Phase 2

1. Fine tune the model via [Transfer learning](https://stackoverflow.com/a/48584180/10566022) and detect person only.



### Phase 3 [Deployment]

1. Convert to [TensorRT](https://github.com/SteveMacenski/jetson_nano_detection_and_tracking).