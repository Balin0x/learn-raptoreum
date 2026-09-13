## disconnectnode
Immediately disconnects from the specified peer node.
Strictly one out of 'address' and 'nodeid' can be provided to identify the node.
To disconnect by nodeid, either set 'address' to the empty string, or call using the named 'nodeid' argument only.

### Arguments
| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | address | string | False | fallback to nodeid | The IP address/port of the node |
| 2 | nodeid | numeric | False | fallback to address | The node ID (see getpeerinfo for node IDs) |
### Result
```json
null    (json null)
```
### Examples
```bash
 raptoreum-cli disconnectnode "192.168.0.6:9999"
```
```bash
 raptoreum-cli disconnectnode "" 1
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": ["192.168.0.6:9999"] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": ["", 1] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```

