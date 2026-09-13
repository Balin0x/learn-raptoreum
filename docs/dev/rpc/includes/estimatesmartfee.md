## estimatesmartfee
Estimates the approximate fee per kilobyte needed for a transaction to begin
confirmation within conf_target blocks if possible and return the number of blocks
for which the estimate is valid.

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | conf_target | numeric | True |  | Confirmation target in blocks (1 - 1008) |
| 2 | estimate_mode | string | False | CONSERVATIVE | The fee estimate mode. |

### Result
```json
{                   (json object)
  "feerate" : n,    (numeric, optional) estimate fee rate in RTM/kB
  "errors" : [      (json array) Errors encountered during processing
    "str",          (string) error
    ...
  ],
  "blocks" : n      (numeric) block number where estimate was found
                    The request target will be clamped between 2 and the highest target
                    fee estimation is able to return based on how long it has been running.
                    An error is returned if not enough transactions and blocks
                    have been observed to make an estimate for any number of blocks.
}
```
### Examples
```bash
 raptoreum-cli estimatesmartfee 6
```

