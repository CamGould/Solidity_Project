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
This project intends to have students work through three sections:
1. Create a joint savings account
2. Compile and deploy the contract in the a VM
3. Interact with the deployed contract
#### Step One - Create a Joint Savings Account Contract in Solidity 
<details>
  <summary>Step One Instructions</summary> 
  
  1. From the provided *starter code*, open the Solidity file named *joint_savings.sol* in the **Remix IDE**.
  2. Define a new contract named *JointSavings*
  3. Define the following variables in the new contract:
      1. Two variables of type address payable named *accountOne and accountTwo*
      2. A variable of type address public named *lastToWithdraw*
      3. Two variables of type uint public named *lastWithdrawAmount and contractBalance*
  4. Define a function named *withdraw* that accepts two arguments: amount of type uint and recipient of type payable address. In this function, code the following:
      1. Define a require statement that checks if recipient is equal to either accountOne or accountTwo. If it isn’t, the require statement returns the “You don't own this account!” text.
      2. Define a require statement that checks if balance is sufficient for accomplishing the withdrawal operation. If there are insufficient funds, it returns the “Insufficient funds!” text.
      3. Add an if statement to check if lastToWithdraw is not equal (!=) to recipient. If it’s not equal, set it to the current value of recipient.
      4. Call the transfer function of the recipient, and pass it the amount to transfer as an argument.
      5. Set lastWithdrawAmount equal to amount.
      6. Set the contractBalance variable equal to the balance of the contract by using *address(this).balance* to reflect the new balance of the contract.
  5. Define a public payable function named deposit. In this function, code the following:
      1. Set the contractBalance variable equal to the balance of the contract by using *address(this).balance*.
  6. Define a public function named setAccounts that takes two address payable arguments, named account1 and account2. In the body of the function, set the values of accountOne and accountTwo to account1 and account2, respectively.
  7. Add a fallback function so that your contract can store ether that’s sent from outside the deposit function.
  
</details>
      
#### Step Two - Compile and Deploy the Contract in the VM
1. Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.
2. In the Remix IDE, navigate to the “Deploy & Run Transactions” pane, and then make sure that “JavaScript VM” is selected as the environment.
    1. *I ran into consistent issues with JavaScript VM - had to use Remix VM*
    2. ![](https://github.com/CamGould/Solidity_Project/blob/main/Execution_Results/Javascript%20Vm%20not%20available.png?raw=true)
3. Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.
    1. *Here you can see where the dropdown was that the contract depolyed successfully*
    2. ![](https://github.com/CamGould/Solidity_Project/blob/main/Execution_Results/Contract%20Deployed%20Successfully.png?raw=true)

#### Step Three - Interact with the Deployed Contract
1. Use the *setAccounts* function to define the authorized Ethereum address that will be able to withdraw funds from your contract.
    1. *Here you can see me setting the account addresses to the provided sample accounts* 
    2. ![](https://github.com/CamGould/Solidity_Project/blob/main/Execution_Results/setAccounts.png?raw=true)
2. Test the deposit functionality of your smart contract by sending the following amounts of ether, sometimes you have to convert it to wei.
    1. *Here you can see the specified deposited ammountsin either ether or wei*
    2. ![](https://github.com/CamGould/Solidity_Project/blob/main/Execution_Results/Deposit%20Amounts.png?raw=true)
3. Test the withdrawl function by withdrawing money into the two accounts
    1. *Here is where I made the call to withdrawl to each account. For some reason when I was making the call it was just stuck pending. I think for awhile to debug but could not determine why.*
    2. ![](https://github.com/CamGould/Solidity_Project/blob/main/Execution_Results/Withdraw%20from%20Accounts.png?raw=true) 
