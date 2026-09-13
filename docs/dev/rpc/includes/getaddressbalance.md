## getaddressbalance
Returns the balance for an address(es) (requires addressindex to be enabled).

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | addresses | json array | False |  |  |
| **Addresses** |  |  |  |  |  |
| 1.1 | address | string | False |  | The base58check encoded address. |
| 2 | asset | string | False | RTM | Get balance for a particular asset instead of RTM. ("*" for all assets) |

### Result for RTM:
```json
{                             (json object)
  "balance" : n,              (numeric) The current total balance in duffs
  "balance_immature" : n,     (numeric) The current immature balance in duffs
  "balance_spendable" : n,    (numeric) The current spendable balance in duffs
  "received" : n              (numeric) The total number of duffs received (including change)
}
```
### Result for assets:
```json
{                               (json object)
  "asset name" : {              (json object)
    "balance" : n,              (numeric) The current total balance in duffs
    "balance_immature" : n,     (numeric) The current immature balance in duffs
    "balance_spendable" : n,    (numeric) The current spendable balance in duffs
    "received" : n              (numeric) The total number of duffs received (including change)
  }
```

### Examples
```bash
 raptoreum-cli getaddressbalance '{"addresses": ["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"]}'
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressbalance", "params": [{"addresses": ["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"]}] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```

