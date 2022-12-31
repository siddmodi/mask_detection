https://user-images.githubusercontent.com/63842900/210129408-65babeb2-eaca-4e73-8ac3-e3c25c027471.mp4

# Face Mask detection

• This project architecture has divided in 2 parts

a) Train our VGG16 model with dataset of peope wearing mask and people no wearing mask, by
using transfer learning in such a way that i remove the last layer of vgg16 and freeze the weights of
all the layers and add last layer accoding to our problem as classifying people with mask and no
mask.

b) I pass our video file to that model and it will classify them on top of the bounding box over the
face which is forming using the haarcascade_frontalface_default xml file as a face detection model,
this will return the coordinates of the bounding box around the face which we can use to create a
box.

• I feed features to our vgg16 are in shape of (number of data points ie. images, 224,224, 3) , here i
also standardize our features by dividing pixels by 255.

• Here i use adam optimizer, binary_crossentroyp as a loss function and accuracy as metrics and
train for 5 epochs.

• We reshape our video frame input as (1,224,224,3) to pass in vgg16 model
