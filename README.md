# Hand Gesture Classification using CNN

## What I Built

I built a hand gesture classification model using CNN. The model classifies three different hand gestures:
- Peace Sign
- Thumbs Up
- Open Palm

I chose this idea because it was simple for me to collect my own dataset while still allowing me to learn the complete workflow. The dataset was created by me instead of using an existing dataset. 

The main goal of this project was not just to get a high accuracy but to understand how image classification models are trained and how different hyperparameters affect their performance.

## Dataset
This dataset consists of 90 images in total, with 30 images for each gesture class.
The three classes are:
- Peace Sign
- Thumbs Up
- Open Palm

The images were taken using a phone camera. Small variations in hand position and angles were included. Before training, all images were resized to 128 x 128 pixels so that the model can process them consistently. The dataset was split into training and validation sets using an 80:20 ratio.

## Model Architecture
The model consists of two convolution layers followed by max pooling layers. These layers help the model learn visual features from the images.
After feature extraction, the output is flattened and passed through a dense layer. A dropout layer is also included to reduce overfitting. Lastly, a softmax output layer predicts one of the three gesture classes.
While building the model, I learned that convolution layers act as feature detectors. The early layers learn simple patterns like edges, while deeper layers learn more complex patterns related to the hand shape and gestures.

## Experiments Performed

### Experiment 1 - Baseline CNN

I first trained a baseline CNN model using standard settings. This experiment is a reference point for all later experiments. The model achieved very high training accuracy but the validation accuracy was significantly lower. This suggested that the model was overfitting the training data.

### Experiment 2 - Data Augmentation

To reduce overfitting, data augmentation was used by applying small rotations, shifts, zooming and horizontal flipping. 
My expectation was that the model would see more variation and learn more general features instead of memorizing specific images. The training accuracy decreased compared to the baseline model because the learning task became more difficult. The validation accuracy did not improve significantly.

### Experiment 3 - Increased Dropout

The baseline experiment showerd signs of overfitting so I increased the dropout rate from 0.3 to 0.5.
This experiment gave the best validation accuracy among all experiments. Increasing dropout helped the model generalize better and reduce its tenedency to memorize the training data.

### Experiment 4 - Higher Learning Rate

In this experiment, I increased the learning rate from 0.001 to 0.01. The model failed to learn meaningful patterns, and both training and validation accuracy remained close to random guessing. This showed that the learning rate was too high and caused unstable weight updates during training.

## Observations

One of the most interesting observations was that a model can achieve very high training accuracy while still performing poorly on unseen images. 
The baseline model reached very high training accuracy but the validation accuracy was much lower. This helped me understand the concept of overfitting more clearly.

I also observed that changing hyperparameters can significantly affect model performance. Some changes improved generalisation while others made training unstable.

## Things That Confused Me

At the beginning of the project, I was confused about why all images needed to be resized to the same dimensions before training.
I was also confused about the difference between training accuracy and validation accuracy. At first, I thought that high training accuracy meant the model was performing well, but the experiments showed that this is not always true.

Understanding convolution layers was also challenging at first. It became easier when I started thinking of them as feature detectors that look for edges and patterns in images.

## Insights Gained

One important insight I gained was that understanding the reasoning behind a model is more valuable than simply obtaining a high accuracy score.

Throughout the project, I spent time understanding why the model behaved in certain ways instead of only focusing on improving the numbers. This helped me connect the practical implementation with concepts such as convolution layers, overfitting, dropout, and learning rates.

## Future Improvements

If I continue working on this project, the first improvement I would make is expanding the dataset. Although the model was able to learn the training images well, the validation results showed that the dataset was still relatively small for good generalisation. I would collect more images under different lighting conditions, backgrounds and camera angles.

I would also like to look into why data augmentation did not improve the validation accuracy as much as I expected. It would be interesting to test different augmentation settings and observe their effect on performance.

Another improvement would be experimenting with additional hyperparameters such as batch size and different optimizers. In this project I mainly focused on dropout and learning rate, but many other factors can influence training behaviour.

Finally, I would like to explore more advanced CNN architectures and compare their performance with the simple CNN used in this project.

### Author: Abhinaya Arunkumar
