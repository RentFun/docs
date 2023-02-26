# Introduction
The RentFun-Js-SDK was developed to make RentFun easy for all partners to integrate.

## Description of Core Functions

1. Fetch rental information
    > Partners may only need to call this one interface
    
   NFT issuers can easily fetch a player's rental information to determine whether to allow the player to log in or not.
    
2. Lend an NFT token(ERC721 standard)
    
    NFT holders can lend out their NFT tokens to earn a rental profit.
    RentFun will create a vault contract for each lender to keep lender's NFT tokens and the lender will be the only owner of the vault contract, and no one can transfer the tokens except its owner.
    
3. Rent an NFT token

    Renters for example, a newcomer of an NFT token based game player can play the game for a small rental fee.
    The NFT tokens will be locked in the lender's vault contract for a full rental term.
    
4. Cancel lend an NFT token
    Lenders can cancel lend an NFT token, while existing alive rentals will not be affected.
    
5. Check if a token is rented
    
    
    
    