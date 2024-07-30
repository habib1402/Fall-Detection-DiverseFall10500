# Visionary Vigilance: Optimized YOLOV8 for Fallen Person Detection with Large-Scale Benchmark Dataset
## Overview
This repository contains the ways of progressive modifications in the proposed network and a diverse and comprehensive dataset for fall detection research. The dataset is a large-scale benchmark comprising approximately 10,500 samples with corresponding annotations.
## Abstract
Falls pose a significant risk to elderly people, patients with diseases such as neurological disorders, cardiovascular diseases, and disabled children. This highlights the need for real-time intelligent fall detection (FD) systems for quick relief leading to assisted living. The existing attempts are often based on multimodal approaches which are computationally expensive due to multi-sensor integration. The computer vision (CV) based era for FD needs the deployment of state-of-the-art (SOTA) networks progressive enhancements to grasp falls effectively. However, CV-based systems often lack the ability to operate efficiently in real-time and the attempts for visual intelligence are often not integrated at feasible stages of the networks. Moreover, the lack of large-scale well-annotated benchmarks limits the ability of FD in challenging and complex environments. To bridge the research gaps, we proposed an enhanced version of YOLOV8 for FD. Our research presents significant contributions to the field of FD, addressing critical limitations through three key contributions. Initially, a comprehensive large-scale dataset is introduced which comprises approximately 10,500 samples with corresponding annotations. The dataset encompasses diverse environmental conditions and scenarios, facilitating the generalization ability of the model. Then, progressive enhancements to the YOLOV8S model are proposed, integrating a specialized focus module in the backbone to optimize feature extraction. Moreover, the convolutional block attention modules (CBAMs) are integrated at the feasible stages of the network to improve spatial and channel contexts for more accurate recognition, especially in complex scenes. Finally, an extensive empirical evaluation showcases the superiority of the proposed approach over 13 SOTA techniques, substantiated by meticulous benchmarking and qualitative validation across varied environments. The empirical findings and analysis of multiple factors such as model performance, size, and processing time prove that the suggested network displays impressive results. 

## Dataset Details
- **Sample Size:** Approximately 10,500 samples
- **Annotations:** Each sample is annotated to denote instances of falls and non-falls.
- **Diversity:** The dataset encompasses diverse environmental conditions and scenarios, facilitating robust real-time processing.
- **Format:** The dataset is provided in a structured format to enable easy use for detection and recognition frameworks.

## Usage
Researchers interested in fall detection research can utilize this dataset. The data will be soon available via the following Google Drive link: [Fall Detection Dataset](https://drive.google.com/drive/folders/1OvXAcmfMHdiCpcuAj-VCAMxNFi_p2_TD?usp=drive_link).
# Integration of Focus Module and CBAMs Integration
## Focus Module
The Focus module is used at the beginning of the backbone:
backbone:
  - [-1, 1, Focus, [64, 3, 2]]
## Convolutional Block Attention Modules (CBAMs) Integrations:
head:
  - [-1, 1, CBAM, [1024]]
  ...
  - [-1, 1, CBAM, [512]]
  ...
  - [-1, 1, CBAM, [256]]
  ...
  - [-1, 1, CBAM, [512]]

In the YAML file, CBAMs are integrated:
After the SPPF (Spatial Pyramid Pooling - Fast) layer
Before each upsampling operation in the feature pyramid
Before each downsampling operation in the feature pyramid
This strategic placement of CBAMs allows the network to refine and focus on the most relevant features at different scales and stages of the network, potentially improving the model's ability to detect objects accurately across various sizes and complexities.
The integration of Focus and CBAM modules in this YOLOv8 architecture aims to enhance the model's feature extraction and attention capabilities, potentially leading to improved object detection performance.

## Citation
If you use this dataset or our proposed approach in your research work, we kindly request you to cite our paper:

@article{khan2024visionary,
  title={Visionary vigilance: Optimized YOLOV8 for fallen person detection with large-scale benchmark dataset},
  author={Khan, Habib and Ullah, Inam and Shabaz, Mohammad and Omer, Muhammad Faizan and Usman, Muhammad Talha and Guellil, Mohammed Seghir and Koo, JaKeoung},
  journal={Image and Vision Computing},
  pages={105195},
  year={2024},
  publisher={Elsevier}
}

## Contact
For any issues regarding the dataset, please contact [habibkhan@ieee.org]. We welcome feedback and collaboration opportunities.
