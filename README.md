![table](https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/blob/main/Images/funding-available.jpeg)

# Artificial_Neural_Network-to-Predict_Charity_Funding-

A nonprofit foundation called Alphabet Soup wants to develop a tool that can help select its applicants for funding with the best chance of success in their ventures. Hence employing their data on previous funding, a binary classifier model will be developed which will predict whether future applicants will be successful or not if they were to be funded by the foundation. 

## Brief Introduction - 

The dataset contained information on more than 34,000 organizations that have received funding from Alphabet Soup over the years. The information included-

        (a) EIN and NAME—Identification columns

        (b) APPLICATION_TYPE—Alphabet Soup application type

        (c) AFFILIATION—Affiliated sector of industry

        (d) CLASSIFICATION—Government organization classification

        (e) USE_CASE—Use case for funding

        (f) ORGANIZATION—Organization type

        (g) STATUS—Active status

        (h) INCOME_AMT—Income classification

        (i) SPECIAL_CONSIDERATIONS—Special consideration for application

        (j) ASK_AMT—Funding amount requested

        (k) IS_SUCCESSFUL—Was the money used effectively
   	
## Aims and Objective -
To build Artificial Neural Network Model that can predict whether future applicants will be successful if they were to be funded by Alphabet Soup

## Machine Learning (Neural Network) Steps to be executed -

      (1) Data Preparation and Scaling,
      
      (2) Compile, Train, and Evaluate the Neural Network Model,
      
      (3) Optimize the Model for best performance possible (Feature Selection, Hyperparameter tuning)
      
      (4) Make recommendation to Alphabet Soup

![images](https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/blob/main/Images/network.svg)

## Specific Libraries and modules employed -
      
      (1) Scikit-Learn Library-
      
            (a) Preprocessing - StandardScaler, OneHotEncoder
  
            (b) model_selection - train_test_split
            
            Manifold - TSNE
  
      (2) TensorFlow - Neural Network
      
      (3) keras-tuner - To automate the Neural Network to choose the best model and the best hyperparameters
      
      (4) Pandas - Data manupulation, Create bins for rare occurrences in columns, Scaling, and OneHotEncoding        


## Modifications included & the improvement in model performance -

![table](https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/blob/main/Images/Comparison%20of%20accuracy%20scores%20final.png) 

#### Trained Model Details :
                (1) First_Model - 
                All features included except 'EIN and NAME'
                
                (2) Features Reduced - 
                All features except "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION" were removed
                
                (3) Activation Function (Tanh) - 
                Activation Function for hidden layers were changed to 'tanh' from 'relu'
                
                (4) Increased Hidden layers - 
                No. of hidden layers were increased from 2 to 4.
                
                (5) Dropout Regularization - 
                50% of neurons from first hidden layers and 20% from the 2nd, 3rd, and 4th hidden layers were dropped.
                
                (6) Test Size(40%) + Tanh Activation - 
                Train to Test ratio was increased to 60/40 and retrained using tahn activation function.
                
                (7) Automated Model (All Features except'EIN and NAME') - 
                Keras Tuner was employed to optimize the hyperparameters & derive the best model.
                
                (8) Automated Model (Reduced Features) - 
                All features except "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION" were removed and 
                Keras Tuner was employed to optimize the hyperparameters and derive the best model employed.
                
                (9) Final Optimization (NAME included back in)- 
                Organization Names was reintroduced back to the dataset used in first_model and retrained. 
                This produced the highest accuracy score out of all the modifications that was attempted.

## Discussion and Conclusions -

The targets for this analysis were 

NAME—Identification columns

    (b) APPLICATION_TYPE—Alphabet Soup application type

    (c) AFFILIATION—Affiliated sector of industry

    (d) CLASSIFICATION—Government organization classification

    (e) USE_CASE—Use case for funding

    (f) ORGANIZATION—Organization type

    (g) STATUS—Active status

    (h) INCOME_AMT—Income classification

    (i) SPECIAL_CONSIDERATIONS—Special consideration for application

    (j) ASK_AMT—Funding amount requested

    (k) IS_SUCCESSFUL—Was the money used effectively

           (1) Inspite of performing dimensionality reduction employing PCA and tSNE, no specific pattern 
               or clusters within the dataset was obtained. 

           (2) Furthermore, with the help of the elbow curve the dataset was further analysed employing n_clusters=3; 
               this yielded a inertia value of 6030. Further training of the data specifically using n_clusters=3; 
               didnot yield a successful dispersion of the dataset forming any specific clusters.

            (3) For the unsupervised K-Means algorithm, inertia value can be used to find better hyperparameters. 
                One such method is the initialization. Using Scikit Learn's "k-means++" and "random" methods, 
                the model was re-trained and the value of its inertia was compared. The lower most value of inertia 
                obtained can then be used for hyperparameter tuning. 
                However, in the above dataset, even this approach failed to obtain distinguishable clusters. 

            (4) The dataset separated into two major clusters (orange and green) was confirmed by Hierarchial Clustering Model
                (most probably indicating myopic and non-myopic group respectivly).

            (5) Therefore, it can be concluded that unsupervised Machine Learning algorithm using KMeans (combined with PCA & tSNE) 
                failed to identify any clusters that can be used to predict Myopia in Children aged between 5-9 years old. 
                However, Hierarchial clustering with further refinement of hyperparameters could potentially yield a 
                better performing predictive model.


## Limitations - 

      (1) In the PCA analysis, 90% of the features were retained, not allowing the PCA to identify the most contributing 
          features for this dataset. Therefore, the analyses can be repeated with reduced features and assess its performance.
      
      (2) Feature extraction or feature engineering steps can be adopted to combine/improve the features that are being 
          used to build the model.
          








![table](https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/blob/main/Images/Comparison%20of%20accuracy%20scores.png)

