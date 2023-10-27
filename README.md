# Satellite-CNN-classification

![Satellite in space]([URL](https://keysight-h.assetsadobe.com/is/image/content/dam/keysight/en/img/ind/aerospace-defense/satellites/Satellite_1200x900.jpg?wid=582&hei=437&fmt=webp-alpha&resMode=sharp2&op_sharpen=1))

Overview: :

Business Case: Urban planning consultants need to filter data for a given city by it's land use. The objective is to run an image classification neural network model on pre-trained data, and use domain knowledge to apply the model to unclassified satellite imagery.

In order to acheive this, the following steps were taken:

1. retrieve the labeled satellite data: using pre-labeled satellite image data from the EuroSAT database (https://www.tensorflow.org/datasets/catalog/eurosat)
1. Create a NN model that can accurately predict land cover using the classified dataset
1. determine best model architecture and tune hyper-parameters to acheive best accuracy scores
1. Predict type of land use on future unseen data

Given time restraints, the entire dataset can take up to 4 hours to run through a model; therefore, will create a "sample" dataset that is a fraction of the entire train/validation dataset, determine the best model, then fit that model to the entire dataset.

# Model performances

1. Starting with a simple Neural Network, a performance of ~50% was deemed inefficient, and moved onto convolutional neural networks.
2. Baseline CNN model performed at 78% validation accuracy
3. Baseline CNN model with regularization on layers performed at 78.5% validation accuracy
4. the above model with dropout layers included performed at 79% accuracy - and would become the top performing model
5. Additional layers were added to the above model, resulting in a decline to 74.7% accuracy

Now that the ideal model based off the sample data was acheived, the model was re-trained on the entire labeled dataset, bringing the accuracy score up to 82% on validation data.

# FINAL MODEL RUN ON UNSEEN DATASET

Using my domain knowledge (born and raised in this area!), I would like to take satellite imagery from the Springfield, MA metropolitan area and see how well the model can classify sections of the image. (taken from Google Earth, 25 October 2023).

The resulting predicted classes were then mapped on the original image, and visual inspection was performed. The model seemed to largely classify areas correctly, and is a good base for future projects.

Some areas for further model tuning & improvement:

1. ReLu appears to be the best activation methodology for neural network layers, however it would be interesting to try other available methodologies (tanh, linear, sigmoid etc.)
2. the filters were largely set at 32, however it would be interesting to evaluate different metrics here
3. ridge regularizers were exclusively used, yet I would like to evaluate lasso, as well as different strengths
4. most importantly, additional labeled data will always help improve the model - hoping to use transfer learning in the future to better train the model for future projects (more to come here).

# Conclusion
Overall, the model performed well at 82% accuracy. As mentioned throughout, there are multiple paths to go in order to improve the model, though arguably the best factor would be incremental data on a like-for-like satellite imagery.
