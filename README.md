# Satellite-CNN-classification

Overview: using pre-labeled satellite image data from the EuroSAT database (https://www.tensorflow.org/datasets/catalog/eurosat):

Business Case: Urban planning consultants need to filter data for a given city by it's land use. Run an image classification model on pre-trained data, and use domain knowledge to apply the model to unclassified satellite imagery.


1. Create a NN model that can accurately predict land cover using the classified dataset
1. determine best model architecture and tune hyper-parameters to acheive best accuracy scores
1. Predict type of land use on future unseen data

Given time restraints, the entire dataset can take up to 4 hours to run through a model; therefore, will create a "sample" dataset that is a fraction of the entire train/validation dataset, determine the best model, then fit that model to the entire dataset.

# FINAL MODEL RUN ON UNSEEN DATASET

Using my domain knowledge (born and raised in this area!), I would like to take satellite imagery from the Springfield, MA metropolitan area and see how well the model can classify sections of the image. (taken from Google Earth, 25 October 2023).

# Conclusion
Overall, the model performed well at 82% accuracy. As mentioned throughout, there are multiple paths to go in order to improve the model, though arguably the best factor would be incremental data on a like-for-like satellite imagery.
