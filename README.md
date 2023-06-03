# Transfer_Learning_Deep_Learning
I gonna use pretrained model to use it on my data
# First I gonna store size of image shape in variable, then I gonna load pretrained model and store it as "classifier"
# I change "input_shape" adding additional (3,)) to my stored variable (224, 224), so now it look like this (224, 224, 3)
# Now I gonna show image of "goldfish" using "Image.open" and resize it into my new "IMAGE_SHAPE" it is good plotted
# Then I gonna scale my image like always deviding it of 255 and puting it into numpy array, when I check shape it show me my new "IMAGE_SHAPE"
# I also gonna change shape using "numpy newaxis" and when I check new shape it show one more dimension
# I gonna check if everything is working good with my model, so I use my model to predict "gold_fish" variable in new shape and check results
