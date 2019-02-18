# GAN_FACES
## Requirements
The basics requirements to run this project is to have installed:
Python 3, jupyter notebook, Tensorflow and Numpy.
 
## Description
This project was divided in 6 main steps:
* 1: Reading the CelebA dataset
* 2: Building inputs to the Networks
* 3: Building the Discriminator Network 
* 4: Building the Generator Network
* 5: Putting all together
* 6: Training
* 7: Viewing Results

#### Reading the CelebA dataset
In this part we load the CelebA dataset with the helper script and we see some images. The 
images are already preprocessed, so the values of the images are in range of -0.5 and 0.5 with a size of 28x28.

#### Building inputs to the Networks
Here i make a function to build the placeholder inputs of the generator and discriminator
networks and also a placeholder for the learning rate. 

#### Building the Discriminator Network
In this part is defined a function that creates the discriminator network. It has four convolutional layers of 64, 128, 256 and 512 filters respectively with size 5x5, all these layers are initialized with the xavier initialization, have a leaky relu activation and a dropout. The last layer of the network is a fully conected layer with sigmoid activation. It is defined with a discriminator variable scope so we can pass only the discriminator train variables for the optimizer.

#### Building the Generator Network
In this part is defined a function that creates the generator network. It has one fully connected layer and four transpose convolutional layers of 256, 128, 64 and out_channel_dim(in this case we are working with RGB images so out_channel_dim = 3) filters respectively with size 5x5, all these layers are initialized with the xavier initialization, have batch normalization, have a leaky relu activation and a dropout(except the last one), the last one has a tanh activation. It is defined with a generator variable scope so we can pass only the generator train variables for the optimizer.

#### Putting all together
Here i'm defining the losses functions and the optimizers.

#### Training
In this part i'm defining all the hyperparameters and training both networks for only 3 epochs(it took 25h of training) and got some good results

#### Viewing results
Below we can see the evolution of the generator images throught the epochs and some sampling from it.

**Begining of first epoch**
![alt text](https://github.com/cfcv/GAN_Faces/blob/master/photos/gan_face_0.png)

**Middle of first epoch**
![alt text](https://github.com/cfcv/GAN_Faces/blob/master/photos/gan_face_1.png)

**Second epoch**
![alt text](https://github.com/cfcv/GAN_Faces/blob/master/photos/gan_face_2.png)

**Last epoch**
![alt text](https://github.com/cfcv/GAN_Faces/blob/master/photos/gan_face_3.png)
