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

#### Tokenizer Initialization and Fitting

- Tokenizer: A tokenizer updates its internal vocabulary based on the text data in the captions, creating a mapping of words to indices.

- Vocabulary Size: Determined by the length of the tokenizer's word index plus one.

- Maximum Sequence Length: The length of the longest caption in the dataset.

#### Data Splitting

Unique images are split into 85% for training and 15% for validation.

#### Model Architecture

###### 1. Feature Extractor (VGG-16):

- VGG-16 is used to extract features from images.

- The top layer of VGG-16 is excluded for convenience.

- Pretrained weights for VGG-16 are loaded.

- VGG-16's architecture is summarized, highlighting layers like convolutional layers, pooling layers, and the final dense layer.

###### 2. Sequence Model (LSTM):

- An LSTM network processes the tokenized captions.

- An embedding layer maps word indices to dense vectors.

- An LSTM layer processes the embedded sequences.

###### 3. Decoder Model:

- Combines features from the VGG-16 and LSTM models.

- Uses fully connected (dense) layers to predict the next word in the sequence.

#### Training Process

- CustomDataGenerator class handles batch generation for training.

- Implements methods like on_epoch_end for shuffling data and __getitem__ for generating batches.

- Extracts features for each image, tokenizes captions, and generates input-output pairs for training.

#### Implementation Steps

###### Feature Extraction:

- Extracts precomputed image features from VGG-16 using pickle.

- Matches training and testing images with extracted features.

###### Model Training:

- Defines and compiles the model.

- Trains the model using the training set and validates it using the validation set.

- Utilizes callbacks like ModelCheckpoint and EarlyStopping for efficient training.

## Example:

Here's an example of a generated caption:

![Screenshot (488)](https://github.com/Mutyala-Veera-Abhi-Nanda/Image-Captioning/assets/164295902/56a6efcc-4bdf-4f21-936b-1ba6e4397985)

Caption: "Man is playing tennis on the court."
