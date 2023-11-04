# EuroSAT_Classification

The aim of this exercise was to perform supervised ML on data from the EuroSAT dataset. In order to achieve it, first, the data had to be prepared: the mean and ranges of the bands in the per-pixel per-file were extracted. Subsequently, new features were derived: NDVI, NDWI, EVI, SAVI. This process is shown in the notebook ```Data_Preprocessing```.

Next, two supervised ML approaches were tested in order to classify the data. These two approaches were Random Forest and Multilayer Perceptron. Notebooks ```TaskReport_Random_Forest``` and ```TaskScript_Random_Forest``` show the process for the Random Forest approach, and the notebook ```MLP_Sklearn``` shows the process for MLP.  

We chose to evaluate both Random Forest and MLP, as these algorithms operate differently. Random Forest was chosen for its ability to handle high-dimensional data and for feature importance analysis, which provides insights into the classification process. Moreover, Random Forest is an ensemble method that combines outputs of multiple single trees, making it very robust. Additionally, this method is faster in training than deep learning methods such as MLP. Lastly, it is said that Random Forest is less prone to overfitting.   

The MLP, on the other hand, is a deep learning method which is also able to handle high-dimensional data and complex relationships in it. Moreover, since the dataset was large enough, the MLP could be used to learn hierarchical and abstract features from the data. Lastly, its architecture is flexible and can be easily adjusted.

Comparing both of the algorithms, it was concluded that for this dataset that the Random Forest achieved higher accuracy.

For both cases, the data was split into train, validation, and test sets in proportions of 60:20:20. The split is done so that first, the algorithm does not simply memorize the data, as that would make it extremely accurate but unable to work with new unseen input. Secondly, in addition to the train and test split, the validation set is used to allow for checking the model during training and also aids in choosing the best hyperparameters. Moreover, all the sets should be well separated so that there is no data leakage between them, as that would also contribute to an overly optimistic performance estimate. Lastly, the test set is an unbiased evaluator of a final model fit on unseen data.

The split of 60:20:20 was chosen as there is a lot of data available for the model to learn from. In another case, when the data is limited, the split could be 80:10:10.
