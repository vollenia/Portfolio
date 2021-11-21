# Portfolio
This is a portfolio of my most interesting projects. The motivation behind this is to put an overview of all projects in one place while simultaneously providing additional context.

# Project 1: Emotion Recognition
Due to technological advances of the past decades, it has become common to communicate with robots in order to receive information.
However, humans are still aware of talking to a machine and not to another human being. The main weakness of such machines that prevents a seamless interaction, besides the processing errors in regard to the specifc task, is the lack of emotional communication.
Since humans convey their emotional state with seemingly every word they say, it becomes immediately noticeable when this layer of communication is missing in a conversation. Therefore, emotion recognition, as the frst step, can be considered the key for affective communication in the human-machine interaction.

In inter-human affective communication the acoustic and visual modalities play a central role for the expression and perception of emotions. While for the acoustic modality the prosody, the manner in which something is said, is significantly more important than the actual content, the visual modality is dominated by facial expressions. Both modalities represent complementary signals which are processed in conjunction by the human brain.

Taking inspiration from the inter-human affective communication, an audio-visual model for emotion recognition is created in this project.

## [1.1 Emotion Recognition from Speech](https://github.com/vollenia/emotion_recognition_from_speech)
* Features: Mel log filter banks extracted via the Kaldi extension for torchaudio
* Neural Network: CNN style architecture adapted to time continuous data
* Training/evaluation: 6-fold cross validation approach

## [1.2 Emotion Recognition from Face Detections](https://github.com/vollenia/emotion_recognition_from_face_detections)
* Features: Selection of greyscaled face detections extracted via Dlib's HOG frontal face detector
* Neural Network: CNN architecture with selected frames passed in as channels 
* Training/evaluation: 6-fold cross validation approach

## [1.3 Emotion Recognition from Facial Landmarks](https://github.com/vollenia/emotion_recognition_from_facial_landmarks)
* Features: Normalized distances computed from facial landmark coordinates extracted via Dlib's shape predictor
* Neural Network: FCNN architecture 
* Training/evaluation: 6-fold cross validation approach

## [1.4 Emotion Recognition from Audio-Visual Features](https://github.com/vollenia/emotion_recognition_audio-visual)
* Features: Mel log filterbanks + grayscaled face detections
* Neural Network: Model-level fusion of architectures from 1.1 and 1.2 
* Training/evaluation: 6-fold cross validation approach

## Results Overview

Emotion Class | Speech | Face Detections | Facial Landmarks | Audio-Visual (Speech + Face Detections)
------------ | ------------- | ------------- | ------------- | -------------
Angry | 43.75% | 49.23% | 46.88% | **56.92%**
Happy | 53.42% | 65.44% | 64.06% | **69.59%**
Neutral | 38.06% | **43.90%** | 32.28% | 38.81%
Sad | 50.00% | 19.72% | 27.78% | **54.17%**

When comparing the audio-visual model's performance against the baselines, the model delivers signifcantly increased performance for three of the
four classes. The only exception is _neutral_ where the best results can be found in the video baseline model. However, despite the decreased performance in regard to _neutral_, it should be noted that the margin between the correct classifcations and the class with the highest percentage of false classifcations increased. This resulted in all classes falsely classifed as _neutral_ having an almost equal distribution of samples and the number of correct classifications being almost twice as high, as can be seen in the confusion matrix for the audio-visual model:

<p align="center">
  <img src="https://github.com/vollenia/emotion_recognition_audio-visual/blob/main/images/mm_confusion_matrix_label.jpg" width="70%" />
</p>

Ultimately, the audio-visual model delivers an overall performance increase of **8.57%** over the audio baseline and **10.30%** over the video baseline.

# [Project 2: Text Generation](https://github.com/vollenia/text_generation)
The goal of this project is to automatically train a language model given a random text and generate new text by utilizing this language model.

Main steps:
* Splitting training data (text) into individual tokens (words / punctuation marks)
* Creating n-gram representations (words and their context of n-1 preceding words)
* Storing n-gram representations in form of a language model
* Generating new token sequences with the language model
* Converting token sequences into text

Some generation results when trained on a random text:
* "Dear Celia, but I will bring you word, good Mistress Anne, yourself must break my oath, to hide the sun dance. Hark, in me what strange, that wouldst thou have me?"
* "I am heart-burned an hour, and, for want of rain, I am, necessity commands me name myself attach thee for a hot January."

# Project 3: CNN Website

## [3.1: Web Scraping - CNN Website](https://github.com/vollenia/web_scraper-CNN_news)
The goal of this project is to automatically collect data from the CNN (Cable News Network) website for a specific time window and store it in a database which can then be efficiently searched for particular contents.

Main Steps:
* Going to the CNN website
* Navigating the website structure to identify webpages for all articles within the specified time window
* Collecting _publishing date_, _title of the article_, _url_, _name of the author_, _short summary of the article_ and the _articel itself_ from the relevant webpages by parsing their HTML structure
* Preparing data to follow specific constraints and storing it as a database in XML format with the information enclosed within the corresponding tags
* Accessing data within the XML databse by tags/keyword pairs in order to enable efficient search for articles covering specific contents
