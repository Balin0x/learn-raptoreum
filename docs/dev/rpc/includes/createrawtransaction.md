## createrawtransaction
Create a transaction spending the given inputs and creating new outputs.
Outputs can be addresses or data.
Returns hex-encoded raw transaction.
Note that the transaction's inputs are not signed, and
it is not stored in the wallet or transmitted to the network.
### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | inputs | json array | True |  | A json array of json objects |
| **Inputs** |  |  |  |  |  |
| 1.1 | txid | string | True |  | The transaction id. |
| 1.2 | vout | numeric | True |  | The output number. |
| 1.3 | sequence | numeric | False |  | The sequence number. |
| 2 | outputs | json array | True |  | a json array with outputs (key-value pairs). |
| **Outputs** |  |  |  |  |  |
| 2.1 | address | numeric or string | True |  | A key-value pair. The key (string) is the Raptoreum address, the value (float or string) is the amount in RTM. |
|  |  |  |  |  |  |
| 2.2 | future_maturity | numeric | True |  | Number of confirmation for this future to mature. |
| 2.3 | future_locktime | numeric | True |  | Total time in seconds from its first confirmation for this future to mature. |
| 2.4 | future_amount | numeric | True |  | Raptoreum amount to be locked. |
|  |  |  |  |  |  |
| 2.5 | assetid | string | True |  | The asset identifier. |
| 2.6 | uniqueid | numeric |  |  | The asset unique id. |
| 2.7 | amount | numeric or string | True |  | Amount to send. |
| 2.8 | future_maturity | numeric |  |  | Number of confirmation for this future to mature. |
| 2.9 | future_locktime | numeric |  |  | Total time in seconds from its first confirmation for this future to mature. |
|  |  |  |  |  |  |
| 2.10 | data | string | True |  | A key-value pair. The key must be "data", the value is hex-encoded data. |
| 3 | locktime | numeric | False | 0 | Raw locktime. Non-0 value also locktime-activates inputs |
### Result
```json
"hex"    (string)  hex string of the transaction
```
### Examples
```bash
 raptoreum-cli createrawtransaction "[{\"txid\":\"myid\",\"vout\":0}]" "[{\"address\":0.01}]"
```
```bash
 raptoreum-cli createrawtransaction "[{\"txid\":\"myid\",\"vout\":0}]" "[{\"data\":\"00010203\"}]"
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": ["[{\"txid\":\"myid\",\"vout\":0}]", "[{\"address\":0.01}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": ["[{\"txid\":\"myid\",\"vout\":0}]", "[{\"data\":\"00010203\"}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```

