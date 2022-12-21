# I. Data Analytics

## Project 1: _Cycling Complaints from Baden-Württemberg<br/>(R & Tableau)_

Events of the recent years have led society to re-think many aspects of our day-to-day lives. One of these aspects is the way we commute. In Germany, it has become increasingly popular to rely on cycling for short-distance commutes. Having close family members and friends committed to this lifestyle, is cause for regular discussions about the advantages and disadvantages of being a cyclist, especially in the city. While all seem to agree on the advantages, the problems vary since not every cyclist takes the same routes. Therefore, it becomes difficult to get an objective picture of the situation that would not only be beneficial for family discussions but also for city and state officials when prioritizing changes.

Fortunately, the SWR (Südwestrundfunk), a public broadcaster local to the south-western states of Germany, initiated a campaign to gather data on this topic. The campaign, fittingly titled [#besserRadfahren](https://www.swr.de/radfahren/besser-radfahren-im-suedwesten-106.html) "#betterCycling", encouraged cyclists from all around the south-west to participate and report problems they are faced with while on the road.

The resulting dataset covers the states of Baden-Württemberg and Rheinland-Pfalz. However, this project focuses on Baden-Württemberg only.

## [1.1 Transforming the Dataset & Analyzing Complaints from Stuttgart<br/>(Post-Processing/Analyzing/Visualizing)](https://github.com/vollenia/cycling_complaints_bw_swr)

The goal of this project is to process and analyze data collected by the SWR in context of their #besserRadfahren campaign.  The pre-processing and short analysis focus on the state of Baden-Württemberg and in particular on its capital city, Stuttgart.

Main Steps:
* Transforming the dataset to extract additional information from unstructured data columns
* Creating a clean dataset for Baden-Württemberg
* Performing an analysis for Stuttgart

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/cycling_complaints_bw_swr/main/images/1_stuttgart_vs_bw.png" width="100%" />
</p>

Covered aspects:
* Stuttgart vs. Baden-Württemberg (seen above)
* Inner city districts of Stuttgart
* Progression of complaints over time in Stuttgart 
* Five largest cities in Baden-Württemberg

## [1.2 Creating an Interactive Dashboard](https://public.tableau.com/app/profile/vollenia/viz/Radfahren_BW_2021/DashboardBW)

The goal of this project is to create an interactive dashboard using the clean dataset created in [1.1](https://github.com/vollenia/cycling_complaints_bw_swr). Presenting the data in this way, will make the information and therefore, the insights accessible to a wide range of people while also allowing them to tailor it to their personal needs.

[Tableau Public](https://public.tableau.com/app/discover), a free visualization plattform, was selected for this task. While missing some features from its payed service, it still provides a relatively wide range of tools for creating and hosting interactive dashboards.

The dashboard is comprised of four elements. First, a map of Baden-Württemberg consisting of three individual layers (regions, zip codes and points of interest) that can be toggled on and off. Second, a sunburst chart that displays the distribution of main an sub-categories for the map selection. Third, a bump-chart representing the progression of the main categories in regard to their rank of importance for the map selection. Fourth, a legend that simultaneously acts as a filter for the main categories.


<div class='tableauPlaceholder' id='viz1671652561519' style='position: relative'>
  <noscript>
    <a href='#'>
      <img alt='Dashboard BW '
           src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ra&#47;Radfahren_BW_2021&#47;DashboardBW&#47;1_rss.png'
           style='border: none' />
    </a>
  </noscript>
  <object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> 
    <param name='embed_code_version' value='3' /> 
    <param name='site_root' value='' />
    <param name='name' value='Radfahren_BW_2021&#47;DashboardBW' />
    <param name='tabs' value='no' />
    <param name='toolbar' value='yes' />
    <param name='static_image' 
           value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ra&#47;Radfahren_BW_2021&#47;DashboardBW&#47;1.png' /> 
    <param name='animate_transition' value='yes' />
    <param name='display_static_image' value='yes' />
    <param name='display_spinner' value='yes' />
    <param name='display_overlay' value='yes' />
    <param name='display_count' value='yes' />
    <param name='language' value='de-DE' />
  </object>
</div>                

## Project 2: _Cable News Network (CNN)<br/>(Python)_
In the digital world of today, data is produced at an ever-increasing pace. There are many available datasets already to perform analysis on and using a pre-made dataset eliminates the need of identifying data sources and collecting the data oneself. This is, without a doubt, a benefit in the majority of cases but can also be a constraint. It becomes more convenient to lean towards a pre-made dataset than going the distance and collecting one’s own data, with all the extra steps that are involved. There seems to be no need to re-analyze "popular" datasets for the n<sup>th</sup> time, while the amounts of freely accessible data and therefore, the number of interesting insights to gather, seem countless. The question is, _what do you want to know_?

In the case of this project, it was of interest to find data that is real, recent and has an impact on our everyday life. Many very different things may come to mind, depending on the person. However, for the majority of us, our lives don't take place in isolation and we are therefore, impacted by the events surrounding us. For this reason, it is of interest to inspect the medium that informs us about the events happening all around us, _the news_.
Cable News Network (CNN) has been selected as the source of this type of data.

## [2.1 Scraping the Website<br/>(Collecting/Pre-Processing/Storing/Accessing)](https://github.com/vollenia/web_scraper-CNN_news)
The goal of this project is to automatically collect data from the [CNN website](https://edition.cnn.com/) for a specific time window and store it in a database which can then be efficiently searched for particular contents.

Main Steps:
* Going to the CNN website
* Navigating the website structure to identify webpages for all articles within the specified time window
* Collecting _publishing date_, _title of the article_, _url_, _name of the author_, _short summary of the article_ and the _articel itself_ from the relevant webpages by parsing their HTML structure
* Preparing data to follow specific constraints and storing it as a database in XML format with the information enclosed within the corresponding tags
* Accessing data within the XML database by tag-keyword pairs in order to enable efficient search for articles covering specific contents

## [2.2 Analyzing Publications for 2021<br/>(Post-Processing/Analyzing/Visualizing)](https://github.com/vollenia/data_analysis_CNN_news)
The goal of this project is to analyze the data collected in [2.1](https://github.com/vollenia/web_scraper-CNN_news) for the year of 2021. The focus of this analysis lies not on the contents of the articles themselves but on the meta information of these articles. It is, however, possible and of interest to extend this analysis onto the contents in the future.

<p align="center">
  <img src="https://raw.githubusercontent.com/vollenia/data_analysis_CNN_news/main/images/pub_year.png" width="100%" />
</p>

Covered aspects:
* Publications throughout the year (seen above)
* The year viewed as a workweek
* Distribution of authorship 
* Close-up on individual months

## [2.3 Creating an Interactive Dashboard<br/>(Post-Processing/Analyzing/Visualizing + Enabeling Interactivity)](https://github.com/vollenia/interactive_dashboard_CNN_news)

The goal of this project is to analyze the data collected in [2.1](https://github.com/vollenia/web_scraper-CNN_news) for the year of 2021. While the analysis performed in [2.2](https://github.com/vollenia/data_analysis_CNN_news) delivered plots that could only be presented as a static image, this project is aimed at creating interactive plots and bundling them together into a python dashboard that can be viewed and interacted with in the browser.

<video src="https://user-images.githubusercontent.com/83287775/173880951-1129555a-c055-46a2-b1f9-69679810c9f9.mov" controls="controls" width="100%">
</video>

Covered aspects:
* Publications throughout the year / months
* Distribution of authorship for the year / months
* The year viewed as a workweek
* Density of publications for individual months contrasted against the whole year

The dashboard consists of two main pages where the first page displays the _Year_ view and the second the _Months_ view with their corresponding plots. The user can switch freely between the two pages using the widget located under _Settings_ in the sidebar. 

<video src="https://user-images.githubusercontent.com/83287775/173898878-79f9a429-39ac-427e-8e5e-9eb20f4e13b5.mov" controls="controls" width="100%">
</video>

While the _Year_ view consists of three plots, the _Months_ view allows for displaying the same three plots for each of the individual months. The months can be navigated through the widget located at the top of the Months page.

<video src="https://user-images.githubusercontent.com/83287775/173898977-9c4b8a90-f4d0-4832-8cb5-c37f61794500.mov" controls="controls" width="100%">
</video>

# II. Deep Learning

## Project 1: _Emotion Recognition<br/>(Python)_
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

# III. Natural Language Processing

## [Project 1: _Text Generation_<br/>(Python)](https://github.com/vollenia/text_generation)
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
