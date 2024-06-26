# Stuttering Classification and Therapy System
Our project is all about helping people who stutter. We've built a smart system that can tells the difference between stuttering and normal speech. Moreover, we've made it easy to get therapy tips based on what kind of stuttering you have. Our system offers a comprehensive approach to address this issue. 

## Project Overview

Here's a brief overview of the functionalities:
* Stuttering Detection: Utilizing cutting-edge speech analysis algorithms, our system accurately detects instances of stuttering in individuals' speech patterns.
* Classification into Main Types: Identified instances of stuttering are classified into main types such as prolongation, repetition, and blocks.
* Personalized Therapy Provision: For each identified type of stuttering, therapy resources in the form of audio recordings are provided.

Lets have a detailed look on the project's pipeline:

## Data Preprocessing Pipeline:

### Custom Stuttering Dataset: 
We created our won dataset manually which contains 815 audio samples categorized into four distinct folders representing different stuttering and non-stuttering speech types.

### Creating dataset:
Audios were mapped to a csv file containg two columns i.e audio file path and labels. The labels column contained the labels assigned to each type of audio. The audio file link column contains the drive file link of each audio.

### Sample Rate Adjustment: 
Audio samples are converted to a uniform sampling rate of 16,000 Hz for model compatibility.


### Feature Extraction: 
An auto feature extractor efficiently extracts relevant features from the audio data to facilitate model training.


### Dataset Splitting: 
The dataset is divided into training (90%) and testing (10%) sets for model training and evaluation.


## Stuttering Classification Model:

### Fine-Tuned DistilHubert: 
Leverages the pre-trained DistilHubert model from Hugging Face as the foundation, fine-tuned for the task of classifying stuttering in speech samples.


### Training and Optimization: 
The model undergoes training for 10 epochs, iteratively adjusting its parameters based on the training data to enhance its classification accuracy.


## Deployment and User Interface:

### Hugging Face Deployment: 
The trained model is deployed on the Hugging Face platform, ensuring accessibility for users worldwide. You can access the deployed model here: [https://huggingface.co/HareemFatima/distilhubert-finetuned-stutterdetection]

### Gradio User Interface: 
A user-friendly Gradio app interface allows users to interact with the system by uploading audio samples for stuttering classification. You can access the interface from here: [https://huggingface.co/spaces/arisha123/HareemFatima-distilhubert-finetuned-stutterdetection]


### Therapy Generation: 
We have incorporated the Massively Multilingual Speech (MMS) Text-to-Speech model from Facebook AI as a foundation for generating audio of therapy recommendations tailored to the user's stuttering type. While the integration of this model with the stuttering classification system is currently under development, users can leverage both models independently. The classification system provides insights into stuttering patterns, and users can then explore relevant therapy resources (text-based) for personalized support.
## Project Dependencies

### DistilHubert Model:
This project leverages the pre-trained DistilHubert model from Hugging Face for its foundation. You can find more information about DistilHubert here: DistilHubert model on Hugging Face:[https://huggingface.co/ntu-spml/distilhubert]

### Massively Multilingual Speech (MMS) Model:
We also leverage this model from Facebook AI to generate therapy recommendations. It allows the system to convert tailored therapy text into natural-sounding audio. You can find more information about it here:[https://huggingface.co/facebook/mms-tts-eng]


### FUTURE PROSPECTS


* Future Integration Plan: While the current system allows for independent use of the stutter detection model and the text-to-speech therapy recommendation model, our goal is to seamlessly integrate both models into a single application.
* Personalized Therapy: Tailor therapy recommendations to individual preferences and needs would improve the system’s functionality.
* Gathering More Data: Acquiring more diverse datasets for training is essential, considering the limited availability of annotated speech data online. Collaboration with hospitals and 
   speech therapy centers would be helpful in gathering real and authentic data.
* Accessibility and Scalability: Optimize resources and support multiple languages for broader user reach.
* Collaboration with Healthcare Professionals: Partner with experts to validate effectiveness and ensure alignment with established speech therapy practices.


## Framework versions
Transformers 4.40.1
Pytorch 2.2.1+cu121
Datasets 2.19.0
Tokenizers 0.19.1
T4 GPU
## Note: This project requires a GPU runtime environment for optimal performance. Please ensure that you have access to a GPU-enabled runtime environment before running the code.

## License

This project is licensed under the MIT.
