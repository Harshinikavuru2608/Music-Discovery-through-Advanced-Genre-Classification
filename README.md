# Music-Discovery-through-Advanced-Genre-Classification
This project uses machine learning to classify music into genres based on audio features. The repository contains three Jupyter notebooks that detail the steps of data processing, feature extraction, and classification.

## Notebooks

### 1) Genre Classification.ipynb

This notebook contains the Genre Classification Model, which operates on a curated dataset of five music genres. Features are standardized using a scaler for consistent future predictions. The scaler and the trained Random Forest model are saved for future use.

- **Model file**: `genreclassificationmodel.joblib`
- **Scaler file**: `scaler2.joblib` 

### 2) Feature Extraction.ipynb

This notebook uses librosa and music21 libraries to extract basic audio features from the dataset. These features alone are not sufficient for genre classification, so an LSTM model is trained to predict more complex features.

- **Model file**: `audiofeatures.keras`
- **Scaler file**: `scaler.joblib` 

### 3) New Audio Classification.ipynb

This notebook demonstrates the classification of new audio files. It uses the librosa library for basic acoustic features and music21 for additional musical data. The extracted features are merged and used as input to the LSTM model for feature prediction. The final array of features is processed by the scaler and the Random Forest model to classify the genre in real-time.

- **Feature Extractor Model file**: `audiofeatures.keras`
- **Genre Classifier Model file**: `genreclassificationmodel.joblib`
- **Scaler files**: `scaler2.joblib` and `scaler.joblib`

## Setup
Before running the notebooks, make sure to install the required Python packages. You can install all the dependencies listed in `requirements.txt` using the following command:

pip install -r requirements.txt

## Docker
This project can be run using Docker, which simplifies the setup and ensures compatibility across systems. First, install Docker on your system if it is not already installed.

To use the pre-built Docker image, pull it from DockerHub and run it using the provided commands. Make sure to replace the file path with the path where your audio file is located:

Commands:
- docker pull harshinikavuru26/genreclassification:v1
- docker run -it -v <path_to_your_audio_file_directory>:/data harshinikavuru26/genreclassification:v1

After running the Docker container, enter the names of your audio files when prompted:
- Please enter the path to your .mp3 file: <your_audio_file>.mp3
- Please enter the path to your .mid file: <your_midi_file>.mid

