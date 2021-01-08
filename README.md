# Dog-Breed-Classifier
Classification algorithm to detect dog breed out of jpg-photos

Dog Breed Classifier
Classification of dog breeds using CNNs (Udacity Nanodegree Datascience Program)
I. Introduction 
Predicting to what class an object belongs is an essential work for us to do. What kind of animal did we just see on TV? Was the part, that we just produced okay from quality-point-of-view? Did the supplier send us the correct parts?
In Machine Learning (ML), classification tasks are one of the main fields of activity. We can use the advantages of ML for our classification purposes, which are for example (but not exclusively):
Fast processing and real time predictions, using consistent criteria
Data input from unlimited resources
Automation
Simplification and easy pattern-detection

This ML-task from Udacity's Data-Scientist-Nanodegree-Program will use Convolutional Neural Networks (CNN) to identify dog breeds from photos given as JPG-file.
II. CRISP-DM
The Cross Industry Standard Process for Data Mining (CRISP-DM) is a widely used open standard process model used for Data Mining. It basically consists out the steps listed below and, hence, is used in this Classification task.
II.1 Business Understanding
We are having thousands of example files that will help us to identify humans and dogs out of a photo. Furthermore we will not only differentiate between dogs and humans. After this differentiation-process we will also clearly identify which dog breed we just saw and -here is where the fun begins- we'll also enter a look-alike-contest between humen and dogs. In order to achieve this, we'll have to go the following steps:
Step 0: Import Datasets
Step 1: Detect Humans
Step 2: Detect Dogs
Step 3: Create a CNN to Classify Dog Breeds (from Scratch)
Step 4: Use a CNN to Classify Dog Breeds (using Transfer Learning)
Step 5: Create a CNN to Classify Dog Breeds (using Transfer Learning)
Step 6: Write a Classification-Algorithm 
Step 7: Test this Algorithm

II.2 Data Understanding
Our datasets differentiates between 133 dog categories including 8351 dog images in total.
There are 6680 training dog images, 835 validation dog images, and 836 test dog images in total, that allow the ML-algorithm to learn on its own.
Furthermore we'll use 13234 total human image in order for the ML-algorithm to learn differentiating between human and dogs.
II.3 Data Preparation
Human face detectorThe human face detector uses a pre-trained-model from Open CV (https://github.com/opencv/opencv/tree/master/data/haarcascades) in order for making things easier for us.
For the detection of doc breeds we use the Keras ResNet50-model in Python taking TensorFlow as backend (as next step to pre-process the data).
Using tensorsFurthermore we need to convert the images in a way, that the Keras-ResNet50-model can work with it.
Predictions with ResNet50Finally we can write a dog-detector-function in Python that will help us identifying, if a picture from a dog is used by returning True or False given a picture.
Dog-Detector-FunctionII.4 Modelling
After these pre-processing-steps we'll create a CNN that serves our needs, hence, we could use it to predict dog-breeds.
In a first step of the modelling process we'll create the tensors needed for (still) pre-processing the data, it means we rescale the images by dividing every pixel in every image by 255.
Preprocessing-tensorsAfter this we can implement our sequential model for a plain stack of layers where each layer has exactly one input tensor and one output tensor:
Model ArchitectureII.5 Evaluation
Now its time to train the model, see how it improves, and, do some final testing.
1st Training and TestingAs you can see we gradually improve the model and finally reach a test accuracy of approximately 3%, which is not to bad at this stage (actually 1% would already be a success).
With the use of transfer learning we can further improve our model. After some additional iterations of the model we reach a test accuracy of approximately 68%. 
Final testingThe model is now ready for implementation / deployment. Hence, let's try to identify dog breeds.
II.6 Deployment
In order to show the prediction-results of the model, please see the following 6 examples.
Dog 1Detecting dog as Anatolian shephard dog - wrongDog 2Detecting dog as Labrador retriever - correctDog 3Detecting dog as Clumber spaniel - correctAs expected 2 out the 3 dogs where classified correctly. Now let's see what happens to the human example pictures.
Human 1Human 1 as Cardigan welsh corgiCardigan welsh corgiHuman 2Human 2 as NewfoundlandNewfoundlandHuman 3Human 3 as Cardigan welsh corgiCardigan welsh corgiII.7 Outlook / Perspectives of the model
We now have an implementation process at hand, how we could model a CNN for picture classification. Not only dog breed-identification is possible. 
Imaging an Automotive production where you could identify quality problems with a web app on your telephone just by taking a picture of a car / car part. Does this car / car part satisfy your (per-defined) quality needs? This question could be answered in an instant after shooting the photo.
You could also easily control, if your supplier sent the right parts with the right quality by automatically taking photos at the beginning of your production line, without using any employee of yours. The algorithm would do all the work for you. 
It sounds scary for the quality employee who would lose his work, but maybe he's the one developing the model in the future.
II.8 Ways for improvement
The use of Deep Learning Models for picture classification requires a lot of data and also a well set-up Computer system with larger GPU-power. Given an optimized system we could build up an optimized Deep Learning Model. However, the purpose of this exercise was to learn how to work with Deep Learning Models. Hence, I learned my lesson and know what's the next learning step for me ;-)
P.S.: The code of the model can be found on https://github.com/Jingle1999/Dog-Breed-Classifier
