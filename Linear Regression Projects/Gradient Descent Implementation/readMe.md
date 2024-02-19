## About the project:

This project shows the implementation of different flavors of the Gradient Descent algorithm namely **Batch Gradient Descent**, **Stochastic Gradient Descent**, **Mini-Batch Gradient Descent**. I have used this implementation to solve a regression 
problem. The obtained result from the Gradient Descent algorithm has also 
been visualized using various plots listed below:
1. Loss vs Iterations
2. Fitted line superimposed on the scatter plot of the training dataset.
3. Contour plots depicting the trajectory of the path taken by Gradient Descent
in its quest to search the parameters in the loss terrain.

Finally, I have compared the results obtained by different variations of the Gradient Descent.

## Implementation Overview:

The main function to get the gradient descent result is:

**fit_best_line_using_GD(X, y, weights_initial, epochs=50, lr=0.01**
                        **batch_size=None,** **sample_strategy='random_without_replacement',** **wrap_index_overflow=True)**

**X** is the design matrix corresponding to the training dataset from which sampling would be done.

**y**(1-d array) contains the target variable's value corresponding to datapoints in X.

**weights_initial** An array containing the initial weights.

**epochs**: The number of times the entire dataset passes through the Gradient Descent algorithm.

**lr** is the learning rate.

**batch_size**: The number of data points used in each iteration to get the 
loss function expression.

**sample_strategy** can be 'random_with_replacement', 'random_without_replacement', 
or 'systematic_sampling'
- 'random_with_replacement' - The batch may contain multiple occurrences of the same data point.
- 'random_without_replacement' - The batch will contain unique data points.
- 'systematic_sampling' - The batch will contain unique data points but sampling will be done sequentially.

**wrap_index_overflow**: True means when the sample index overflows 
len(X)-1 then the sample index would be wrapped using the modulo 
operation.

## How Sampling of data points is being handled for different sample_strategy?
There is a custom Sampler class.

**Sampler(X, y)**, is the constructor.

**sample_data(self, batch_size, sample_strategy='random_with_replacement',**
            **wrap_index_overflow=True)**: 
This method is responsible for sampling the data points according to sample_strategy.

Functions for visualization:

**visualize_GD_result(gd_result)**:
This method creates a loss vs iteration plot and a plot containing the fitted line obtained using the Gradient Descent.

**gd_result**: The object returned by the fit_best_line_using_GD().

**show_path_took_by_gd(w0_values, w1_values, loss_terrain, gd_result, smooth_trajectory=False)**:
This function creates a contour plot representing the loss terrain. It 
then superimposes the path taken by the Gradient Descent algorithm on this 
loss terrain.

**Note**: Use show_path_took_by_gd(w0_values, w1_values, loss_terrain, gd_result,  smooth_trajectory=False) function only when the loss function 
has 2 parameters.
