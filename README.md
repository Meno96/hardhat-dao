<h1 align="center">
    Hardhat DAO
</h1>

<br/>

This project shows how to make a DAO
 
<hr/>

## 🗎&nbsp; Requirements
- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
    You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
    
- [Nodejs](https://nodejs.org/en/)

    You'll know you've installed nodejs right if you can run: `node --version` and get an ouput like: `vx.x.x`
- [Yarn](https://yarnpkg.com/getting-started/install) instead of `npm`
   
   You'll know you've installed yarn right if you can run: `yarn --version` and get an output like: `x.x.x`
   
   You might need to [install it with `npm`](https://classic.yarnpkg.com/lang/en/docs/install/) or `corepack`

## 🛠️&nbsp; How to run
- Clone the repo:
    ```
    git clone https://github.com/Meno96/hardhat-smartcontract-lottery.git
    ```
- Enter the directory:
    ```
    cd hardhat-smartcontract-lottery
    ```
- Install packages:
    ```
    yarn
    ```

### Run the test suite (which also has all the functionality)

  ```
  yarn hardhat test
  ```
or

  ```
  npx hardhat test
  ```

### If you want to deploy to a testnet:

Add a `.env` file with the same contents of `.env.example`, but replaced with your variables.
![WARNING](https://via.placeholder.com/15/f03c15/000000?text=+) **WARNING** ![WARNING](https://via.placeholder.com/15/f03c15/000000?text=+)
> DO NOT PUSH YOUR PRIVATE_KEY TO GITHUB


## 🚀&nbsp; How it's suppose to work?

### On-Chain Governance Example

Here is the rundown of what the test suite does. 

1. We will deploy an ERC20 token that we will use to govern our DAO.
2. We will deploy a Timelock contract that we will use to give a buffer between executing proposals.
   - Note: **The timelock is the contract that will handle all the money, ownerships, etc**
3. We will deploy our Governence contract 
   - Note: **The Governance contract is in charge of proposals and such, but the Timelock executes!**
4. We will deploy a simple Box contract, which will be owned by our governance process! (aka, our timelock contract).
5. We will propose a new value to be added to our Box contract.
6. We will then vote on that proposal.
7. We will then queue the proposal to be executed.
8. Then, we will execute it!

#### Additionally, you can do it all manually on your own local network like so:

1. Setup local blockchain 

    ```
    yarn hardhat node
    ```

2. Propose a new value to be added to our Box contract

    In a second terminal (leave your blockchain running)

    ```
    yarn hardhat run scripts/propose.ts --network localhost
    ```

3. Vote on that proposal

    ```
    yarn hardhat run scripts/vote.ts --network localhost
    ```

4. Queue & Execute proposal!

    ```
    yarn hardhat run scripts/queue-and-execute.ts --network localhost
    ```

You can also use the [Openzeppelin contract wizard](https://wizard.openzeppelin.com/#governor) to get other contracts to work with variations of this governance contract. 

## 📫&nbsp; Have a question? Want to chat? 

[LinkedIn](https://www.linkedin.com/in/daniele-menin/)

[Instagram](https://www.instagram.com/danielemeno96/)

