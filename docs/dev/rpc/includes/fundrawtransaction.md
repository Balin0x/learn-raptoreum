## fundrawtransaction
Add inputs to a transaction until it has enough in value to meet its out value.
This will not modify existing inputs, and will add at most one change output to the outputs.
No existing outputs will be modified unless "subtractFeeFromOutputs" is specified.
Note that inputs which were signed may need to be resigned after completion since in/outputs have been added.
The inputs added will not be signed, use signrawtransactionwithkey
 or signrawtransactionwithwallet for that.
Note that all existing inputs must have their previous output transaction be in the wallet.
Note that all inputs selected must be of standard form and P2SH scripts must be
in the wallet using importaddress or addmultisigaddress (to calculate fees).
You can see whether this is the case by checking the "solvable" field in the listunspent output.
Only pay-to-pubkey, multisig, and P2SH versions thereof are currently supported for watch-only.

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | hexstring | string | True |  | The hex string of the raw transaction |
| 2 | options | json object | False |  | for backward compatibility: passing in a true instead of an object will result in {"includeWatching":true} |
| **Options** |  |  |  |  |  |
| 2.1 | changeAddress | string | False | pool address | The Raptoreum address to receive the change. |
| 2.2 | changePosition | numeric | False | random | The index of the change output. |
| 2.3 | includeWatching | boolean | False | False | Also select inputs which are watch only. |
| 2.4 | lockUnspents | boolean | False | False | Lock selected unspent outputs. |
| 2.5 | feeRate | numeric or string | False | not set: makes wallet determine the fee | Set a specific fee rate in RTM/kB. |
| 2.6 | subtractFeeFromOutputs | json array | False | empty array | A json array of integers. |
| 2.7 | conf_target | numeric | False | fallback to wallet's default | Confirmation target (in blocks). |
| 2.8 | estimate_mode | string | False | UNSET | The fee estimate mode, must be one of:. |

### Result
```json
{                     (json object)
  "hex" : "hex",      (string) The resulting raw transaction (hex-encoded string)
  "fee" : n,          (numeric) Fee in RTM the resulting transaction pays
  "changepos" : n     (numeric) The position of the added change output, or -1
}
```
### Examples

 Create a transaction with no inputs

```bash
 raptoreum-cli createrawtransaction "[]" "{\"myaddress\":0.01}"
```

 Add sufficient unsigned inputs to meet the output value

```bash
 raptoreum-cli fundrawtransaction "rawtransactionhex"
```

 Sign the transaction

```bash
 raptoreum-cli signrawtransaction "fundedtransactionhex"
```

 Send the transaction

```bash
 raptoreum-cli sendrawtransaction "signedtransactionhex"
```

