# Transfer_Learning_Deep_Learning
I gonna use pretrained model to use it on my data
# First I gonna store size of image shape in variable, then I gonna load pretrained model and store it as "classifier"
# I change "input_shape" adding additional (3,)) to my stored variable (224, 224), so now it look like this (224, 224, 3)
# Now I gonna show image of "goldfish" using "Image.open" and resize it into my new "IMAGE_SHAPE" it is good plotted
# Then I gonna scale my image like always deviding it of 255 and puting it into numpy array, when I check shape it show me my new "IMAGE_SHAPE"
# I also gonna change shape using "numpy newaxis" and when I check new shape it show one more dimension
# I gonna check if everything is working good with my model, so I use my model to predict "gold_fish" variable in new shape and check results
# And "numpy argmax" return me index of prediction
# Now I gonna download tensorflow dataset using "keras.utils.get_file", origin will be url of file and I gonna save it in directory
# Then I gonna prepare my data first creating empty list for labels, then I open the file and put it into my list 
# And I check predictions from my model on the new dataset, so I take my list and check predicted label index 
# Then I gonna download flower images, so I use "keras.utils.get_file" on "dataset url", unzip it and store in directory 
# Then I check if it is saved and I can import "pathlib" to convert my data using "pathlib.Path" on my dataset it is very useful
# I put my directory into a list and use "pattern technique glob" to look at first five images
# Now I check the length of the list to see how many images I have and then I create list of roses images
# I use "Image" to open rose image of index[1] and I also check tulips by creating list of them and showing one image 
# I organize first lists of my images and then their indexes into numerical values and check first rose image 
# Now I use "cv2.imread" of first image of rose to check the shape of image, I need to resize and scale my image 
# So I use "cv2" and resize method "(224,224)" this will be new shape of my image, now I gonna do this on all my images 
# I create two empth lists, one for resized images and secound for flower labels of flower names
