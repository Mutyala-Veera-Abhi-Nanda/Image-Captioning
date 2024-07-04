# Image Captioning Project

This project is for generating captions for images using VGG-16 and LSTM. The project involves preprocessing image data, training a model, and generating captions for new images.

## Dataset
The dataset used in this project is the COCO (Common Objects in Context) dataset, which includes images and their corresponding captions.
## Requirements

- Python
- numpy
- pandas
- tensorflow
- tqdm
- matplotlib
- seaborn

## Key Sections in the Notebook

#### Importing Dependencies

- Lists the necessary libraries and dependencies for the project, including standard Python libraries and specific packages like TensorFlow, Keras, and Pandas.

#### Dataset Exploration

- Dataset Source: The dataset used is from the COCO (Common Objects in Context) dataset.

- Dataset Details: Contains 82,783 image files.

- Data Organization: Images are stored in directories, and captions are loaded into a Pandas DataFrame containing image_id, image_path, and caption.

#### Data Preprocessing

###### Image Processing:

- Converts images to RGB format.

- Converts images into 1D vectors and normalizes them.

###### Text Processing:

- Converts captions to lowercase.

- Removes non-alphabetic characters and extra whitespace.

- Removes single characters from captions.

- Adds special tokens ("startseq" and "endseq") to each caption.

#### Evaluation:
- Generating captions for new images

## Results:

After training the model, you can evaluate its performance by generating captions for new images. The model's performance can be visualized using various evaluation metrics and plots.

## Example:

Here's an example of a generated caption:

![Screenshot (488)](https://github.com/Mutyala-Veera-Abhi-Nanda/Image-Captioning/assets/164295902/56a6efcc-4bdf-4f21-936b-1ba6e4397985)

Caption: "Man is playing tennis on the court."
