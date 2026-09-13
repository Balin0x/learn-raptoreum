## generatetoaddress
Mine blocks immediately to a specified address (before the RPC call returns)

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | nblocks | numeric | True |  | How many blocks are generated immediately. |
| 2 | address | string | True |  | The address to send the newly generated RTM to. |
| 3 | maxtries | numeric | False | 1000000 | How many iterations to try. |

### Result
```json
[           (json array) hashes of blocks generated
  "hex",    (string) blockhash
  ...
]
```
### Examples

Generate 11 blocks to myaddress:

```bash
 raptoreum-cli generatetoaddress 11 "myaddress"
```

If you are running the Raptoreum Core wallet, you can get a new address to send the newly generated coins to with:

```bash
 raptoreum-cli getnewaddress
```

