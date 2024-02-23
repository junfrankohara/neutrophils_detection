# Automated Detection and Quantification of Neutrophil Infiltration in Ulcerative Colitis Biopsies Using YOLOv5

![image](https://github.com/junfrankohara/neutrophils_detection/blob/main/readme.png)


# Overview

- This repository introduces an automated pipeline designed for the detection and quantification of neutrophil infiltration in biopsy samples of ulcerative colitis. Our approach involves:

    - Whole Slide Imaging (WSI) Processing: Requires scanning at 40x magnification.
    - Semantic Segmentation: Utilizes a model to segment epithelium and lamina propria regions within the WSIs.
    - Neutrophil Detection: Implements YOLO v5 architecture to process 320x320 pixel (75x75 μm) patches, detecting neutrophils in both segmented regions. The model provides a total neutrophil count, adjusted per region (1 mm²), and predicts pathological scores (PHRI = 0, 1, ≥2; NHI = ≤1, 2, ≥3).
    - Visualization: Generates images highlighting detected neutrophils, marked in distinct colors for easy identification (red for epithelium, blue for lamina propria at low magnification; red and green rectangles at high magnification for lamina propria and epithelium, respectively). Outputs a PDF report with detected neutrophils and pathological scores.

# Setup and Execution

- Models and Images: Upload required models and images to your Google Drive.
- Availability: The segmentation and neutrophil detection models can be downloaded from the "Releases" section of this repository.

# Environment Compatibility

Ensure the following software versions for optimal compatibility:

    - Python: 3.10.12
    - PyTorch: 2.1.0
    - segmentation_models_pytorch: 0.2.1
    - Pillow: 10.0.1

Note: The code has been rigorously tested on Google Colaboratory and confirmed to work efficiently with the above environment specifications.
