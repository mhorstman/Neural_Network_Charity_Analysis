# Charity Analysis Using Neural Networks

## Overview
The purpose of this analysis is to help Alphabet Soup determine if deep learning can help decide which charitable investments will be sucessful. The company provided a csv file with past investment to use to train and test a model and the results are discussed below.  

- **Input:** charity_data.csv, AlphabetSoupCharity_starter_code.ipynb
- **Tools/Software:** Google Colab, Python Tensor Flow
- **Output:** AlphabetSoupCharity.ipynb, AlphabetSoupCharity.h5,AlphabetSoupCharity_Optimization.ipynb, README.md

## Results
The analysis was grouped into 3 main groupings: Data Preprocessing; Compiling, Training, and Evaluating the Model; and Model Optimization.

#### Data Preprocessing
The data in the input csv file was split out into target and features to feed into the deep learning model. Several columns were unsued because they did not contribute to the analysis and therefore those columns were dropped from the analyis. 
- Target Data: IS_SUCCESSFUL
- Feature Data: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT
- Unused Data: EIN, and NAME

#### Compiling, Training, and Evaluating the Model
The deep learning model was set up wtih 2 hidden layers which yielded a total of 403 parameters. The number of neurons were chosen to start out with a low number so system resources could be conserved. In the optimization the number of neurons were incresased. 
- Neurons in Layer 1: 8
- Neurons in Layer 2: 5

#### Optimization
In order to improve model performance a series of 4 attempts were made at optimization. None of the optimizations had a material impact on the results which can be seen in the next section below.
- Optimization 1: Add 2 additional hidden layers (neurons per layer: 8, 6, 4, 2)
- Optimization 2: Add neurons to hidden layers (neurons per layer: 50, 25)
- Optimization 3: Change activation function from ReLU to Tanh
- Optimization 4: Adjust input data by dropping INCOME_AMT. This column was chosen because there are many rows with zero income amount so I theorized that might be skewing the results.
- Optimization 5: Combine all changes from opimizations 1 through 4 and run them together in one model.

### Overall Results
The loss and accuracy metrics for the original model and each of the 5 optimizations are located in the table below.
![Overall Results](https://github.com/mhorstman/Neural_Network_Charity_Analysis/blob/main/results_summary.png)
From this table we can see that the original model had a loss of 0.56 and accuracy of 0.72. None of the optimization attempts made a material impact on either metric. 

## Summary
The results of the model were moderate and none of the optimization attemps improved the model. Therefore I believe that the data is complext enough that neural networks may not be able to get any additional accuracy. I reccommend trying to re-run the analysis using Random Forest supervised machine learning model to see if better results can be achieved. If possible, additional data added to the dataset could also yield better results. 