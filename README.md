# Circle Packing with Encoder-Decoder Approach

## Overview

This project implements a circle packing solution using an Encoder-Decoder approach. We have extended the model to also include any arbitrary outer shape. The basic aim of the project is to fit a given number of circles with their corresponding radii, whithin a circle or any other shape, while maintaining minimum overlap between the inner circles. The codebase consists of 3 files that cater to 3 different cases. The first file is for packing circles of any radii within a circle. The second file is to fit circles of any radii within a polygon and the third file is to fit them within any outer shape. Note that for the outer shape case, there are certain criteria that needs to be fulfilled for the code to work. Basically, if teh outer shape is represented in (r,$\theta$ ) form, if there is not a one-to-one mapping between r and $\theta$.

1. **Any Shape Packing**: Fits any circle of varying radii within a specified outer shape.
2. **Polygon Packing**: Packs any number of circles with different radii within any polygonal shape.
3. **Circle Within Circle Packing**: Fits circles of any radius within larger circles.

All the above files are ipynb files.

## Installation

To set up the project, first download the codebase.

Once you have downloaded the codebase, run the following command to install all dependencies/ requirements.

pip install -r requirements.txt

## Run the Model

1. Any Shape Packing

In this case we have taken the outer shape to be $r = 1+cos^2(\theta)$. There are multiple hyperparameters that one can tweak while playing with the model. Firstly in case of any shape packing, you have a RBF model that has parameters like output features, input features, learning rate, num_of_epochs etc, that you can change. We have also provided a plot to visualize what the rbf kernel is learning. It learns the maximum distance the center of a circle with radii $r_i$ can go without exceeding the outer shape. You can also vary epsilon and sigma parameters to see how the rbj kernel learns differently.

In order to pack circles of say ${r_1, r_2...} you need to change the variable small_circle, and add radii of the circles you would like to pack. Along with the small circle radii, there are other parameters that you can change. Other parameters include the number of runs, the patience(number of epochs upto which we dont change the beta distribution despite poor performance ) etc.

2. Polygon Packing

Here we have a parameter called N, which corresponds to the number of sides in the outer shape. We have similar hyperparameters here as well that can be tweaked as per your convenience.

3. Circle Within Circle Packing

We have similar hyperparameters here as well that can be tweaked to improve performance.

Note that in all these models we have introduced a parameter that varies the beta distribution that samples perturbation points. The amount by which the paramters $\alpha$ and $\beta$ decrease or increase are also params that can be adjusted.
