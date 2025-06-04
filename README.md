# Dog Emotion YOLO Detection Model With StableDiffusion Generated Images

## Introduction

Given that accurately interpreting dog behaviors visually is challenging due to subtle behavioral cues, YOLO's robust image detection capabilities offer significant potential to automate and enhance this process. Benefits of being able to classify a dog’s emotional state can lead to products and services in many different industries from consumer products, shelter monitoring, to safety.


The problem involved generating images of dogs exhibiting various emotions using the Stable Diffusion model (RealVisXL V5.0), which produces realistic and varied representations. The images are generated with varying fur lengths, cues, backgrounds, and coat colors.
I was unable to find a good dataset of appropriately licensed dogs categorized by emotions. While a neural network is unfamiliar to a dogs‘ emotional cues, we have been training dogs for years and can accurately predict emotional states by behaviour cues like a tucked tail. Therefore, we can leverage this knowledge in the dataset generation in order to teach our how to classify the same cues.
For a lack of time, given there are 1000 images per class, I developed code to automatically label the images with the appropriate bounding box. My original approach involved boxing the entire image, however, I soon realized that my model was learning to box the entire image and not detecting the positions of animals. Therefore, in order to solve this problem, I added randomness to the centering and sizing of the generated bounding box. This helped my model achieve better results.

### Image Generation
Images were synthesized using Stable Diffusion, ensuring a diverse and comprehensive dataset depicting distinct emotional states. This step aimed to provide robust training data capable of capturing subtle emotional variations.

Data Tagging and Cleaning
Images generated were systematically tagged according to the emotional state exhibited by the dogs. Data was cleaned to exclude unclear or ambiguous images to improve overall data quality and model performance. Bounding boxes were generated around the center of the image with slight random noise to improve model performance. 

## Neural Network Implementation

#### Models

A baseline YOLO model was trained to validate the feasibility of the detection and classification task, establishing initial benchmarks for performance metrics such as accuracy, precision, recall, and mAP (mean Average Precision).
The YOLO architecture was selected for its strengths in rapid and accurate image detection and classification, essential for real-time applicability.
Images were prepared in YOLO-compatible format, defined through a structured dataset YAML file.

Hyperparameters including learning rate, epochs, batch size, and image dimensions were systematically selected.
Model Refinement 

Multiple iterations of YOLO models were implemented with adjustments in hyperparameters, augmented datasets, and enhanced tagging procedures. Each iteration included performance evaluation against the baseline to quantify improvements.
Hyperparameter tuning was performed iteratively.

Performance metrics, such as precision and recall, guided model selection and refinement.
Overall, the project demonstrated that deep learning, specifically YOLO, effectively classifies dog emotions from images, significantly outperforming simpler baseline methods. Future improvements could involve increasing dataset diversity and employing advanced augmentation techniques to enhance generalizability further.
