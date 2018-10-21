# EC601_miniproject2

## target:
#### Use TensorFlow (or any tool you prefer) to recognize between two classes of objects.  These classes could be:
#### Cars and Trucks or Cars and SUVs
#### Roses and Sunflowers or Vegetables
#### You need to capture the images yourself and tag them.  You can use any Tagging system (e.g, https://hubs.ly/H0dktLv0 Neurala).
#### You need to design your own Training, Testing and Verification sets.
#### You need to compare between two different systems based on the literature review you did and/or reading material provided
#### Bonus:  Provide an API with example code for another developer to use your system


## Steps
### First step
#### download the pictures from the internet(Google Database,kaggle)
#### label the pictures
#### update 1:
#### 1.download the pictures from kaggle:https://www.kaggle.com/jessicali9530/stanford-cars-dataset/kernels  the dataset Stanford Cars Dataset,but this dataset is used in mutiple classification, the csv files and pictures were divided into 196 classes, I have to modify the files and make it more fitable to our binary classification problem. 
#### 2.I set half of all the pictures to be training picture and testing for the remaining.
#### 3.In the original csv files, there are 196 classes, so I used google computer vision to recognize which is SUV, and then use the matlab and python(pandas and numpy) to modify the csv file, making all the pictures which is SUV to be class 1, and the other pictures are class 0. 

#### update 2:
#### processing the data:
#### in the training dataset there are 8144 images. I set 70% of them as training set and the rest 30% to shift images which can increase the accuracy of the model. as the validation set. and using the ImageDataGenerator to shift images which can increase the accuracy of the model. 

### Second step: 2 different models

#### 1.VGG19 MODEL
#### Use the vgg19 model which is used in airbus ship detection project to do transfer learning 
#### Just need to change the input pictures path and the final layers of the model to train the model.
#### compare to normal vgg19 model. I have delete the original prediction layer and add a 1*1 FL after other layers. Because we just need to handle a binary classification problem and this will increase the training speed. However, at the same time, it is undoubtedly that will lower the accuracy of the prediction.

#### 2.SMALLER VGG MODEL
#### After using the vgg19 model, learning from it's basic theory, I build a smaller vgg model by using Tensorflow. the main feature of it are as follows:
#### a)using the 3*3 conv layer to increase the depth
#### b)using the 'max' pooling layer to minimize the array
#### c)using the full connected layer before the final classification layer
#### d)using the 'relu' function as the activation function.

##### introduction to the model:
##### the layers of my model are as follows:
##### CONV(32,(3,3))->RELU->POOL('MAX')->DROPOUT(0.25)->CONV(64,(3,3))->RELU->POOL('MAX')->DROPOUT(0.25)->CONV(128,(3,3))->RELU->POOL('MAX')->DROPOUT(0.25)->FL(128)->DROPOUT(0.5)->SOFTMAX


