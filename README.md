# emotion_detector
#IN THIS IPYTHON FILE 7 EMOTIONS OF HUMEN ARE DETECTED
#THE CLASSES ARE [ANGRY,DISGUST,FEAR,HAPPY,NEUTRAL,SAD,SURPRISE]
---> fro this detection I am using convolution neural networks with keras
---> here i put 4 continue layers again and again for better results
--->i am using imagedaragenrator class of keras to actually manuplate the image of input
in this manuplation i am converting to gray then changing the size and adding a third dimention for neural network
for adding third dimention i am using numpy function extend dims.

after this i am making the model in this i am defining convolution neural network in this i am putting these parameters:
 1)conv2D :will create a convolution layer for model
 2)activation : defining activation function(relu)
 3)batch normalization : normalize activation of previous layer for each batch
 4)maxpooling2D : taking the maximum value from a  defined window size of full matrix
 5)dropout: randomly select neurons and ignore during training (0.5/half)
  
 here after defining function the filters were not enough so i am adding them again and testing for this
 2nd time : 64 filters
 3rd time : 128 filters
 4th time : 256 filters
 then flatting them and then dence connected layers for connecting all the neurons.
 doing it again but without flatten layer because we have done it in previous layer
 and then putting activation layerwith softmax
 

After prapring the model i am also putting 3 main things with callback class of keras
these things are following :
  1) checkpoint : it will detect the validation loss and minimize it. it is more likely a booster for neural network
  2)early stopping : it helps to stop training earlier than usual the point behind using this is take the tracking of validation loss from checkpoint and if it has minimized and all the weights are allready restored then simply stop the trainining it helps a lot when we need our model quickly as possible
  3) reduce learing rate : Let's assume our model is in traing part and we find there is no improvment in learning rate, In this case we can reduce the learning rate. This function reduce it by a factor 2-10.
  
  
  after these three important steps we can compile our model for this i am calling the compile function from my model class which is sequential class of keras
  then fitting the train and validation sets by model.fit_generator
  and we are done with our model
  
  for testing the model i also provide a live mode where you can detect the emotion by running that
  and also a code which will detect emotion of saved image from your pc
