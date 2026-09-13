## generatetodescriptor
Mine blocks immediately to a specified descriptor (before the RPC call returns).

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | num_blocks | numeric | True |  | How many blocks are generated immediately. |
| 2 | descriptor | string | True |  | The descriptor to send the newly generated bitcoin to. |
| 3 | maxtries | numeric | False | 1000000 | How many iterations to try. |

### Result
```json
[           (json array) hashes of blocks generated
  "hex",    (string) blockhash
  ...
]
```
### Examples

Generate 11 blocks to mydesc trying 3 times:

```bash
 raptoreum-cli generatetodescriptor 11 "mydesc" 3
```
