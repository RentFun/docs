# interfaces

> This section is a work in progress..

## getAliveRentals

**getAliveRentals**(renter: string, contract: string) => Promise<{renter: string; contract: string; tokenId: number; vault: string; endTime: number;}[]>

Returns unexpired rentals for a given renter and an ERC721 contract address.

**Inputs** 
    
|    |    |
| :------------ | :------------ |
|renter    |The address of renter   |
|contract    |The address of an ERC721 contract     |

**Outputs**
> An array of structs, here are the members of the structure.

|    |    |
| :------------ | :------------ | 
|renter    |The address of renter    |
|contract    |The address of an ERC721 contract    |
|tokenId    |The token's ID    |
|vault    |Lender's vault contract which holds the rented token    |
|endTime    |A timestamp of the end of the rental    |

```
if (endTime < Math.ceil(Date.now() / 1000)) {
    // The rent is expired
} else {
    // allow to login with the tokenID 
}
```

## Usage Example
```
const rfun = new RentFun();
const renter = "0x0000000000000000000000000000000000000001";
const contract = "0x0000000000000000000000000000000000000002";
const aliveRentals = await rfun.getAliveRentals(renter, contract);

/* returns example
[
    {
        renter: "0x0000000000000000000000000000000000000001",
        contract = "0x0000000000000000000000000000000000000002"
        tokenId: 1,
        vault: "0x0000000000000000000000000000000000000003",
        endTime: 1676534925
    }
]
*/
```

## lend

**lend**(contract: string, tokenId: number, payment: string, unitFee: number) => Promise< void >

lend an NFT token. Lend can also use this to change the payment method and the unitFee. Just lend again.

|    |    |
| :------------ | :------------ |
|contract    |The address of an ERC721 contract     |
|tokenId    |The token's ID   |
|payment    |The address of an ERC20 token to pay the rental fee, address(0) means pay with ether.   |
|unitFee    |The price per unit of rental time   |

**Lend Example**
 ```
const rfun = new RentFun();
//
const contract = "0x0000000000000000000000000000000000000002";
const tokenId = 1;
const payment = "0x0000000000000000000000000000000000000003";
const unitFee = 10000000000000
await rfun.lend(contract, tokenId, payment, unitFee);
```

## rent

**rent**(contract: string, tokenId: number, amount: number) => Promise< void >

rent an NFT token.

|    |    |
| :------------ | :------------ |
|contract    |The address of an ERC721 contract     |
|tokenId    |The token's ID   |
|amount    | The number of rentals for a unit of rental time  |

**Rent Example**
 ```
const rfun = new RentFun();
//
const contract = "0x0000000000000000000000000000000000000002";
const tokenId = 1;
const amount = 3;
await rfun.rent(contract, tokenId, amount);
```

## cancelLend

**cancelLend**(contract: string, tokenId: number) => Promise< void >
    
cancel lend an NFT token, existing alive rentals will not be affected.

|    |    |
| :------------ | :------------ |
|contract    |The address of an ERC721 contract     |
|tokenId    |The token's ID   |

**cancelLend**
 ```
const rfun = new RentFun();
//
const contract = "0x0000000000000000000000000000000000000002";
const tokenId = 1;
await rfun.cancelLend(contract, tokenId);
```

## isRented

**isRented**(contract: string, tokenId: number) => Promise< boolean >
    
check if a token is rented

|    |    |
| :------------ | :------------ |
|contract    |The address of an ERC721 contract     |
|tokenId    |The token's ID   |

**isRented**
 ```
const rfun = new RentFun();
//
const contract = "0x0000000000000000000000000000000000000002";
const tokenId = 1;
await rfun.isRented(contract, tokenId);

/* returns example
true
*/
```











