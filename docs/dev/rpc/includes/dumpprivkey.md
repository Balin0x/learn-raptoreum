## dumpprivkey
Reveals the private key corresponding to 'address'.
Then the importprivkey can be used with this output.

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | address | string | True |  | The Raptoreum address for the private key |
### Result
```json
"str"    (string) The private key
```
### Examples
```bash
 raptoreum-cli dumpprivkey "myaddress"
```
```bash
 raptoreum-cli importprivkey "mykey"
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "dumpprivkey", "params": ["myaddress"] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```

