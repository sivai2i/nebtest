# Nebtest

NebTest will automate unit testing of nebulas smart contracts.

# Features

* With NebTest, we can automate smart contract testing on both testnet and mainnet.
* Run test case with multiple test data sets at a time.
* Run test cases in clean state, by deploying a smart contract before each test case.

# Pre-requisites

* node >= 8.10.3 [(Download the latest node version here)](https://nodejs.org/en/download/)

# Methods

|   Name	|   Parameters	|  Return 	|  Description 	|
|---	|:----:|:----:|---	|
|   createNewAccount	|  - 	|  Account 	|   Creates a new account from wallet	|
|  transferToken 	|  to, token  |  -	|   Send token to the given address from wallet	|
|  deployContract 	|  fileName	|  - 	|  Deploy the contract file |
|  callContract 	|   value, call	|  transaction 	|  Call the specified methods with arguments 	|
|  transact 	|   value, call	|  receipt 	|  Returns the transaction receipt 	|

# Getting Started

1. **Install**  
  npm install --save nebtest  
  npm install --save mocha chai

2. **Include nebtest to your test case**  
  const Nebtest = require('nebtest');

3. **Export variables**  

    Download and follow the instructions to create a web-wallet [https://github.com/nebulasio/web-wallet](https://github.com/nebulasio/web-wallet)  

    Create a wallet  

    <img src="https://raw.githubusercontent.com/Ideas2IT/nebtest/master/screenshot/web-wallet.png" />

    From the wallet info, you will get the wallet details  

    <img src="https://raw.githubusercontent.com/Ideas2IT/nebtest/master/screenshot/wallet-info.png" />

    export ENVIRONMENT='testnet'  
    export SOURCEACCOUNT='wallet private key'  
    export COINBASE='wallet address'

4. **Mock Contract**  
    Place your contract files in test directory
    ```
        test/contracts/contractFile.js
    ```

5. **Test data**  
    Place your test data in test directory
    ```
        test/testCases.json
    ```

6. **Test data - sample format**
    ```
    const testData = [
      {
        name: 'Test Case Description',
        data: [
          {
            name: 'Test data name',
            testInput: {
              ...test inputs
            },
            testExpect: {
              ...test result expect
            }
          }
        ]
      }
    ```
7. **Test Cases**  
    Write your test cases in
    ```
        test/test.js
    ```

8. **Run test**

    Add following command to scripts. The timeout is based on the mining time of the contract you are running. Increase the timeout if you are getting the timeout error.

    ```
    "scripts": {
      ...
      "test": "mocha --timeout 600000"
    }
    ```
    Run the test as,

    ```
      npm run test
    ```

# Example

  Check here for a complete [example](https://github.com/Ideas2IT/nebtest/tree/master/example)

  **Test Result**  

  <img src="https://raw.githubusercontent.com/Ideas2IT/nebtest/master/screenshot/example.png" />
  
# Resources

  [Steps for creating nebulas web wallet](https://medium.com/nebulasio/creating-a-nas-wallet-9d01b5fa2df6)

  [To claim free nebulas tokens](https://testnet.nebulas.io/claim/https://testnet.nebulas.io/claim/)
