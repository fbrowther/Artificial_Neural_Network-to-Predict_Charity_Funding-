![table](https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/blob/main/Images/funding-available.jpeg)

# Artificial_Neural_Network-to-Predict_Charity_Funding-

A nonprofit foundation called Alphabet Soup wants to develop a tool that can help select its applicants for funding with the best chance of success in their ventures. Employing their historic data on funding approval, a binary classifier model was developed which will predict whether future applicants will be successful or not if they were to be funded by the foundation. 

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
                Keras Tuner was employed to optimize the hyperparameters and derive the best model employed
                
                (9) Final Optimization (NAME included back in)- 
                Organization Names was reintroduced back to the dataset used in first_model and retrained. 
                This produced the highest accuracy score out of all the modifications that was attempted.
                
                (10) Epoches - No of epoches were increased for most of the models above (from 100 to 200) without further improvement.


## Discussion and Conclusions -

       (1) NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, 
       ASK_AMT were features used for training the model while IS_SUCCESSFUL was the target variable.

       (2) Various modifications of the model were performed to increase the accuracy of the model. These included, icreasing the number of
       hidden layers, changing the activation function, reducing the number of features to the relevant features ("APPLICATION_TYPE", "AFFILIATION", 
       "CLASSIFICATION") that didnot compromise the model performance, increasing the test size proportion to 40%, reduce the number of neurons in
       the hidden layers by 50% or 20% (Dropout Regularization), and finally employing the automated model training using Keras Tuner which is 
       scalable hyperparameter optimization framework that tries all combination of the hyperparameters and chooses the ones that generate the most
       accuray and picks the best model to train.
            
       (3) All the model that has been presented here were able to predict both in Training and Test with almost equal accuracy. 
       Hence there was no problem of underfitting or over-fitting noted in these trained models. 
            
       (4) In conclusion, it was noted that NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION were the only features that 
       contributed to predictive power of the models. Any other features (except these) even if excluded didnot influence the model accuracy.
       
## Impportant files for reference
        (1) Final optimization files (Jupyter Notebook & HDF5) - 
        (https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/tree/main/Final%20Optimization)
        (2) Various modifications of the models (Jupyter Notebook) - 
        https://github.com/fbrowther/Artificial_Neural_Network-to-Predict_Charity_Funding-/tree/main/Jupyter%20notebooks
        (3) Various modifications of the models (HDF5) -
