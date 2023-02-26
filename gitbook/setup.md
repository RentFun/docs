# Setup

> This section is a work in progress..

### Custom Provider URL

By default, the [default provider](https://docs.ethers.org/v5/api/providers/#providers-getDefaultProvider) is automatically used when initiating `accessdelegate`
```
import { RentFun } from "rentfun";
const rfun = new RentFun();
```

A custom provider can be assigned as the following example:
```
import { ethers } from "ethers";
import { RentFun } from "rentfun";
const provider = new ethers.providers.JsonRpcProvider('https://arb-mainnet.g.alchemy.com/v2/-KEY', 'any');
const rfun = new RentFun(provider);
```

If you are using this in a Node environment as a backend service, you can also assign a provider with the PROVIDER_URL environment variable.
```
# .env
PROVIDER_URL="https://arb-mainnet.g.alchemy.com/v2/-KEY"
```
