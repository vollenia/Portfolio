# Portfolio
Portfolio of my projects

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

## Results

Emotion Class | Audio | Pixelvalues | Landmarks
------------ | ------------- | ------------- | -------------
Angry | 43.75% | **49.23%** | 46.88%
Happy | 53.42% | **65.44%** | 64.06%
Neutral | 38.06% | **43.90%** | 32.28%
Sad | **50.00%** | 19.72% | 27.78%

Emotion Class | Audio | Pixelvalues | Landmarks | Audio-Visual
------------ | ------------- | ------------- | ------------- | -------------
Angry | 43.75% | 49.23% | 46.88% | **56.92%**
Happy | 53.42% | 65.44% | 64.06% | **69.59%**
Neutral | 38.06% | **43.90%** | 32.28% | 38.81%
Sad | 50.00% | 19.72% | 27.78% | **54.17%**

While this margin was 13.93% in
the video baseline, it increased to 16.08% in the audio-visual model, resulting
in all classes falsely classied as neutral having an almost equal distribution of
samples. Ultimately, the audio-visual model delivers an overall performance
increase of 8.57% from the audio baseline and 10.30% from the video baseline.

