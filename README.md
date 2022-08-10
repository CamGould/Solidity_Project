<h1 align="center">Sample Blockchain Bank Account Using Solidity and Remix</h1>
<h2 align="center"><em>Joint Savings Account</em></h2>
<h4 align="center"> Created by <em>Cam Gould</em> for the <em>University of Toronto Fintech BootCamp</em> </h4>

<p align="center">
  <img
    src="https://blog.cakedefi.com/content/images/2021/07/istockphoto-1226293128-612x612.jpeg"
  >
</p>

### Background Information
A fintech startup company has recently hired you. This company is disrupting the finance industry with its own cross-border, Ethereum-compatible blockchain that connects financial institutions. Currently, the team is building smart contracts to automate many of the institutions’ financial processes and features, such as hosting joint savings accounts.
<br>
<br>
To automate the creation of joint savings accounts, you’ll create a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. Your smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.
<br>
### Project Files
Use the following links to jump right into the Solidity Contract or view results:
<br>
<br>
This notebook contains the [Solidity Contract](https://github.com/CamGould/Solidity_Project/blob/main/Solidity%20Code/Joint_Savings.sol)
<br>
This folder contains [screenshots while running the contract](https://github.com/CamGould/Solidity_Project/tree/main/Execution_Results)
<br>
### Project Outline and Instructions
#### Prepare the Data for Training and Testing
1. Create a Jupyter Notebook for each RNN.
2. For the Fear and Greed model, use the FNG values to try and predict the closing price.
3. For the closing price model, use previous closing prices to try and predict the next closing price. 
4. Each model will need to use 70% of the data for training and 30% of the data for testing.
5. Apply a MinMaxScaler to the X and y values to scale the data for the model.
6. Reshape the X_train and X_test values to fit the model's requirement of samples, time steps, and features.

#### Build and Train LSTM RNNs
1. In each Jupyter Notebook, create the same custom LSTM RNN architecture. 
    1. In the first notebook, fit the data using the FNG values. 
    2. In the second notebook, fit the data using only closing prices.

###  Key Findings and Visuals 
#### Visual Price Predictions of Each Model:
***The Model using Closing Price*** - the far better performing model:
<br>
![](https://github.com/CamGould/Deep_Learning_using_LSTM/blob/main/Supplemental/Closing_graph.png?raw=true)
<br>
<br>
***The Model using FNG Indicators*** - a poor performing model:
<br>
![](https://github.com/CamGould/Deep_Learning_using_LSTM/blob/main/Supplemental/FNG_graph.png?raw=true)
<br>
<br>

#### Evaluating the Performance of Each Model

*Which model has a lower loss?*
<br> 
The loss value for each epoch in the training and validation stage displays how well the model is behaving after each stage of its optimization. After looking at how the models each performed, it is no suprise that the **Closing Price Model** had a lower loss than the *FNG Model*. The results for eachof these can be found in their notebooks when the model is running the epochs.
<br>
<br>
*Which model tracks the actual values better over time?*
<br>
When comparing the two graphs of the outputs of each model it is not hard to tell that the **Closing Price Model** tracked the actual values far better. If the two models were closer, and we could not tell right away from the visuals, I would take the average distance the model's price prediction was off of the actual price to determine this answer.
<br>
<br>
*Which window size works best for the models?*
In the end I decided to go with a 10-day closing price window. I found that by having a larger window, the model was predicting prices. using smoother data. This in return helped to minimize some of the outliers, or extremes, that were effecting the model's accuracy of predictions.
