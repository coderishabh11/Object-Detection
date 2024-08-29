# Object Detection using Pascal VOC 2012 Dataset

## Introduction
This project focuses on object detection using the Pascal VOC 2012 dataset, which contains approximately 12,000 images across 20 object categories. The goal is to recognize and localize objects within realistic scenes. The twenty object classes are:

- **Person**: `person`
- **Animal**: `bird`, `cat`, `cow`, `dog`, `horse`, `sheep`
- **Vehicle**: `aeroplane`, `bicycle`, `boat`, `bus`, `car`, `motorbike`, `train`
- **Indoor**: `bottle`, `chair`, `dining table`, `potted plant`, `sofa`, `tv/monitor`

The project addresses object detection, which involves predicting the bounding box and label of each object in an image.

## Dataset
The Pascal VOC 2012 dataset is used for training and testing. It contains 20 object categories with various challenges like occlusions, varying object sizes, and complex backgrounds.

## Model Implementations

### 1. MobileNet's Caffe Model
**What is MobileNet?**
MobileNet is a convolutional neural network designed for mobile and embedded vision applications. It uses a streamlined architecture based on depthwise separable convolutions, making it lightweight and efficient for devices with limited resources.

**Initial Requirements**
- Caffe prototxt file: Contains the model definition.
- Caffe model file: Contains the pre-trained model weights.

### 2. Faster R-CNN with ResNet-50-FPN Backbone
The Faster R-CNN model is implemented with a ResNet-50-FPN backbone. This model is designed for real-time object detection with region proposal networks. 

**Model Details:**
- **Input:** List of tensors, each of shape `[C, H, W]`, expected in the 0-1 range.
- **Output:** During training, the model returns classification and regression losses. During inference, it returns post-processed predictions including bounding boxes, labels, and scores.

### 3. Faster R-CNN with MobileNetV3-Large-FPN Backbone
Another variant of Faster R-CNN is implemented using the MobileNetV3-Large-FPN backbone. This model is also optimized for real-time object detection with a focus on efficiency.

**Model Details:**
- **Weights:** Pre-trained on COCO, available as `FasterRCNN_MobileNet_V3_Large_FPN_Weights.COCO_V1`.
- **Input/Output:** Similar to the ResNet-50-FPN model, with preprocessing operations such as rescaling images to [0.0, 1.0].

## Getting Started

### Prerequisites
- Python 3.x
- PyTorch
- TorchVision
- Albumentations (for data augmentation)
- Caffe (for MobileNet Caffe model)

### Installation
Clone this repository and install the required packages:
```bash
git clone <repository_url>
cd <repository_directory>
pip install -r requirements.txt
```

## Running the Project

### Training:
To train the models, run the training script with the desired model configuration.

### Evaluation:
Evaluate the trained model on the Pascal VOC 2012 test set.

## Results
- **MobileNet's Caffe Model:** Efficient for embedded systems but with limitations in detection accuracy.
- **Faster R-CNN ResNet-50-FPN:** Achieved higher accuracy in detecting objects across different categories.
- **Faster R-CNN MobileNetV3-Large-FPN:** Balanced approach with good detection accuracy and computational efficiency.

## Conclusion
This project demonstrates the application of different object detection models on the Pascal VOC 2012 dataset. By experimenting with various architectures, we gained insights into the trade-offs between accuracy and computational efficiency.

## References
- [MobileNet Paper (Google, 2017)](https://arxiv.org/abs/1704.04861)
- [Faster R-CNN Paper](https://arxiv.org/abs/1506.01497)
- [Pascal VOC 2012 Dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/)
