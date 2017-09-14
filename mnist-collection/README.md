# MNIST Examples

---

## Overview

The examples listed below demonstrate several deep learning algorithms on MNIST
dataset, which is one of the most popular image classification datasets in the
machine learning community. The MNIST dataset will be automatically downloaded
when running any of the examples.

---

## Classification task (`classification.py` and `classification_bnn.py`)

This example demonstrates the training of hand-written digits classification on
MNIST dataset. The convolutional neural network takes 28x28 pixel grayscale
images as input and outputs the predictions of 10-way classification.

When you run the example by

```
python classification.py

```

you will see the training progress in the console (decreasing training and
validation error). The model will eventually reach around 1% validation error
rate.

Training can be dramatically sped up by using a CUDA GPU when the
nnabla_ext-cuda extension is installed. Run the above command with `-c
cuda.cudnn` option to let NNabla use GPU acceleration.

```
python classification.py -c cuda.cudnn
```

After the learning completes successfully, the results will be saved in
"tmp.monitor/". In this folder you will find model files "\*.h5" and result
files "\*.txt".

The classification example provides two choices of neural network architectures
to train, LeNet and ResNet. You can select it with the `-n` option. For more
details see the source code and the help produced by running with the `-h`
option.

You can also try training of various types of binary neural network
classification models on MNIST dataset.

```
python classification_bnn.py [-c cuda.cunn] [-h|--help]
```


## Deep Convolutional GAN (`dcgan.py`)

This example shows how to learn and generate images using Generative
Adversarial Networks demonstrated on MNIST dataset. The image generator neural
network takes 256 dimension random vectors as inputs, and outputs 28x28 pixel
generated images. The discriminator neural network takes 28x28 pixel images as
inputs, and outputs the score of whether the inputs are real or generated.

Reference: "Unsupervised Representation Learning with Deep Convolutional
Generative Adversarial Networks". https://arxiv.org/abs/1507.00677

```
python dcgan.py [-c cuda.cudnn] [-h|--help]
```

After the learning completes correctly, the results will be saved in
"tmp.monitor.dcgan". In this folder you will find the discriminator model files
"discriminator_\*.h5", the generator model files "generator_\*.h5", log files
"\*.txt" and some generated images in "Fake-images".