# BitSampa CCIP Workshop 

Wallet Account on Avalanche Fuji: `0x732903f195c27C45Aa86a2045aa160442608F21A`

Wallet Account on Sepolia: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64`

Original tutorial: https://cll-devrel.gitbook.io/ccip-bootcamp/day-3/exercise-4-sending-usdc-cross-chain

- LINK Token Contracts: https://docs.chain.link/resources/link-token-contracts
- Fuji faucet: https://core.app/tools/testnet-faucet?subnet=c&token=c 
- LINK on Fuji faucet: https://faucets.chain.link/fuji
- Necessary CCIP Token: https://docs.chain.link/ccip/test-tokens#mint-test-tokens
- Contract Funding: https://docs.chain.link/resources/fund-your-contract

# CCIP
- Architecture: https://docs.chain.link/ccip/architecture#token-pools
- Concepts Overview: https://docs.chain.link/ccip/concepts#lane

# Setup
### 1. Deploy Contract On Avalanche Fuji

- Avalanche Fuji Router Address (`ccipRouter`): `0xF694E193200268f9a4868e4Aa017A0118C9a8177`
- LINK on Avalanche Fuji Address (`linkToken`): `0x0b9d5D9136855f6FEc3c0993feE6E9CE8a297846`
- USDC Token on Avalanche Fuji Address (`usdcToken`): `0x5425890298aed601595a70AB815c96711a31Bc65` 

- TransferUSDC Contract Address: `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369` (It was deployed on Avalanche Fuji)

### 2. On AvalancheFuji, call allowlistDestinationChain function
- Destination Chain Selector (`_destinationChainSelector`): `16015286601757825753` (Enable the contract to transfer tokens to Ethereum Sepolia)
- `_allowed`: `true`

### 3. On AvalancheFuji, fund TransferUSDC.sol with 3 LINK
- On the Wallet, send LINK to the contract: `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369`
- Transaction: https://testnet.snowtrace.io/tx/0x08611bf65d60374eed9f1c5f3bc422053f1aa2f91956d458b1996ebf7fde9b09

### 4. On AvalancheFuji, call transferUsdc function
- Find the transferUsdc function and provide:
- - CCIP Chain Selector for the Ethereum Sepolia test network, as the `_destinationChainSelector` parameter: `16015286601757825753`
- - Your wallet address, as the `_receiver` parameter: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64` (Sepolia Receiver Account - `EOA`)
- - As the `_amount` parameter: `1000000` (6 digits, 1 USDC)
- - As the `_gasLimit` parameter: `0` (`0` is set as the `_gasLimit` parameter because we are sending tokens to an EOA so there is no cost for executing the ccipReceive function on the destination side)


### Transfer tokens and pay in LINK
- Funding Contract with LINK: https://testnet.snowtrace.io/tx/0x9c50b3ea2080bbf7bd641e3a29e28c75b0a2e2585eb9852ca380ee5610a0c25f
- CCIP-BnM Transaction to Sepolia (CCIP Explorer): https://ccip.chain.link/msg/0x3fc1c79f1886d71cebca6b6ad28a4aa17357deedede6f650c153cc7a6524ce3e
- Sepolia EtherScan: https://sepolia.etherscan.io/tx/0x76394134d9539b8f64100fd3498495d438f69f372690b81c6a0c5969c31e45a0

### Transfer tokens and pay in native
- Funding Contract with AVAX (native token): https://testnet.snowtrace.io/tx/0x72f451cc32068a11ee483fd6931274c5cd04079f34147c0f009d2a993b9a888d
- Transfer Token CCIP-BnM: https://testnet.snowtrace.io/tx/0x717ab1a6cce4a52f873813fcfeb7b5174305929a9a5db04d290d0a08c7a1b4fb
- CCIP Explorer: https://ccip.chain.link/msg/0xa438316ee394d8606e78a873b3e859b88b417ea52aa276787a6aeb575f61ad01
- Sepolia EtherScan: https://sepolia.etherscan.io/tx/0x824da2c687c725f6935f405c8fd51c109663aa4812d91b41e315d2522637afce

