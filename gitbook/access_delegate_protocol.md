# Access Delegate Protocol

## Introduction
At present, the most major NFT Token standard -- ERC721 does not assign role rights to NFT tokens, such as access rights， right of use and editing rights but only one owner, which undoubtedly increases the threshold of entry for many projects. We cannot directly modify ERC721 standard, but we can develop protocols like Access Delegate Protocol (Hereinafter referred to as ADP) to make NFT tokens as if they have these roles in terms of security and business cooperation, so as to lower the threshold for participation in various projects or games, and thus to increase liquidity.

## Terminology
**Pool** for ADP is a container for user assets which could be a NFT Token or a contract.

## ADP with NFT Token Pool
As shown in the picture above, NFT tokens will be transferred to ADP Token Pool from lender and ADP will record a rental data rather than send the token to the renter. The main process is as follows:
1. Alice delegate an NFT token to ADP.
2. Bob rent an NFT token from ADP.
3. Project partners query ADP by using the AccessDelegate-Javascript-SDK and allow Bob to login in with the token he rented from RentFun.

### Reward Split
1. 
