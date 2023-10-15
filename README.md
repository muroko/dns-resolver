# Dnero Name Service - DNS Resolver

###### This NPM can be used to retrieve an address from a DNS or a DNS from an address on the Dnero Blockchain.
###### It can also retrieve a list of domain names from a list of addresses.

### Installation
To install dns-resolver use the following statement:
```console
npm install dns-resolver
```

### Import and instanciate DNS
To import and instanciate dns-resolver use the following statement:
```js script
import DNS from "dns-resolver";

const dns = new DNS();
```

### Get domain name from an address
To get the domain name from an address use the ```getDomainName``` function such as: 
```js script
import DNS from 'dns-resolver';

const address = '0x123...';
const dns = new DNS();
const domainName = await dns.getDomainName(address);
console.log(domainName);
/* will return the domain name 
 or null if no domain name is assigned to this address
 i.e. will log 'domainname.dnero' or null */
```

### Get address from a domain name
To get the address from a domain name use the ```getAddress``` function such as:
```js script
import DNS from 'dns-resolver';

const domainName = 'test.dnero';
const dns = new DNS();
const address = await dns.getAddress(domainName);
console.log(address);
/* will return the address or null if the domain
is not assigned to an address
i.e. will log '0x123...' or null */
```

### Get domain names for a list of addresses
If you need to process many addresses (eg: showing domain names of transaction histories), use the ```getDomainNames``` function such as: 
```js script
import DNS from 'dns-resolver';

const addresses = ['0x123...', '0x456...'];
const dns = new DNS();
const domainNames = await dns.getDomainNames(addresses);
console.log(domainNames);
/* will return an object where the key is the address
 and the value is the domain name or an empty string if no domain name is assigned on this address
 i.e. will log { "0x123...": "domainname.dnero", "0x456...": "" } */
```

### Instanciate DNS with a custom RPC endpoint
To instanciate dns-resolver using a custom RPC endpoint use the following statement:
```js script
import DNS from "dns-resolver";

const dns = new DNS({customRpcEndpoint: 'YOUR_CUSTOM_RPC_ENDPOINT_HERE'});
```
