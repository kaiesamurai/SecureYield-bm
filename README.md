### SecureYield: Decentralized Insurance for DeFi Investments

### About the Project
SecureYield is designed to alleviate the fear of losing crypto assets in DeFi protocols by providing a decentralized insurance solution. By leveraging Chainlink's Proof-of-Reserve (PoR) and Proof-of-Supply (PoS) technology, SecureYield offers parametric insurance to protect against catastrophic events, encouraging more users to participate in DeFi lending.

### Inspiration
The DeFi ecosystem, despite its rapid growth and high yields, lacks sufficient insurance coverage for "Black Swan" events. Traditional insurance processes, which involve cumbersome claims procedures, do not align with the automated nature of DeFi. To address this, we developed SecureYield, a parametric risk management product that uses smart contracts to offer real-time protection for stablecoin assets like TUSD.

### What It Does
SecureYield provides automated risk management by:
1. **Accepting Deposits**: Users deposit their funds into the SecureYield smart contract.
2. **Lending Funds**: The smart contract transfers these funds to a DeFi protocol like Aave.
3. **Monitoring Data Feeds**: Using Chainlink's PoR and PoS data feeds, the contract monitors the stability of TUSD. If PoR is significantly lower than PoS, the contract withdraws funds from Aave and returns them to the user.
4. **Protection Against Hacks**: The smart contract also monitors the reserves of the DeFi protocol's wallet to detect any irregularities.
5. **User Control**: Users can withdraw their funds and accrued interest at any time, ensuring flexibility and control over their investments.

### How We Built It
SecureYield was developed using:
- **Solidity**: For writing the smart contracts.
- **Chainlink**: To access PoR and PoS data feeds.
- **Scaffold-Eth**: For the development framework.
- **IPFS**: For decentralized hosting of the project website.
- **Hardhat**: For testing and deployment.

### Challenges We Ran Into
- **Data Feeds**: No TUSD PoR/PoS data feeds on the Kovan testnet required us to create custom external adapters.
- **Economic Structuring**: Defining payout conditions and fee structures proved complex.
- **Interest Harvesting**: Integrating a system for the smart contract to collect a portion of the interest from Aave proved challenging.

### Accomplishments That We're Proud Of
- Successfully developed a parametric insurance smart contract that reacts to real-time data.
- Achieved end-to-end security and automated risk management without the need for a claims process.
- Enabled instant withdrawals and interest collection for users.

### What We Learned
- **Complexity of Insurance**: Creating robust insurance products for DeFi requires detailed parameterization.
- **Collaboration**: Working as a remote team, we learned to overcome technical and logistical challenges.
- **DeFi Ecosystem**: Gained deep insights into DeFi protocols, data feeds, and smart contract integration.

### What's Next for SecureYield
1. **Mainnet Deployment**: Launch on Ethereum or other EVM-compatible blockchains.
2. **Expanded Coverage**: Include more stablecoins and DeFi protocols.
3. **Enhanced Monitoring**: Incorporate additional parameters for detecting money laundering and other risks.
4. **Economic Structuring**: Develop sustainable fee models to ensure the protocol's longevity.
5. **Donation Mechanism**: Allow donors to sponsor wallets, creating a financial protection system for individuals in emerging markets.

### Built With
- **ethers.js**
- **figma**
- **google-docs**
- **hardhat**
- **ipfs**
- **javascript**
- **lucid-chart**
- **powerpoint**
- **scaffold-eth**
- **solidity**


### Requirements
- Node 12

### Installation
1. Install dependencies:
   ```bash
   yarn install
   ```

2. Test Smart Contract:
   ```bash
   yarn test
   ```

### Run Locally
The project comes with a set of "mock" contracts that are configured during local deployment. These mock contracts correspond to:
- TUSD Reserve Feed
- TUSD Supply Feed
- TUSD ERC20 Token

The project also includes a Mock Protocol defining its own Mock Reserve Token (equivalent to aTokens, cTokens, and yTokens).

#### Steps to Run Locally:
1. Ensure `defaultNetwork` in `hardhat.config.js` is set to `localhost` and `targetNetwork` in `App.jsx` is set to `NETWORKS['localhost']`.

2. Run the local Hardhat Network:
   ```bash
   yarn chain
   ```

3. Deploy contracts to the local Hardhat Network:
   ```bash
   yarn deploy
   ```

4. Run the frontend:
   ```bash
   yarn start
   ```

### Run on Kovan Testnet
The deployment script for Kovan sets the addresses for the following contracts:
- TUSD Reserve Feed
- TUSD Supply Feed
- TUSD ERC20 Token
- AAVE Lending Protocol
- AAVE Data Provider

Mock feeds are also deployed to simulate PoR/PoS mismatch.

#### Steps to Run on Kovan:
1. Ensure `defaultNetwork` in `hardhat.config.js` is set to `kovan` and `targetNetwork` in `App.jsx` is set to `NETWORKS['kovan']`.

2. Generate a deployment account:
   ```bash
   yarn generate
   ```

3. Send some Kovan ETH to the generated account.

4. Deploy contracts to Kovan:
   ```bash
   yarn deploy
   ```

5. Run the frontend:
   ```bash
   yarn start
   ```

6. Deploy to IPFS:
   ```bash
   yarn ipfs
   ```

### Debug Panel
Deployer accounts will have access to a Debug Panel where they can trigger certain events and manipulate the deployed smart contracts directly through this UI. The link to the Debug Panel is located in the website's footer.

### Uniswap Branch
There is a `uniswap` branch that is a work in progress (WIP). This branch aims to modify the workflow in the case of a TUSD PoR/PoS event by converting the user's TUSD to WETH.

### Try It Out
Explore SecureYield and safeguard your DeFi investments with our decentralized insurance protocol. Join us in making DeFi a safer and more accessible space for everyone!