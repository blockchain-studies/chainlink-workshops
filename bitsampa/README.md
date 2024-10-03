# BitSampa CCIP Workshop 

Wallet Account on Avalanche Fuji: `0x732903f195c27C45Aa86a2045aa160442608F21A`

Wallet Account on Sepolia: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64`

Original tutorial: https://cll-devrel.gitbook.io/ccip-bootcamp/day-3/exercise-4-sending-usdc-cross-chain

- LINK Token Contracts: https://docs.chain.link/resources/link-token-contracts
- Fuji faucet: https://core.app/tools/testnet-faucet?subnet=c&token=c 
- USDC Faucet: https://faucet.circle.com
- LINK on Fuji faucet: https://faucets.chain.link/fuji
- Necessary CCIP Token: https://docs.chain.link/ccip/test-tokens#mint-test-tokens
- Contract Funding: https://docs.chain.link/resources/fund-your-contract

# CCIP
- Architecture: https://docs.chain.link/ccip/architecture#token-pools
- Concepts Overview: https://docs.chain.link/ccip/concepts#lane
- CCIP Explorer: https://ccip.chain.link

# Setup
### 1. Deploy Contract On Avalanche Fuji

- Avalanche Fuji Router Address (`ccipRouter`): `0xF694E193200268f9a4868e4Aa017A0118C9a8177`
- LINK on Avalanche Fuji Address (`linkToken`): `0x0b9d5D9136855f6FEc3c0993feE6E9CE8a297846`
- USDC Token on Avalanche Fuji Address (`usdcToken`): `0x5425890298aed601595a70AB815c96711a31Bc65`

- TransferUSDC Contract Address: `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369`(It was deployed on Avalanche Fuji)
- - Transaction: https://testnet.snowtrace.io/tx/0x08611bf65d60374eed9f1c5f3bc422053f1aa2f91956d458b1996ebf7fde9b09
- - Contract: https://testnet.snowtrace.io/address/0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369

### 2. On AvalancheFuji, call allowlistDestinationChain function
- Destination Chain Selector (`_destinationChainSelector`): `16015286601757825753` (Enable the contract to transfer tokens to Ethereum Sepolia)
- `_allowed`: `true`

### 3. On AvalancheFuji, fund TransferUSDC.sol with 3 LINK
- On the Wallet, send LINK to the contract: `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369`
- Transaction: https://testnet.snowtrace.io/tx/0x08611bf65d60374eed9f1c5f3bc422053f1aa2f91956d458b1996ebf7fde9b09

### 4. On Avalanche Fuji, call approve function on USDC.sol
- Go to: https://testnet.snowtrace.io/address/0x5425890298aed601595a70AB815c96711a31Bc65/contract/43113/writeProxyContract?chainId=43113
- Choice `Write As A Proxy`
- Connect the Wallet to the Snowtrace Block Explorer
- In the `approve` function, approve, for the use of:
- - Spender (the contract deployed before): `0xFA4cbCD6Fe6c79E0Fb0442C2729c7E17Db60B369`
- - Amount: `5000000` (5 USDC is allowed to be transferred)
- Approve the transaction in the Wallet

### 5. On AvalancheFuji, call transferUsdc function
- Find the transferUsdc function and provide:
- - CCIP Chain Selector for the Ethereum Sepolia test network, as the `_destinationChainSelector` parameter: `16015286601757825753`
- - Your wallet address, as the `_receiver` parameter: `0xE5435Db2b26a59083788cA861e7f86CF7338CF64` (Sepolia Receiver Account - `EOA`) (An `EOA` isn't able to receive data, in this case, only the token will be transferred) 
- - As the `_amount` parameter: `5000000` (6 digits, 5 USDC)
- - As the `_gasLimit` parameter: `0` (`0` is set as the `_gasLimit` parameter because we are sending tokens to an EOA so there is no cost for executing the ccipReceive function on the destination side)

- Import the USDC token address on Sepolia network into the Wallet (import token option): `0x1c7D4B196Cb0C7B01d743Fbc6116a902379C7238`

- Transaction:
- - CCIP Explorer: https://ccip.chain.link/msg/0x73a031ec1db951ab07491de5cae155e9fcc7bfba0c8d65f3eec5fb961514fdc4 
- - Snowtrace Explorer: https://testnet.snowtrace.io/tx/0x75caea3b9adcb2e25eccc578f774ba38badbb63f1d18ef41e25986495dd1b224
- - Sepolia Explorer: https://sepolia.etherscan.io/tx/0xdbeafdf2b7cc476f82e52a4533d5b293e3e48805d3845ccc23a0786f0995feba 


