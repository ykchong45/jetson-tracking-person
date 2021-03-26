# Jetson Tracking Project

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15czITEKu8PnmlB5KRhmxiKVPXEc8ZeoQ?usp=sharing)

## Current progress

The notebook can identify the person in the video, keep track of the person and output a video with bounding box correctly. This fulfills the basic objective of the project.

Multiple models and tracking algorithms have been tested, the best pair is `CenterNet MobileNetV2 FPN 512x512` with `CSRT tracker`.

## Overview

For a practical Jetson use case, TensorRT support for the DL model is a must. As suggested on the Internet, `SSD mobilenet v2`  is [optimized for Jetson](https://github.com/dusty-nv/jetson-inference). But this project uses CenterNet, which is needed to be converted to TensorRT before deployment.

Phase 1: intended to be done for our project. 

Phase 2: to fine tune the model. (Optional)

Phase 3: to deploy the project on the hardware. (Optional)


## Steps

### Phase 1

- [x] Create a Tensorflow [notebook](https://tfhub.dev/tensorflow/ssd_mobilenet_v2/2) on object detection using pre-trained model.
- [x] Temporarily disable detection of other object class.
- [ ] (Skipped) Add a pipeline for [live video](https://github.com/IAmSuyogJadhav/Lightning-Fast-Object-Detector) detection. <sup>1<sup>
- [ ] (Skipped) [Reshape](https://github.com/tensorflow/models/issues/3196) recorded video for model input. <sup>2</sup>
- [x] Format output file and bounding box.

### Phase 2

- [x] Enhance tracking performance with OpenCV tracking algo.
- [ ] Fine tune the model via [Transfer learning](https://stackoverflow.com/a/48584180/10566022) and detect person only.

### Phase 3 [Deployment]

- [ ] Convert to [TensorRT](https://github.com/SteveMacenski/jetson_nano_detection_and_tracking).

## Footnotes
1. Jupyter Notebook couldn't render live video.
2. Time taken for a 720\*2560 image detection is roughly the same as for a 720\*1280 image.
