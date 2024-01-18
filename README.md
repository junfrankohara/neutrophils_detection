# Automated Detection and Quantification of Neutrophil Infiltration in Ulcerative Colitis Biopsies Using YOLOv5

![image](https://github.com/junfrankohara/neutrophils_detection/blob/main/readme.png)
Pipeline Overview

- This repository presents a pipeline for automated detection and quantification of neutrophil infiltration in ulcerative colitis biopsies. WSI is need to scanned at 40x magnification. A semantic segmentation model segmented the epithelium and lamina propria regions within the WSIs. These areas were then divided into 320x320 pixel (75x75μm) patches for processing by a neutrophil detection model using the YOLO v5 architecture. This model detected neutrophils within both regions, providing a total count adjusted per region (0.66mm^2) to predict pathological scores (PHRI = 0, PHRI = 1, PHRI ≥ 2, NHI ≤ 1, NHI = 2, NHI ≥ 3). Images highlighting the location of detected neutrophils were generated and automatically outputted as a PDF along with the predicted pathological scores. At low magnification, patches with neutrophils in the epithelium are marked in red, and those in the lamina propria are marked in blue. At high magnification, detected neutrophils in the lamina propria are indicated with red rectangles, and those in the epithelium with green rectangles.
- To run this code, you need to upload models and images to your Google Drive.
- The segmentation model and neutrophil detection models are available from "Releases"
- Environment Compatibility:
  - Python: 3.10.12
  - PyTorch: 2.1.0
  - segmentation_models_pytorch: 0.2.1
  - Pillow: 10.0.1

Note: The code has been tested and confirmed to work on Google Colaboratory with the above environment specifications.

Overview

- This repository introduces an automated pipeline designed for the detection and quantification of neutrophil infiltration in biopsy samples of ulcerative colitis. Our approach involves:

    - Whole Slide Imaging (WSI) Processing: Requires scanning at 40x magnification.
    - Semantic Segmentation: Utilizes a model to segment epithelium and lamina propria regions within the WSIs.
    - Neutrophil Detection: Implements YOLO v5 architecture to process 320x320 pixel (75x75μm) patches, detecting neutrophils in both segmented regions. The model provides a total neutrophil count, adjusted per region (0.66mm²), and predicts pathological scores (PHRI = 0, 1, ≥2; NHI = ≤1, 2, ≥3).
    - Visualization: Generates images highlighting detected neutrophils, marked in distinct colors for easy identification (red for epithelium, blue for lamina propria at low magnification; red and green rectangles at high magnification for lamina propria and epithelium, respectively). Outputs include a PDF report with detected locations and pathological scores.

- Setup and Execution

    - Models and Images: Upload required models and images to your Google Drive.
    - Availability: The segmentation and neutrophil detection models can be downloaded from the "Releases" section of this repository.

Environment Compatibility

Ensure the following software versions for optimal compatibility:

    - Python: 3.10.12
    -PyTorch: 2.1.0
    - segmentation_models_pytorch: 0.2.1
    - Pillow: 10.0.1

Note: The code has been rigorously tested on Google Colaboratory and confirmed to work efficiently with the above environment specifications.
