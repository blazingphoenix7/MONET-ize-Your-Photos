# MONET-ize-Your-Photos

# Generating Monet with CycleGAN: Bridging AI and Impressionist Art

## Project Overview

In the quest to blend artificial intelligence with the artistic nuances of Impressionist painting, this repository presents a profound experiment: replicating Claude Monet's painting style through advanced generative adversarial networks (GANs). This project, rooted in a Kaggle challenge, employs a sophisticated CycleGAN architecture to not only generate Monet-style images but also explore the broader implications of AI in creative industries.

## Why Monet?

Claude Monet's work is renowned for its radical engagement with light and color, which challenged traditional artistic expressions and laid the groundwork for Impressionism. Our AI model attempts to capture this revolutionary spirit, offering a computational perspective on Monet's techniques and potentially expanding the creative toolkit offered by machine learning.

## Technical Details

### CycleGAN Architecture

Unlike traditional GANs, CycleGANs facilitate image-to-image translation without paired training examples, making them ideal for tasks where matching input-output pairs are unavailable. This project utilizes dual generators and discriminators to handle the bidirectional transformation between photographs and Monet-style paintings.

#### Components
- **Generators (G<sub>photo</sub>, G<sub>Monet</sub>)**: Transform photographs to paintings and vice versa. These are built using a modified U-Net architecture, which is specifically designed to better capture and recreate the stylistic elements of Monet’s artwork.
- **Discriminators (D<sub>photo</sub>, D<sub>Monet</sub>)**: Evaluate the authenticity of generated images against real ones. These discriminators use a PatchGAN design, which classifies images on a patch level and has shown great success in tasks that involve style transfer.

#### Innovative Features
- **Reflective Padding**: Used in the generators to avoid border artifacts, ensuring that the generated images do not have distorted edges, thus maintaining the aesthetic quality.
- **Instance Normalization**: Applied in both generators and discriminators to help the model generalize across different sets of images and stabilize training.
- **Residual Connections**: Incorporated within the U-Net architecture to preserve image content through deeper network layers, enhancing the cycle consistency attribute of the model.

### Advanced Training Techniques

- **Adaptive Gradient Clipping**: This technique is utilized to prevent exploding gradients, a common issue in training GANs that can lead to model instability.
- **Learning Rate Decay**: Implemented to fine-tune the training process as the models converge, improving the quality of generated images.
- **Cycle Consistency Loss with Identity Mapping Loss**: Ensures that each generator can reconstruct the original image, which is crucial for maintaining the identity between transformations.

## Model Evaluation

### Metrics
- **Fréchet Inception Distance (FID)**: Measures the quality of generated images by comparing the distance between feature vectors calculated by InceptionNet for real and generated images.
- **Memorization-informed FID (MiFID)**: Enhances FID by incorporating a memorization term, crucial for assessing whether the model merely replicates training data or genuinely 'understands' Monet's style.

## Usage

Detailed instructions are provided for setting up the environment, preparing the dataset, and running the training process. By following these guidelines, users can not only replicate this project's results but also experiment with modifying the architecture or training approach to explore new creative dimensions.

1. **Clone this repository.**
2. **Download the dataset from ->** [Kaggle Monet Dataset](https://www.kaggle.com/competitions/gan-getting-started/data).
3. **Unzip all the data directories.**
4. **Set up your environment:**
    - Ensure you have Python and the necessary packages installed as listed in requirements.txt. You can also run ```pip install requirements.txt``` in the directory where the cloned repository and datasets are stored. 
    - A TPU is recommended for training the models efficiently.
5. **Run the notebooks:** The Jupyter notebooks will guide you through the process of training the models and visualizing the results. Make sure to set the **GCS_PATH** variable to the directory where the cloned repository and datasets are stored. 


## Contributions and Collaboration

We invite contributions from fellow researchers, developers, and art enthusiasts. Whether it is improving the existing model, experimenting with different datasets, or conceptualizing new uses of AI in art, your insights are valued.

## License

This project is available under the MIT license, allowing for both academic and commercial use.

---

This README aims not just to explain but to inspire. By merging the technical prowess of AI with the expressive power of art, we open a dialog on the potential of new technologies to transform our understanding and interaction with the world. Let's continue this exploration together and see what new realities we can construct.
