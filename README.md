# Malaria-Detector

The dataset contains 2 folders - Infected and Uninfected

It contains 27,558 images

This dataset is taken from the official NIH website: https://lhncbc.nlm.nih.gov/publication/pub9932

NOTE:
We are dealing with large group of real image files hence it is difficult to fit into memory as a numpy array
So we will feed these images into our model in Batches

Everything is explained in jupyter notebook but here is the overview of how the project went:

Set up the directory and check whether or not we have all the folders required: 

1) Seperate folders for train and test

2) Each folder should contain sub folders for each class: infected folder and uninfected folder

Now set up the paths for test and train data as shown in the jupyter notebook

We have to make sure that all the images should be in the same size in order for a CNN to train on

Steps involved:

1) Load and set up the paths for both train and test data

2) Visualize a sample cell_image using matplotlib

3) Trying to figure the common image shape for a CNN model to train on by calculating the average of the dimensions of all the images

4) Preparing Data for the Model:

    a) Using Tensorflow's built-in tools to automatically process the data, generating a flow of batches from a directory, and image            manipulation
    
    b) Image Manipulation using ImageDataGenerator to perform transformations like: Rotation, re-sizing, scaling
    
5) Create a model

6) Training the model

    a) Create two generators each for test and train data
    
    b) Now let the train and test images flow from directory through ImageDataGenerator object 
    
    c) Fit the model with the generator
    
7) Model Evaluation

    a) Predict a test image with the help of created model through generator
    
NOTE:

1) Instead of getting class results we will get the probablities 

2) Now we can put the probability threshold value according to the requirement for each class in the real world which indirectly helps in dealing with Type-1 and Type-2 errors

    pred_prob = model.predict_generator(test_image_gen)
    
    predictions = pred_prob > 0.5    ..... we can change this threshold value



    
