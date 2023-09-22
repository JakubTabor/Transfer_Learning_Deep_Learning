 Now I gonna describe i details how function transfer model

# First i load pretrained model and save it as "feature_extractor_model"

* Then i use "hub.KerasLayer" and put inside first my model, then the shape and disable the training, so I froze it during the training
* I save it as "pretrained_model_without_top_layer" and I gonna use it in keras model  

# Now I gonna create keras model to train it on my flowers dataset, with help of pretrained model 

* So first i stop number of classes as variable, then I create keras model and put as a layer "pretrained_model_without_top_layer"
* Then I put also Dense layer with number of classes and look at summary of this model 
* We can see that the transfer model was trained on over 2 000 000 elements, so we can expect that it can handle the task very good
* We can also see that in summary there are Trainable and Non-trainable params, it means that froze of layer works 
* And our data for training include 6,405 elements

# Now I compile my model with optimizer as adam, then my loss will be "SparseCategoricalCrossentropy" and metrics in accuracy
* Then I train my model and set number of epochs at 5, I save history of my training as "history 2" to plot it later
* I can see that perforamnce of my model is very good, with five epochs i get very good accuracy
* And my model is very simple, I don't need to build model with many layers to get nice accuracy

# After evaluation I get accuracy 0.88, which is very good, I print it with a pretty way
* Then I print keys to see what I can plot on graph 
* And I plot first accuracy of my model, I see growing trend which is a good sign 
* Then I plot loss history during training and testing and see downward trend, so everything is alright

# I check also some predictions, previously converting predicted numbers into max. arguments
* Transfer model perform so good in comparison with my previous model which was much more complicated
* It is very powerful tool to use in case of big and complicated dataset, it save a lot of time and computation power

**MY MODEL**

* This is deeper description of my transfer learning model, with more analyze and plot graphs

# First I load my data like previous, I save url, then get file with flower photos, save it in directory and unzip 
* Then I import pathlib and change my data using "pathlib.Path", now its ready for operations
* Next I sort my data, I create one dictionary for flower photos and change all images in one category into list 

# Now I create dictionary for labels of my flowers types, so I assign number for every type
* Then I call my object to check if everything works good and now its time to resize my images

# Now I create function which task is to get acces to images in my dict and then resize every image and append ready images and their labels into lists
* So first i create two lists, then make for loop on flower names and images in my dictionary with acces to items 
* I use "cv2.imread" to get access to images and save this operation as "img"
* Then I use "cv2.resize" and put "in variable" and then new sage of my all images
* And I fill my two lists with my images of new size and their labels, I change this list into numpy array

# Now when my data is preprocessed i can "train_test_split" and get train and test set
* I also scale my X_train and X_test to use it in training and evaluation 

# I plot three first images to get idea of my data, previous resize them 
* I check shape of image, it will be input shape in my model, and also check the shape after flattening, looks huge

# Now I gonna build model with keras Sequential, so I start with passing first Convolutional 2D layer
* I set number of filters, so feature detectors at 32, then "kernel_size " will be 3 by 3, activation will be relu and I pass "IMAGE_SHAPE" 
* And add additional third dimension and now I have shape of image, then I use "MaxPooling2D" after layer to reduce computation
* It gonna take  the maximum value over an input window

# Then I pass another Convolutional 2D layer, this time with 64 filter detectors, number of filters is hyperparameter
* And i pass pull layer also after this Conv2D layer, then I flatten all convolutional layers to fit into shape of my neural network
* After flattening i pass two Dense layers, I don't need to set big number of neurons because my convolutional layers, will do much of the work

# And I add Dropout layers after every Dense layer for better final accuracy, it will drop pass value of neurons 
* I put last Dense layer with 5 neurons, because I have 5 classes and activation sigmoid 

# Now I can compile my model, with optimizer as adam, loss as "sparse_categorical_crossentropy" because my output is direct value
* If i convert it into categorical i use "categorical_crossentropy"
* I want to plot later performance of my model, so I save training process as history and add additional "validation_split" to see it during the training
* My data is complicated and I don't use data augmentation so i get after evaluation 0.63 which is still not that bad 
* And I save model evaluation as scores, I also print with a pretty way using metrics and model score is percents 

# Then I print history to check what parameters i can plot on graph
* First i plot accuracy during training and accuracy growth during testing my model performance
* And look how my accuracy inprove with each epoch 
* I also plot loss of my model, during training and testing, I see downward trend with each epoch, so its good

# My model its not perfect, but we can notice the right trend on the graph
* I also check predictions with predictions of my model and true values, I need to change predicted values to argmax, to be i right range

**TRANSFER LEARNING EXPLANATION**

# Transfer_Learning_Deep_Learning
* I gonna use pretrained model to use it on my data

# First I gonna store size of image shape in variable, then I gonna load pretrained model and store it as "classifier"
* I change "input_shape" adding additional (3,)) to my stored variable (224, 224), so now it look like this (224, 224, 3)
* Now I gonna show image of "goldfish" using "Image.open" and resize it into my new "IMAGE_SHAPE" it is good plotted

# Then I gonna scale my image like always deviding it of 255 and puting it into numpy array, when I check shape it show me my new "IMAGE_SHAPE"
* I also gonna change shape using "numpy newaxis" and when I check new shape it show one more dimension
* I gonna check if everything is working good with my model, so I use my model to predict "gold_fish" variable in new shape and check results
* And "numpy argmax" return me index of prediction

# Now I gonna download tensorflow dataset using "keras.utils.get_file", origin will be url of file and I gonna save it in directory
* Then I gonna prepare my data first creating empty list for labels, then I open the file and put it into my list 
* And I check predictions from my model on the new dataset, so I take my list and check predicted label index 

# Then I gonna download flower images, so I use "keras.utils.get_file" on "dataset url", unzip it and store in directory 
* Next I check if it is saved and I can import "pathlib" to convert my data using "pathlib.Path" on my dataset it is very useful
* I put my directory into a list and use "pattern technique glob" to look at first five images
* Now I check the length of the list to see how many images I have and then I create list of roses images

# I use "Image" to open rose image of index[1] and I also check tulips by creating list of them and showing one image 
* I organize first lists of my images and then their indexes into numerical values and check first rose image 
* Now I use "cv2.imread" of first image of rose to check the shape of image, I need to resize and scale my image 
* So I use "cv2" and resize method "(224,224)" this will be new shape of my image, now I gonna do this on all my images 

# I create two empth lists, one for resized images and secound for flower labels of flower names
* Then i make for loop for flower name and image in my flower dictionary and I do it for every image 
* I gonna use method "imread from cv2" on image variable and store it as img, then I use resize mthod on that img variable and give shape (224,224)
* Now in first list will append resized images and in the second labels of this images I change this list into numpy arrays and store as X and y

# Next I can import "train_test_split" and get train and test set I also now scale my images "X_train / 255 and X_test / 255"
* I check the shape and its all right, now I gonna show thre images, then I use my model to get predictions on this images and get label of prediction

# Now I get url of pretrained model, set one layer and put shape of it, "trainable = False" means that it will be not trained 
* I gonna create new model which will include "pretrained model" and output layer with number of flower classes 
* I get summary to look at my model`s structure, it looks that my pretrained model was trained on 2,257,984, when my data include only 6,405

# Then I compile my model with "optimizer as adam, loss as SparseCategoricalCrossentropy and metrics as accuracy" then I set number of epochs at five
* With only five epoch I get accuracy more than (0.9), this is the power of transfer learning 
* After evaluating my model i get (0.88) accuracy, this is very good because i don't need so much computing power to get good accuracy
