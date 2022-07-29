# hardhat-defi-fcc

FreeCodeCamp blockchain course - Lesson 13 Hardhat Defi and Aave

## Timestamps and notes

-   aave docs https://docs.aave.com/developers/getting-started/readme
-   The aave protocol treats everything as an ERC20 token
-   Wrapped Ether ("WETH") = Ethereum but in an ERC20 token contract

19:40 Forking from mainnet

-   Hardhat docs https://hardhat.org/hardhat-network/docs/guides/forking-other-networks
-   Pros: Quick, easy and resembles whats on mainnet
-   Cons: We need an API, some contracts are complex to work with
-   `yarn hardhat run .\scripts\aaveBorrow.js`

19:45 Depositing into Aave

-   NOTE - uses v2 of the docs in this tutorial
-   Use the LendingPool contract
-   Need to use the LendingPoolAddressesProvider to get the address
-   https://docs.aave.com/developers/v/2.0/the-core-protocol/addresses-provider
-   copy in the contract interface - https://docs.aave.com/developers/v/2.0/the-core-protocol/addresses-provider/ilendingpooladdressesprovider
-   Get copy of the ILendingPool
-   https://docs.aave.com/developers/v/2.0/the-core-protocol/lendingpool/ilendingpool
-   `yarn add --dev @aave/protocol-v2`
-   update the imports on the solidity ILendingPool.sol file to point to node modules
-   check by running `yarn hardhat compile`

19:57 Borrowing from Aave

-   Link to get Chainlink - https://docs.chain.link/docs/ethereum-addresses/
-   Get the address for DAI on mainnet
-   Just reading from the contract so don't need a signer (deployer)
-   dai token address from mainnet
-   https://ww7.etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f?a=0x8a91c9a16cd62693649d80afa85a09dbbdcb8508

20:12 Repaying with Aave

-   Note there is a small amount borrowed remaining, which represents interest accrued

20:14 Visualizing the transactions (And aTokens)

20:19 Speed Run Ethereum - Austin Griffith

-   https://speedrunethereum.com/
-   scaffold-eth https://github.com/scaffold-eth/scaffold-eth#-scaffold-eth
