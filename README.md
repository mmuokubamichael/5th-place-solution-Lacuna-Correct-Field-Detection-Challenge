# 5th-place-solution-Lacuna-Correct-Field-Detection-Challenge
## Approach
The Lacuna Correct Field Detection Solution was built on an optimized catboost model .
### Data Types:  
Planet Data (June 2017, December 2017, June 2018, December 2018) and Sentinel Data. 
All the data provided was used in the model build process with different processing/preprocessing methods applied.
## Features/Feature Generation
The data pre-processing involved extraction of all image data from the respective folders:
### Planet Data: 
Planet Images were provided in 3-Channels, and in 4 time periods. The data was loaded from all 4 folders (for each period) for each image ID and appended. 
On loading, the images were resized to a single channel then an Otsu threshold was applied, and the image was centrally cropped to a 20 by 20 image. This gave 20 * 20 * 4 flattened features (1600 features in total).
### Sentinel Data:  
Sentinel Data was loaded for all images and an average was gotten for all pixels across all the bands, a total of 192 values, representing 16 sentinel values across 12 months. 


Planet and Sentinel Data were combined for a total of 1600 + 192 (=1792) features. 
All zero-only columns were further removed.

## Model Training and Prediction
The algorithm used was a catboost model with hyperparameters generated from a Grid Search.
The model was then trained using a 10-fold cross-validation, and predictions made on the test set with each fold. The final prediction was an average of predictions from every fold.

### Running on Google Colab
1. Upload the Lacuna Correct Field Detection Challenge.ipynb file into Colab 
2. Upload all provided Files from Zindi.
3. Click Rutime
4. Click ‘Run All’
## Packages
 .Packages not available on Colab that had to be installed: Catboost
 .All other packages can be imported directly on Colab as contained in the code as well
 
 link to the competition: https://zindi.africa/competitions/lacuna-correct-field-detection-challenge/leaderboard
