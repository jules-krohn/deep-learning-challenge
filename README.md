# deep-learning-challenge


The purpose of this analysis is to try to predict whether an organization's project will be successful using the grant funds provided by the AlphabetSoup Charity. 

Data Preprocessing

*The target (y) variable is whether the project was successful, or the "IS_SUCCESSFUL" column in the dataframe.
*The variables that are the features (X) is every other column in the dataframe, excluding "EIN" and "NAME".

*The variables that should be removed from the dataset are the EIN ID number and the NAME of the organization, though in the optimized version of the model the name of the organization was a tested feature. There are pros and cons to keeping the name. On one hand, the algorithm may see that the more often a specific organization successfully completes a funded project, the more likely they are to complete further projects, possibly increasing the accuracy of the model. On the other hand, an organization's name in itself doesn't have much weight on whether or not their project will be successful, though if the same name of an organization is proven to have enough successfully funded projects, the model may put weight on the name instead of other features, skewing the accuracy.

Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why? I chose to have 50 neurons in the input layer, as there were 47 different features in the scaled data dataframe. I had two hidden layers, each with 30 neurons because they were 2/3 the number of neurons in the input layer. This idea came from a Medium article linked here: https://medium.com/geekculture/introduction-to-neural-network-2f8b8221fbd3#:~:text=The%20number%20of%20hidden%20neurons,size%20of%20the%20input%20layer.

Were you able to achieve the target model performance? Yes. The initial model ran at around 72% accuracy, while the optimized model ran at 78% accuracy. 

What steps did you take in your attempts to increase model performance?
The steps taken are as follows:
* Include the NAME column from the original data set. This in itself made a large difference in the accuracy of the model, though only the organizations who have applied more than ten times were included.
*Change the activation from "relu" on the hidden layers to "tanh"
*Decreased the number of neurons used in the hidden layers 
*Used one more hidden layer than in the initial model

Summary: 
This deep learning model was overall successful, and I was able to increase the overall accuracy from 72% to 78%, which means the algorithm is likely to successfuly predict a successful project 78% of the time. Successful organizations are likely to:
* Have applied more than ten times
* Have an application type of: T3, T4, T6, T5, T8, T7, or T19
* Have a classification value of C1000, C2000, C1200, C3000, C2100, or C7000  
