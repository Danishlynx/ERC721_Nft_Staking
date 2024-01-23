# ERC20-ERC721 NFT Staking System

This project consists of three Ethereum smart contracts designed to create an ERC20 token, an ERC721 NFT token, and a staking system that allows users to stake their ERC721 NFTs in exchange for ERC20 tokens. The system allows users to receive NFTs and withdraw ERC20 tokens as rewards at regular intervals.

## Smart Contracts

### 1. MyToken (ERC20)
- **Name:** MyToken
- **Symbol:** MT

This smart contract represents an ERC20 token called "MyToken" with the symbol "MT."
- Users can mint MT tokens using the `mint` function, where they provide the recipient's address and the amount of tokens to mint.
- The `spendAllowance` function allows users to spend MT tokens by specifying the allowance granted by another user.
- To withdraw NFTs, users must use the `approveTokenTransfer` function to approve token transfers from their account.

### 2. MyNftContract (ERC721)
- **Name:** MyNftContract
- **Symbol:** MNC

This smart contract represents an ERC721 NFT contract called "MyNftContract" with the symbol "MNC."
- Users can mint NFTs using the `mint` function, which increments the NFT ID and mints NFTs to the specified recipient's address.
- The `tokenURI` function returns the URI of the metadata associated with a specific NFT.
- The `_baseURI` function defines the base URI for the metadata associated with NFTs.

### 3. MyAuthorityContract
- **Name:** MyAuthorityContract

This smart contract serves as the authority contract that coordinates the staking and rewards distribution process.
- It holds references to the MyToken and MyNftContract instances.
- Users can mint NFTs using the `mintNft` function. This involves spending MT tokens to mint NFTs.
- Users can stake their NFTs using the `stakeNft` function. The contract keeps track of the staked NFTs and their owners.
- To claim staking rewards, users can use the `claimStakingRewards` function. Rewards are calculated based on the number of staked NFTs and the time elapsed since the last claim.
- The contract ensures that only the NFT owner can unstake their NFTs using the `unstakeNft` function.
- Users must approve token transfers before staking using the `approveTokenTransfer` function.
- The contract implements the `onERC721Received` function to receive NFTs.

## Testing

To test this system, you can deploy these contracts on an Ethereum test network or a local development environment like Remix. Make sure to adjust the `TIME_PER_DAY` constant for testing purposes to have shorter time intervals.

Here's a basic overview of the workflow:

1. Mint MT tokens using the `mint` function in the MyToken contract.
2. Mint NFTs using the `mint` function in the MyNftContract.
3. Stake NFTs using the `stakeNft` function in the MyAuthorityContract.
4. Claim rewards using the `claimStakingRewards` function after the specified time period.

Ensure you have MT tokens and NFTs in your Ethereum wallet before testing these functionalities.

Feel free to customize and extend the contracts as needed for your specific use case.

Please note that this README provides an overview of the project's structure and functionality. It's essential to thoroughly test the contracts and ensure they meet your specific requirements before deploying them on the Ethereum mainnet or any production environment.
