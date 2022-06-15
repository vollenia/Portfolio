# Project 1: Data Science<br/>_- Cable News Network (CNN) -_
In the digital world of today, data is produced at an ever-increasing pace. There are many available datasets already to perform analysis on and using a pre-made dataset eliminates the need of identifying data sources and collecting the data oneself. This is, without a doubt, a benefit in the majority of cases but can also be a constraint. It becomes more convenient to lean towards a pre-made dataset than going the distance and collecting one’s own data, with all the extra steps that are involved. There seems to be no need to re-analyze "popular" datasets for the n<sup>th</sup> time, while the amounts of freely accessible data and therefore, the number of interesting insights to gather, seem countless. The question is, _what do you want to know_?

In the case of this project, it was of interest to find data that is real, recent and has an impact on our everyday life. Many very different things may come to mind, depending on the person. However, for the majority of us, our lives don't take place in isolation and we are therefore, impacted by the events surrounding us. For this reason, it is of interest to inspect the medium that informs us about the events happening all around us, _the news_.
Cable News Network (CNN) has been selected as the source of this type of data.


## [1.1 Scraping the Website<br/>(Collecting/Pre-Processing/Storing + Accessing)](https://github.com/vollenia/web_scraper-CNN_news)
The goal of this project is to automatically collect data from the [CNN website](https://edition.cnn.com/) for a specific time window and store it in a database which can then be efficiently searched for particular contents.

Main Steps:
* Going to the CNN website
* Navigating the website structure to identify webpages for all articles within the specified time window
* Collecting _publishing date_, _title of the article_, _url_, _name of the author_, _short summary of the article_ and the _articel itself_ from the relevant webpages by parsing their HTML structure
* Preparing data to follow specific constraints and storing it as a database in XML format with the information enclosed within the corresponding tags
* Accessing data within the XML database by tag-keyword pairs in order to enable efficient search for articles covering specific contents

## [1.2 Analyzing Publications for 2021<br/>(Post-Processing/Analyzing/Visualizing)](https://github.com/vollenia/data_analysis_CNN_news)
The goal of this project is to analyze the data collected in [1.1](https://github.com/vollenia/web_scraper-CNN_news) for the year of 2021. The focus of this analysis lies not on the contents of the articles themselves but on the meta information of these articles. It is, however, possible and of interest to extend this analysis onto the contents in the future.

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/data_analysis_CNN_news/main/images/pub_year.png" width="100%" />
</p>

Covered aspects:
* Publications throughout the year (seen above)
* The year viewed as a workweek
* Distribution of authorship 
* Close-up on individual months

## [1.3 Creating an Interactive Dashboard<br/>(Post-Processing/Analyzing/Visualizing + Enabeling Interactivity)](https://github.com/vollenia/interactive_dashboard_CNN_news)

The goal of this project is to analyze the data collected in [1.1](https://github.com/vollenia/web_scraper-CNN_news) for the year of 20211. While the analysis performed in [1.2](https://github.com/vollenia/data_analysis_CNN_news) delivered plots that could only be presented as a static image, this project is aimed at creating interactive plots and bundling them together into a dashboard that can be viewed and interacted with in the browser.

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/interactive_dashboard_CNN_news/main/media/pub_year.gif" width="100%" />
</p>

Covered aspects:
* Publications throughout the year / months
* Distribution of authorship for the year / months
* The year viewed as a workweek
* Density of publications for individual months contrasted against the whole year

The dashboard consists of two main pages where the first page displays the Year view and the second the Months view with their corresponding plots. The user can switch freely between the two pages using the widget located under Settings in the sidebar. 

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/interactive_dashboard_CNN_news/main/media/dash_main.gif" width="100%" />
</p>

While the Year view consists of three plots, the Months view allows for displaying the same three plots for each of the individual months. The months can be navigated through the widget located at the top of the Months page.

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/interactive_dashboard_CNN_news/main/media/dash_months.gif" width="100%" />
</p>

# Project 2: Deep Learning<br/>_- Emotion Recognition -_
Due to technological advances of the past decades, it has become common to communicate with robots in order to receive information.
However, humans are still aware of talking to a machine and not to another human being. The main weakness of such machines that prevents a seamless interaction, besides the processing errors in regard to the specifc task, is the lack of emotional communication.
Since humans convey their emotional state with seemingly every word they say, it becomes immediately noticeable when this layer of communication is missing in a conversation. Therefore, emotion recognition, as the frst step, can be considered the key for affective communication in the human-machine interaction.

In inter-human affective communication the acoustic and visual modalities play a central role for the expression and perception of emotions. While for the acoustic modality the prosody, the manner in which something is said, is significantly more important than the actual content, the visual modality is dominated by facial expressions. Both modalities represent complementary signals which are processed in conjunction by the human brain.

Taking inspiration from the inter-human affective communication, an audio-visual model for emotion recognition is created in this project.

## [2.1 Emotion Recognition from Speech](https://github.com/vollenia/emotion_recognition_from_speech)
* Features: Mel log filter banks extracted via the Kaldi extension for torchaudio
* Neural Network: CNN style architecture adapted to time continuous data
* Training/evaluation: 6-fold cross validation approach

## [2.2 Emotion Recognition from Face Detections](https://github.com/vollenia/emotion_recognition_from_face_detections)
* Features: Selection of greyscaled face detections extracted via Dlib's HOG frontal face detector
* Neural Network: CNN architecture with selected frames passed in as channels 
* Training/evaluation: 6-fold cross validation approach

## [2.3 Emotion Recognition from Facial Landmarks](https://github.com/vollenia/emotion_recognition_from_facial_landmarks)
* Features: Normalized distances computed from facial landmark coordinates extracted via Dlib's shape predictor
* Neural Network: FCNN architecture 
* Training/evaluation: 6-fold cross validation approach

## [2.4 Emotion Recognition from Audio-Visual Features](https://github.com/vollenia/emotion_recognition_audio-visual)
* Features: Mel log filterbanks + grayscaled face detections
* Neural Network: Model-level fusion of architectures from [1.1](https://github.com/vollenia/emotion_recognition_from_speech) and [1.2](https://github.com/vollenia/emotion_recognition_from_face_detections) 
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
  <img src="https://raw.githubusercontent.com/vollenia/emotion_recognition_audio-visual/main/images/mm_confusion_matrix_label.jpg" width="70%" />
</p>

Ultimately, the audio-visual model delivers an overall performance increase of **8.57%** over the audio baseline and **10.30%** over the video baseline.

# [Project 3: Natural Language Processing<br/>_- Text Generation -_](https://github.com/vollenia/text_generation)
The goal of this project is to automatically train a language model given a random text and generate new text by utilizing this language model.

Main steps:
* Splitting training data (text) into individual tokens (words / punctuation marks)
* Creating n-gram representations (words and their context of n-1 preceding words)
* Storing n-gram representations in form of a language model
* Generating new token sequences with the language model
* Converting token sequences into text

Some generation results when trained on a random text:
* _"Dear Celia, but I will bring you word, good Mistress Anne, yourself must break my oath, to hide the sun dance. Hark, in me what strange, that wouldst thou have me?"_
* _"I am heart-burned an hour, and, for want of rain, I am, necessity commands me name myself attach thee for a hot January."_
