# garbage-classification

Author: Xinming Wang, Yufeng Xing


# Goal

- Boundary detection
- Garbage type classification

Every minute, at least 15 tonnes of plastic waste leak into the ocean. How to reduce and recycle the garbage is a meaningful topic. If we could use deep learning methods to detect and classify garbage in an image, we might be able to clean up the waste more efficiently.


# Dataset

TACO is an open image dataset of waste in the wild. It contains photos of garbage taken in various environments.

Dataset Overview:
- 1500 images
- 4784 annotations
- 60 sub-categories & 28 super-categories

| Dataset Overview  | data by category | data by super category |
| ------------- | ------------- | ------------- |
| ![Image](https://github.com/Ming2010/garbage-classification/blob/main/img/dataset_preview.png)  | ![Image](https://github.com/Ming2010/garbage-classification/blob/main/img/data_by_cat.png)  | ![Image](https://github.com/Ming2010/garbage-classification/blob/main/img/data_by_supcat.png)

# Model

We tried both RetinaNet and MoblieNetV2 as our models.

- RetinaNet

RetinaNet is one of the best one-stage object detection models that has proven to work well with dense and small scale objects.

We fine-tuned the pre-trained RetinaNet to perform the boundary detection on our data.

- MobileNetV2

MobileNetV2 is a small, low-latency, low-power model parameterized to meet the resource constraints of a variety of use cases (mobile phone, for example). It can be built upon for classification, detection, embedding and segmentation similar to how other popular large scale models.

We fine-tuned the MobileNetV2 to perform both boundary detection and garbage classfication on our data.

# Result

Our models are able to detect the garbage from different environments and classify the garbage. However, some of the categories do not exist in pre-built model, so we did a mapping to make it fit. Plus, our model is slow, so it was hard to tune hyperparameters. To improve, we may think about including more garbage class types, performing more accurate boundary detection, and do some model-level improvement.


# References

dataset: http://tacodataset.org/