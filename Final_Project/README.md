# INFO_7390_Final_Project

## Data source
Since data is too larger(4+G), we can only provide the source link: https://www.kaggle.com/c/rsna-pneumonia-detection-challenge/data

## Compare with other model
we test the model with ssd_mobilenet_v1 with our dataset, the code is zipped in the hub too.

## Research Idea
Our Project aims to detect Pneumonia via radiographs of lung. The output of our work is to build a model to classify the disease as well as to predict boundary box of the evidence area. Our dataset is from Kaggles whose format is DICOM.
The work we have done is: build an object detection model, reformat dataset to adjust input of the model, do EDA of dataset, training model with different hyper-parameters, combine models with different backbone component together to give a better output.

## Research Evaluation
1 Compare the methods with other kaggles works
2 Evaluate the classification loss of both training and validation data.
3 Evaluate boundary boxes’ location parameters’ regression loss for training and validation.

## Difference between other Kagglers
We use two different backbone of Retinanet to train the model and give an output combining weighted average of boundary boxes. Other kagglers may also use Retinanet but they either change the inside of the Retinanet or just use it. Others use Faster RCNN, Mask RCNN,YOLOv3 and so on.

## Scope of the project
The scope is Research on Internet to find a best Object Detection Model Concept and build Retinanet model, reformat dataset to adjust input of the model, do EDA of dataset, training model with different hyper-parameters, combine models with different backbone component together to give a better output, other things including bug fixing and Tensorflow GPU running configuration.

## Code explanation
Before every code section, we write an explanation, just check them in Data_Preparation_and_EDA.ipynb and Training Model and output result.ipynb files.

## Citations
Citations are in the python code, just check them in Data_Preparation_and_EDA.ipynb and Training Model and output result.ipynb files.

## Run Code Tips for NEU COE student
1.    Install Python3.6, Tensorflow/Tensorflow-gpu1.9+,Anaconda,keras on your computer, install retinanet according to the official github: https://github.com/fizyr/keras-retinanet
2.    Convert the dataset into jpg format using pydicom if your dataset is in DICOM format
3.    Convert the csv file into standard format as retinanet github says. https://github.com/fizyr/keras-retinanet
4.    Put your data and code in well structured directory.
5.    Open anaconda run jupyter notbook and run the project code in order.
6.    If you want to compare the model with ssd_mobilenet_v1, you can use the zip file we provided.

## Conclusion
We got a total loss of 0.28 for regression on predicting boundary boxes and we got a loss of 0.2364 on classification on best model snapshot after training with Retinanet. And we got a loss of 0.43 on regression and loss of 0.38 on classification on validation data.
We set the threshold of score for Pneumonia is 0.3 and there may be several boxes generated for one picture so we apply weighted average method to combine them together to generate one final output boundary box. The output possibility over 0.5 is not very often so we need to do further improvement on model in the future.
After running ssd_mobilenet_v1 model with our dataset, the loss on classification is still at high level(about 1.362) after 100 iterations and loss on regularization is still about 1.883 high, we need a long term to train the model to give a better performance.

## License

Copyright 2018 Junyuan Bao, Mohao Li

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


