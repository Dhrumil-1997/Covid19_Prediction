## Cov CNN Web Application

Coronavirus disease (COVID-19) is a pandemic caused by the SARS-CoV-2 coronavirus, which has never been observed in humans before. COVID-19 is quickly spreading over
the world. COVID-19 can be found in people who have a lung infection. The Reverse transcription-polymerase chain reaction
(RT-PCR) assay is the gold standard for identifying COVID-19. RT-PCR tests, on the other hand, are in scarce supply. As a result, early diagnosis of the condition is challenging. X-rays
and other readily available techniques are frequently used to diagnose infections in the lungs. It has been established that X-ray scans may be utilised effectively for COVID-19 diagnosis.
However, a physical diagnosis of a large number of patient’s X-rays is a lengthy process. Radiologists can detect COVID-19 from X-ray images using a deep learning-based diagnostic
procedure. In order to identify illnesses from datasets, pretrained CNNs are routinely utilised. 

## Proposed Soution:
This work provides a CNN model with a parallelization technique for extracting features from
X-ray pictures by applying filters to the images in parallel.With precision, our suggested technique attempts to achieve improved accuracy and a lower loss rate. To accomplish so, the
parallelization approach is used to examine the accuracy and loss rates of three types of CNN: VGG-16, Xception, and ResNet50. Because VGG-16, Xception and ResNet50 models are pretrained,
they are imported straight from Keras. Furthermore, this article uses a Convolution Neural Network [CNN] to predict COVID-19 using a dataset: A public SARS-CoV-2 CT scan dataset of
COVID X-ray pictures and Non-COVID X-ray pictures.


## Proposed Method

### 1. VGG16
Used VGG16 network has 16 layers, as illustrated in Figure, with 13 convolutional layers with 3x3 filters and 2x2 max-pooling layers stacked on top.
The relu activation function is applied between these layers. After that, there are three fully connected layers that hold the
majority of the network’s parameters. Finally, the probability for each classification is calculated using a softmax function.

![alt text](https://raw.githubusercontent.com/Dhrumil-1997/Covid19_Prediction/new/main/)

### 2. ResNet50 
ResNet50 is a ResNet variation containing 48 Convolution layers, 1 MaxPool layer, and 1 Average Pool layer as shown
in the figure. There are total 3.8 x 109 floating point operations in it. ResNet is separated into five phases, the first
of which may be thought of as a pre-processing of INPUT, and the remaining four of which are made up of a Bottleneck
and have a more identical structure. We have an input stem with a 7x7 convolution, a 64-channel output, and a 2-stride
stride. Then there’s a 3x3 max pooling layer with a 2 stride. In this layer, we successfully reduce the input width and height
by four times while increasing the channel size to 64. We have a down-sampling block and residual blocks on stage 2 and following stages.

![alt text](https://raw.githubusercontent.com/Dhrumil-1997/Covid19_Prediction/new/main/)

### 3. Xception
In deep learning frameworks like TensorFlow and Keras, Xception is a depthwise separable convolution, also known as "separable convolution", that comprises of two operations:
1. A depthwise convolution, which is a spatial convolution conducted separately on each channel of an input, and
2. A pointwise convolution, which is a 1x1 convolution that projects the depthwise convolution’s output channels onto a new channel space.

Xception’s architecture consists of Depthwise Separable Convolution blocks + Maxpooling, all of which are coupled via shortcuts in the same way as ResNet implementations
are.The depthwise convolution is followed by a pointwise convolution, which is unique to Xception. This change is
justified by the fact that the inception module in Inception-v3 performs 1x1 convolutions before any nn spatial con-volutions.The data initially passes via the entry flow, then
eight times through the middle flow, and lastly through the exit flow. Batch normalisation is applied to all Convolution and SeparableConvolution layers. Here, the middle layer is the most basic layer, consisting 
of stacked blocks of ReLU + Separatable Conv layers that do not change the image’s dimensionality but instead accept the input from the entry flow, repeat the step eight times, and gives 
output to the exit flow. With the use of a maxpooling layer with a 3x3 filter and a strid of 2, entry and exit flows are employed to change the image’s dimensionality.


![alt text](https://raw.githubusercontent.com/Dhrumil-1997/Covid19_Prediction/new/main/)

## Experimental Setup

### 1. Dataset 
The ”SARS-CoV-2 CT Scan Dataset,” [3] which is perhaps the biggest freely accessible dataset of CT scans for
COVID-19 identification, was utilised. The dataset comprises a total of 2481 CT-scan pictures, including 1252 CT-scans
for SARS-Cov-2 infection positive patients and 1229 CT-scans for healthy individuals who are not infected. This
information was gathered from genuine patients at hospitals in Sao Paulo, Brazil. The goal of the dataset is to foster
the development of artificial intelligence-enabled methods for determining whether a patient is afflicted with the fatal virus
by analysing his or her scan.

## Results 
### 1. Django web interface

![alt text](https://raw.githubusercontent.com/Dhrumil-1997/Covid19_Prediction/new/main/)

### Evaluation Metrics

![alt text](https://raw.githubusercontent.com/Dhrumil-1997/Covid19_Prediction/new/main/)

## Limitation
False – Negative findings matter the most in this sort of
study because if someone has covid-19 and the system predicts
non-covid as a result, it can make matters worse. However,
we did not incorporate or analyze the ROC curves for the
models. In order to eliminate False – Negative outcomes, we
must examine the ROC curve and its behavior.
If we choose any image other than an X-ray image, the
algorithm will anticipate it as a covid positive. As a result,
we must impose some constraints in order to prevent this
circumstance from recurring in the future.

## Future Work
We want to enhance our outcomes as much as possible
by removing as many False-Negative discoveries as feasible.
A bigger dataset of Covid X-rays and X-rays of other lung
disorders can be used to improve this suggested approach. It
may also be used for IoT-related tasks, such as linking them
to an X-ray machine and predicting COVID-19 in real time.


## Authors
[Dhrumil Patel](https://github.com/Dhrumil-1997/)

[Dhruv Patel](https://github.com/dhruv2610/)


## Acknowledgement
We would like to extend our sincere gratitude to Dr. Garima Bajwa, our supervisor, for his assistance with our research study.

## How to run the code

We used django web framework for web integration.You need to serup django environment in your system or location where your project is located.

Please check the requirements.txt file for the pre-requiests for running the project.

Then go to cmd ... go to the located path of your project and run manage.py file.

Ex. path> pyhton manage.py runserver (Manage.py file locatated at "Covid_CNN_WebApp\cov_cnn_web")

This will host your website on localhost and now you can use the website.

