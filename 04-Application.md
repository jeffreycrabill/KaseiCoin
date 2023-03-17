# Application

## Challenge: Martian Token Crowdsale

![alt=" "](Images/21-4-application-image.png)

### Background

After waiting for years and passing several tests, you were selected by the Martian Aerospace Agency to be part of the first human colony on Mars. As a prominent fintech professional, you were chosen to lead a project to develop a monetary system for the new Mars colony. You have decided to base this new monetary system on blockchain technology, and to define a new cryptocurrency called **KaseiCoin**. (“Kasei” means “Mars” in Japanese.)

KaseiCoin will be a fungible token that is ERC-20 compliant. You will launch a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin.

### What You're Creating

You will create a fungible token that is ERC-20 compliant and that will be minted by using a `Crowdsale` contract from the OpenZeppelin Solidity library.

The crowdsale contract that you create will manage the entire crowdsale process, allowing users to send ether to the contract and in return receive KAI, or KaseiCoin tokens. Your contract will mint the tokens automatically and distribute them to buyers in one transaction.

Note that the starter files that are provided for this Challenge contain a `pragma` for Solidity version 0.5.5. You will use the starter files to do the following:

1. Create the KaseiCoin token contract.

2. Create the KaseiCoin crowdsale contract.

3. Create the KaseiCoin deployer contract.

4. Perform a real-world, pre-production test of your crowdsale. In order to do so, you will deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

5. Record a short video or take several screenshots that show the deployed contract in action.

6. **Optional:** Use OpenZeppelin to extend the functionality of your crowdsale contract by adding time restrictions, refund capabilities, and a cap for the number of tokens that may be created.

> **Note** You may choose whether or not to complete the optional section. It is designed to further your professional growth and development, but it will not be graded as part of this assignment. Please reach out to your instructional team if you have any questions about how to complete the optional section.

In the `README.md` file of your GitHub repository for this Challenge, you will create a section called Evaluation Evidence. In this section, you will share screenshots of your work from each subsection of the Challenge assignment.

### Files

Download the following files to help you get started:

[Starter code](Challenge/Starter_Code.zip)

### Instructions

The steps for this Challenge are divided into the following sections:

1. Create the KaseiCoin Token Contract

2. Create the KaseiCoin Crowdsale Contract

3. Create the KaseiCoin Deployer Contract

4. Deploy the Crowdsale to a Local Blockchain

5. Optional: Extend the Crowdsale Contract by Using OpenZeppelin

#### Create the KaseiCoin Token Contract

In this section, you will create a smart contract that defines KaseiCoin as an ERC-20 token. To do so, complete the following steps:

1. Import the provided `KaseiCoin.sol` starter file into the Remix IDE.

2. Import the following contracts from the OpenZeppelin library:

    * `ERC20`

    * `ERC20Detailed`

    * `ERC20Mintable`

3. Define a contract for the KaseiCoin token called `KaseiCoin`, and have the contract inherit the three contracts that you just imported from OpenZeppelin.

4. Inside of your `KaseiCoin` contract, add a constructor with the following parameters: `name`, `symbol`, and `initial_supply`.

5. Then, as part of your constructor definition, add a call to the `ERC20Detailed` contract’s constructor, passing the parameters `name`, `symbol`, and `18`. Recall that 18 is the value for the `decimal` parameter.


6. Compile the contract using compiler version 0.5.5.

7. Check for any errors and debug as needed.

8. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Create the KaseiCoin Crowdsale Contract

In this section, you will define the KaseiCoin crowdsale contract. To do so, complete the following steps:

1. Import the provided `KaseiCoinCrowdsale.sol` starter code into the Remix IDE.

2. Have this contract inherit the following OpenZeppelin contracts:

    * `Crowdsale`

    * `MintedCrowdsale`

3. Within the `KaisenCoinCrowdsale` constructor, provide parameters for all of the features of your crowdsale, such as `rate`, `wallet` (where the funds that the token raises should be deposited), and `token` (the KaseiCoin that the KaseiCoinCrowdsale will use). Configure these parameters as you see fit for your KaseiCoin token.

4. Compile the contract using compiler version 0.5.5.

5. Check for any errors and debug as needed.

6. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Create the KaseiCoin Deployer Contract

In this section, you will create the KaseiCoin deployer contract. Start by uncommenting the `KaseiCoinCrowdsaleDeployer` contract in the provided `KaseiCoinCrowdsale.sol` starter code.

Next, within the `KaseiCoinCrowdsaleDeployer` contract, add variables to store the addresses of the `KaseiCoin` and `KaseiCoinCrowdsale` contracts, which this contract will deploy. To do so, complete the following steps:

1. Create an `address public` variable called `kasei_token_address`, which will store `KaseiCoin`’s address once that contract has been deployed.

2. Create an `address public` variable called `kasei_crowdsale_address`, which will store `KaseiCoinCrowdsale`'s address once that contract has been deployed.

3. Add the following parameters to the constructor for the `KaseiCoinCrowdsaleDeployer` contract: `name`, `symbol`, and `wallet`.

Complete Steps 4–9 within the constructor body (between the curly braces).

4. Create the KaseiCoin token by using a new instance of the `KaseiCoin` contract with parameters `name` and `symbol,` and by setting the `initial_supply` parameter to 0.

5. Assign the KaseiCoin token contract’s address to the `kasei_token_address` variable. This will allow you to easily fetch the token's address later.

6. Create a new instance of the `KaseiCoinCrowdsale` contract using the following parameters:

    * `rate` (Set `rate` equal to 1 in order to maintain parity with ether.)

    * `wallet` (Pass `wallet` in from the main constructor. This is the wallet that will get paid all of the ether raised by the crowdsale contract.)

    * `token` (This is the `token` variable where `KaseiCoin` is stored.)

7. Assign the KaseiCoin crowdsale contract’s address to the `kasei_crowdsale_address` variable. This will allow you to easily fetch the crowdsale’s address later.

8. Set the `KaseiCoinCrowdsale` contract as a minter.

9. Have the `KaseiCoinCrowdsaleDeployer` renounce its minter role.

10. Compile the contract using compiler version 0.5.5.

11. Check for any errors and debug as needed.

12. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Deploy the Crowdsale to a Local Blockchain

In this section, you will deploy the crowdsale to a local blockchain using Remix, MetaMask, and Ganache. To do so, complete the following steps. Record a short video or take screenshots that illustrate the three steps outlined below as evidence of your deployed crowdsale contract.

1. Deploy the crowdsale to a local blockchain with Remix, MetaMask, and Ganache.

> **Hint** Refer back to the videos in the previous lessons for a step-by-step walkthrough of how to deploy the crowdsale.

2. Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances associated with those accounts.

3. After purchasing tokens with one or more test accounts, view the total supply of minted tokens and the amount of wei that has been raised in the crowdsale contract.

#### Optional: Extend the Crowdsale Contract by Using OpenZeppelin

In this **optional** section, you may extend the crowdsale contract to enhance its functionality. To do so, you will use the following OpenZeppelin contracts:

* `CappedCrowdsale`: This contract allows you to cap the total amount of ether that may be raised during your crowdsale.

* `TimedCrowdsale`: This contract allows you to set a time limit for your crowdsale by adding an opening time and a closing time.

* `RefundablePostDeliveryCrowdsale`: Every time you launch a crowdsale, you set a goal amount of ether to raise. If the goal is not reached, it is common practice to refund your investors. This contract adds this capability to a crowdsale.

> **Hint** We encourage you to read more about these contracts on the [Crowdsales page](https://docs.openzeppelin.com/contracts/2.x/crowdsales) of the OpenZeppelin documentation.

To enhance your KaseiCoin crowdsale with this added functionality, complete the following steps:

1. Import the three OpenZeppelin contracts described above into the `KaseiCoinCrowdsale.sol` contract by using the following code:

    ```solidity
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/CappedCrowdsale.sol";
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/TimedCrowdsale.sol";
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/distribution/RefundablePostDeliveryCrowdsale.sol";
    ```

2. In addition to the `Crowdsale` and `MintedCrowdsale` contracts, which your contract previously inherited from OpenZeppelin, have your `KaseiCoinCrowdsale` contract inherit the three contracts that you imported in the previous step:

    * `CappedCrowdsale`

    * `TimedCrowdsale`

    * `RefundablePostDeliveryCrowdsale`

3. In the `KaseiCoinCrowdsale` constructor, add the following new parameters:

    * `uint goal`: This variable will represent the amount of ether which you hope to raise during the crowdsale&mdash;the crowdsale’s goal.

    * `uint open`: This variable will represent the opening time for the crowdsale.

    * `uint close`: This variable will represent the closing time for the crowdsale.

4. Complete the `KaseiCoinCrowdsale` constructor code by adding calls to the new contracts, as the following code shows:

    ```solidity
    constructor(
            uint256 rate, // rate in TKNbits
            address payable wallet, // sale beneficiary
            KaseiCoin token, // the KaseiCoin itself that the KaseiCoinCrowdsale will work with
            uint goal, // the crowdsale goal
            uint open, // the crowdsale opening time
            uint close // the crowdsale closing time
        ) public
            Crowdsale(rate, wallet, token)
            CappedCrowdsale(goal)
            TimedCrowdsale(open, close)
            RefundableCrowdsale(goal)
        {
            // constructor can stay empty
        }
    ```

    > **Important** `RefundablePostDeliveryCrowdsale` itself inherits the `RefundableCrowdsale` contract, which requires a `goal` parameter. So, in addition to the others, you must call the `RefundableCrowdsale` constructor from your `KaseiCoinCrowdsale` constructor. `RefundablePostDeliveryCrowdsale` does not have its own constructor, which is why we use the `RefundableCrowdsale` constructor that it inherits.
    >
    > If you forget to call the `RefundableCrowdsale` constructor, the `RefundablePostDeliveryCrowdsale` will fail. This is because it does not have its own constructor, and so it relies on the `RefundableCrowdsale` constructor.

5. Next, update the `KaseiCoinCrowdsaleDeployer` contract to allow the deployment of the updated crowdsale contract. In the constructor of the deployer contract, add a new `uint` parameter called `goal` that will allow you to set the crowdsale goal.

6. In the core assignment, you added an instance of the `KaseiCoinCrowdsale` contract to the KaseiCoin deployer contract. Since we have modified the `KaseiCoinCrowdsale` contract to support new functionality, you must now update your previous code with the following code:

    ```solidity
    KaseiCoinCrowdsale kasei_crowdsale = new KaseiCoinCrowdsale (1, wallet, token, goal, now, now + 24 weeks);
    ```

   Note that in the preceding code, you added values for the three new parameters. The `goal` parameter represents the amount of ether to raise during the crowdsale, `now` represents the crowdsale opening time, and `now + 24 weeks` represents the closing time.

    The `now` function returns the current Ethereum block timestamp in the form of seconds since the Unix epoch. The **Unix epoch** (also known as **Unix time**, **POSIX time**, or **Unix timestamp**) is an integer that represents the number of seconds that have elapsed since January 1, 1970 (midnight UTC/GMT), not counting leap seconds.

7. Compile and test the updated contract by completing following steps:

    * Send ether to the crowdsale from a different account (**not** the same account that is raising funds). Then, once you confirm that the crowdsale works as expected, try to add the token to your wallet and test a transaction.

    * You can set the `close` time to be `now + 5 minutes`, or any timeline that you'd like to test, for a shorter crowdsale.

    * When sending ether to the contract, make sure that you meet the contract’s `goal`. Then, finalize the sale using the `Crowdsale` contract's `finalize` function. To finalize the sale, `isOpen` must return false (`isOpen` comes from `TimedCrowdsale` and checks to see whether the `close` time has passed yet). If you set the `goal` to 300 ether, for example, you may need to purchase tokens from multiple accounts in order to meet the goal. If you run out of pre-funded accounts in Ganache, you can create a new workspace.

    * View your tokens in MetaMask. In MetaMask, click Add Token, then click Custom Token,  and enter the token contract’s address. Make sure to purchase higher amounts of tokens in order to see the denomination appear in your wallet as more than a few wei worth.

### Requirements

In order for your submission to be graded, you must create a section in the `README.md` file of your GitHub repository called Evaluation Evidence, where you will share screenshots of your work.

#### Step 1: Create the KaseiCoin Token Contract (10 points)

To receive all points, you must:

* Code the `KaseiCoin` contract. (5 points)

* Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository. (5 points)

#### Step 2: Create the KaseiCoin Crowdsale Contract (15 points)

To receive all points you must:

* Have your `KaseiCoinCrowdsale` contract inherit the OpenZeppelin `Crowdsale` and `MintedCrowdsale` contracts. (5 points)

* Add the `rate`, `wallet`, and `token` parameters to your crowdsale contract’s constructor. (5 points)

* Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository. (5 points)

#### Step 3: Create the KaseiCoin Deployer Contract (35 points)

To receive all points you must:

* Add variables to the `KaseiCoinCrowdsaleDeployer` contract that can store the `KaseiCoin` and `KaseiCoinCrowdsale` contract addresses. (5 points)

* Add the `name`, `symbol`, and `wallet` parameters to the `KaseiCoinCrowdsaleDeployer` contract’s constructor. (10 points)

* Add the required code within the constructor’s body. (15 points)

* Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository. (5 points)

#### Step 4: Deploy the Crowdsale to a Local Blockchain (30 points)

To receive all points you must:

* Record a short video or take screenshots as evidence of your deployed crowdsale contract. The video or screenshots should illustrate the following: (30 points)

   * Deployment of the contract to a local blockchain with Remix, MetaMask, and Ganache.

   * Using test accounts to buy new tokens from the crowdsale and then checking the balances associated with the test accounts.

   * After purchasing tokens with test accounts, viewing the total supply of minted tokens and the amount of wei that has been raised by the crowdsale.

> **Important** If you provide screenshots, add them to the `README.md` file of your Challenge repository. The screenshots should provide a guide that someone else could use to compile the contracts and add the KaseiCoin token to MetaMask.

#### Coding Conventions and Formatting (10 points)

To receive all points, you must:

- Place imports at the top of the file. (3 points)

- Name functions and variables using `mixedCase`, as stated in the [Solidity Language Style Guide](https://docs.soliditylang.org/en/v0.5.3/style-guide.html#naming-conventions). (2 points)

- Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. (3 points)

- Use concise logic and creative engineering where possible. (2 points)

### Submission

Create a GitHub repository and a `README.md` file that explains the process for purchasing KaseiCoin.

Your `README.md` file should include screenshots that illustrate your contracts’ functionality as detailed in the instructions above.

You can also record your interactions with the executed contract as an animated GIF or short video. To record a video, you can use the following tools:

* If you are working on a Mac, you can create a screen-recording by using the built-in QuickTime player. To learn more about this tool, refer to the [Use QuickTime Player](https://support.apple.com/en-us/HT208721#quicktime) Apple support page.

* If you are working in Windows 10, you can create a screen-recording by using the built-in Xbox Game Bar. To learn more about this tool, refer to the [Use Xbox Game Bar to capture game clips and screenshots on Windows 10](https://beta.support.xbox.com/help/friends-social-activity/share-socialize/record-game-clips-game-bar-windows-10) Microsoft support page.

* To create an animated GIF, you can use [Recordit](https://recordit.co/) on a Mac or in Windows.

To submit your Challenge assignment, click Submit, and then provide the URL of your GitHub repository for grading.

> **Note** You are allowed to miss up to two Challenge assignments and still earn your certificate. If you complete all Challenge assignments, your lowest two grades will be dropped. If you wish to skip this assignment, click Next, and move on to the next Module.

Comments are disabled for graded submissions in BootCamp Spot. If you have questions about your feedback, please notify your instructional staff or your Student Success Manager. If you would like to resubmit your work for an improved grade, you can use the Resubmit Assignment button to upload new links.  You may resubmit up to three times for a total of four submissions.

## Career Connection

Welcome, and congratulations on completing the module on tokenomics! You’re nearing the end of the boot camp, and this week’s career content will ensure that you are ready for your next steps—whether that’s a job search, a promotion, or something entirely new.

Here’s the Career Connection agenda for today:

* Tokenomics in the Workplace

* Finding Your Career Fit: Earning a Raise or Promotion

* Interview Prep

* Next Steps

### Tokenomics in the Workplace

This module discussed several innovations inspired by tokenization, including new crowdfunding processes and NFTs. Another opportunity is the fractionization of assets. Remember how disruptive Robinhood was when it started offering fractional shares? Tokenized assets can be fractionized as well. The point is that innovation is everywhere in the world of tokenomics.

Now, we want you to pause and dream for a bit. What does tokenomics have in store for you? Will you be an innovator and develop new ways of using the technology? Or are you interested in working with one of the current innovations?

There are tokenomics jobs in the current market that never existed before. Today, there is a job posting for a Blockchain Creative Director, a visionary for a company’s NFT portfolio. There is also a posting for a Tokenomic Modeling Analyst. These are totally new job titles! How will you contribute to the innovation?

### Finding Your Career Fit: Earning a Raise or Promotion


![alt = "On the Job"](Images/FinTech-Career-On-The-Job.png)

At some point in your career, you may need to ask for a raise or a promotion. We’ve decided to bring this up now because preparing for this moment ahead of time will set you up for success. Consider implementing the following recommendations:

* **Keep receipts.** Keep track of your major successes at the company in a personal document. Include quantitative figures such as the number of people managed or the amount of cost reduced. These “receipts” can be used to demonstrate your value as an employee.

* **Periodically check salary trends.** Stay up to date on the salary range for positions similar to yours. Understand how people in similar positions are being compensated in your location and at your company.

* **Learn the company fiscal calendar.** At most companies there are specific times when it is most convenient to raise salaries. This is commonly at the end of the fiscal year when the company is planning the next year’s budget. Other times to consider are during an annual or quarterly employee review. Learn these dates and plan accordingly.

When the time is right, this small bit of work will create a strong foundation for your raise or promotion conversation.

> **Interview Prep**
>
> Read each question, enter your answer in a notebook file or text editor, and then compare your response to the provided one.
>
> **Note:** The lessons didn’t explicitly cover all the questions. However, the skills and concepts that you learned (plus your research skills) should have prepared you to answer them.
>
> 1. What is tokenomics?
>
>       * Answer: The word tokenomics is a combination of the words token and economics. So, tokenomics is the study of the economics of crypto tokens.
>
> 2. What factors do you consider when assessing a cryptocurrency for investment purposes?
>
>    * Answer: These answers will vary. Some things that you may discuss are the token’s functionality, founding team, community, whitepaper, hash rate, fees, market capitalization, and circulating supply.
>
> 3. What is a layer-1 token?
>       * Answer: Layer-1 tokens are the native tokens to a particular blockchain. They are used to power all activity on that blockchain. ETH, SOL, and BNB are all examples of layer-1 tokens.

### Next Steps
* Consider adding your tokenomics skills to your application materials.

* Remember, you have access to your Career Coach for up to three months after graduation. Schedule a meeting to discuss how you would like to work with them post-graduation.
