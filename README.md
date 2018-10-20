# EC601_miniproject2

## target:
#### Use TensorFlow (or any tool you prefer) to recognize between two classes of objects.  These classes could be:
#### Cars and Trucks or Cars and SUVs
#### Roses and Sunflowers or Vegetables
#### You need to capture the images yourself and tag them.  You can use any Tagging system (e.g, https://hubs.ly/H0dktLv0 Neurala).  You #### need to design your own Training, Testing and Verification sets.
#### You need to compare between two different systems based on the literature review you did and/or reading material provided
#### Bonus:  Provide an API with example code for another developer to use your system


## Steps
### First step
#### download the pictures from the internet(Google Database)
#### label the pictures
#### update:
#### 1.download the pictures from kaggle:https://www.kaggle.com/jessicali9530/stanford-cars-dataset/kernels  the dataset Stanford Cars Dataset,but this dataset is used in mutiple classification, the csv files and pictures were divided into 196 classes, I have to modify the files and make it more fitable to our binary classification problem. 
#### 2.I set half of all the pictures to be training picture and testing for the remaining.
#### 3.In the original csv files, there are 196 classes, so I used google computer vision to recognize which is SUV, and then use the matlab and python(pandas and numpy) to modify the csv file, making all the pictures which is SUV to be class 1, and the other pictures are class 0. 

### Second step
#### use the vgg19 model which is used in airbus ship detection project to do transfer learning 
#### I just need to change the input pictures path and the final layers of the model to train the model.
