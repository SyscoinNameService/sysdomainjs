# Syscoin Name Service

Nodejs SDK

Npm: https://www.npmjs.com/package/sysdomainjs

Github: https://github.com/SyscoinNameService/sysdomainjs

Before installing the package you need to check and be sure to install the packages below:

```
npm install web3 
```

Install Package

```
npm install sysdomainjs
```

Call 
```
const domainjs = require('sysdomainjs');
```

Set config

contractAddress: "0xA1019535E6b364523949EaF45F4B17521c1cb074"

https://explorer.syscoin.org/token/0xA1019535E6b364523949EaF45F4B17521c1cb074

```
const config = 
{
	testnet:{
		rpcUrl: "",
		contractAddress: ""
	},
	mainnet:{ 
		rpcUrl: "https://rpc.syscoin.org/",
		contractAddress: "0xA1019535E6b364523949EaF45F4B17521c1cb074"
	},
	defaultNetwork: "mainnet"
}
```

Install

```
   // install
	const sdk = domainjs.SDK(config);

	// change your domains
	const _domain = "sysdomains.sys";
	
	// change your address
	const _address = "0xbb48801EAF9947db8b49a96DEA231C5893125B9c";
	
	// resolve domain to get the address of the owner. metadata: true // false default return metadata along with domain information
	const owner = await sdk.getOwner(_domain, false);

	console.log(owner);

	// get total domains
	const balance = await sdk.balanceOf(_address);

	console.log(balance);

	// get a domain default from a user's address, requiring the user to set the default domain name initially.
	const domain = await sdk.getDomain(_address);

	console.log(domain);
	
	// gets all the domains owned by an wallet address.
	const domains = await sdk.getDomains(_address);

	console.log(domains);
	
	//get a value of metadata from the domain name
	const _avatar = await sdk.getMetadata("avatar", _domain);

	console.log(_avatar);
	
	//get values of metadata from the domain name
	const _values = await sdk.getMetadatas(["avatar", "website", "social:twitter"], _domain);

	console.log(_values);
	
	//namehash is a recursive process that can generate a unique hash for any valid domain name.
	const hashname = await sdk.hashname(_domain);

	console.log(hashname);
```

Pls update test.js for specific instructions

Thanks!



