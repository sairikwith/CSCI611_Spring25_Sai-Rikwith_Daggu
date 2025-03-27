# Style Transfer - Assignment 4  

This repository contains an implementation of the neural style transfer algorithm, inspired by the paper *"A Neural Algorithm of Artistic Style"* by Gatys et al. The project leverages a pre-trained VGG19 network to extract content and style features from images, optimizing a target image to merge the content of one with the artistic style of another.  

## Overview  
Neural style transfer (NST) is a deep learning technique that applies the artistic style of one image (e.g., a painting) to the content of another (e.g., a photograph). This implementation follows the method outlined in the original paper, using VGG19 to extract relevant features and optimize the output image accordingly.  

## Usage  

### Running Locally  
1. Clone this repository:  
   ```bash
   git clone [https://github.com/sairikwith/CSCI611_Spring25_Sai-Rikwith_Daggu.git]
   cd CSCI611_Spring25_Sai-Rikwith_Daggu
   git checkout Assignment_4
   ```
2. Run the Jupyter notebook:  
   ```bash
   jupyter notebook CSCI 611 Assignment 4.ipynb
   ```
3. Follow the steps in the notebook to:  
   - Load content and style images  
   - Extract features using VGG19  
   - Define content and style loss functions  
   - Optimize the target image  

### Running in Google Colab  
- Upload the `CSCI 611 Assignment 4.ipynb` file to Google Drive  
- Open it using Google Colab  
- Enable GPU acceleration (`Runtime > Change runtime type > Hardware accelerator > GPU`)  
- Run all cells in the notebook  

## Implementation Details  
This implementation includes the following components:  
- **Feature Extraction**: Uses a pre-trained VGG19 network to extract content and style representations.  
- **Gram Matrix Calculation**: Computes the style representation by measuring correlations between features.  
- **Loss Functions**: Defines content loss and style loss to guide the optimization.  
- **Optimization**: Uses the Adam optimizer to iteratively update the target image.  

## Hyperparameter Tuning  
Experiments were conducted to analyze the impact of different hyperparameters:  

- **Style Weight**: Determines the balance between content preservation and stylization.  
  - Lower values (1e4) retain more content details.  
  - Higher values (1e8) produce more stylized images.  
- **Layer Weights Distribution**: Affects how different levels of style are emphasized.  
  - Early layers contribute to larger style patterns.  
  - Later layers refine finer details.  
- **Number of Iterations**: Controls the level of refinement.  
  - 1500 iterations: Quick results with less detail.  
  - 2000 iterations: A good balance between speed and quality.  
  - 2500 iterations: More refined details but longer runtime.   
- **Initial Image**: Affects the final output.  
  - Starting from the content image provides reliable results.  
  - Starting from random noise leads to more creative variations.  

## Results  
The report includes visual examples demonstrating how different hyperparameters influence the final output. The default settings (style weight = 1e6, 2500 iterations, learning rate = 0.001) strike a balance between maintaining content and achieving artistic stylization.  

## Author  
**Sai Rikwith Daggu(012147396)**  
