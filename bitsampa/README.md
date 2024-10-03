# BitSampa CCIP Workshop 

Wallet Account on Avalanche Fuji: `0x732903f195c27C45Aa86a2045aa160442608F21A`

Wallet Account on Sepolia: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64`

Original tutorial: https://cll-devrel.gitbook.io/ccip-bootcamp/day-3/exercise-4-sending-usdc-cross-chain

- LINK Token Contracts: https://docs.chain.link/resources/link-token-contracts
- Fuji faucet: https://core.app/tools/testnet-faucet?subnet=c&token=c 
- LINK on Fuji faucet: https://faucets.chain.link/fuji
- Necessary CCIP Token: https://docs.chain.link/ccip/test-tokens#mint-test-tokens
- Contract Funding: https://docs.chain.link/resources/fund-your-contract

# Setup
### Deploy Contract On Avalanche Fuji

- Avalanche Fuji Router Address (`ccipRouter`): `0xF694E193200268f9a4868e4Aa017A0118C9a8177`
- LINK on Avalanche Fuji Address (`linkToken`): `0x0b9d5D9136855f6FEc3c0993feE6E9CE8a297846`
- USDC Token on Avalanche Fuji Address (`usdcToken`): `0x5425890298aed601595a70AB815c96711a31Bc65` 
- Destination Chain Selector: `16015286601757825753` (Enable the contract to transfer tokens to Ethereum Sepolia)
- Sepolia Receiver Account: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64`

- TransferUSDC Contract Address: `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369` (It was deployed on Avalanche Fuji)

### Transfer tokens and pay in LINK
- Funding Contract with LINK: https://testnet.snowtrace.io/tx/0x9c50b3ea2080bbf7bd641e3a29e28c75b0a2e2585eb9852ca380ee5610a0c25f
- CCIP-BnM Transaction to Sepolia (CCIP Explorer): https://ccip.chain.link/msg/0x3fc1c79f1886d71cebca6b6ad28a4aa17357deedede6f650c153cc7a6524ce3e
- Sepolia EtherScan: https://sepolia.etherscan.io/tx/0x76394134d9539b8f64100fd3498495d438f69f372690b81c6a0c5969c31e45a0

### Transfer tokens and pay in native
- Funding Contract with AVAX (native token): https://testnet.snowtrace.io/tx/0x72f451cc32068a11ee483fd6931274c5cd04079f34147c0f009d2a993b9a888d
- Transfer Token CCIP-BnM: https://testnet.snowtrace.io/tx/0x717ab1a6cce4a52f873813fcfeb7b5174305929a9a5db04d290d0a08c7a1b4fb
- CCIP Explorer: https://ccip.chain.link/msg/0xa438316ee394d8606e78a873b3e859b88b417ea52aa276787a6aeb575f61ad01
- Sepolia EtherScan: https://sepolia.etherscan.io/tx/0x824da2c687c725f6935f405c8fd51c109663aa4812d91b41e315d2522637afce

## CCIP
- Architecture: https://docs.chain.link/ccip/architecture#token-pools
- Concepts Overview: https://docs.chain.link/ccip/concepts#lane