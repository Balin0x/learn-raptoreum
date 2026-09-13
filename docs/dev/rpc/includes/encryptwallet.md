## encryptwallet
Encrypts the wallet with 'passphrase'. This is for first time encryption.
After this, any calls that interact with private keys such as sending or signing
will require the passphrase to be set prior the making these calls.
Use the walletpassphrase call for this, and then walletlock call.
If the wallet is already encrypted, use the walletpassphrasechange call.

### Arguments

| Position | Name | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | passphrase | string | True |  | The pass phrase to encrypt the wallet with. It must be at least 1 character, but should be long. |

### Result
```json
"str"    (string) A string with further instructions
```

### Examples

Encrypt your wallet
```bash
 raptoreum-cli encryptwallet "my pass phrase"
```

Now set the passphrase to use the wallet, such as for signing or sending raptoreum
```bash
 raptoreum-cli walletpassphrase "my pass phrase"
```

Now we can do something like sign
```bash
 raptoreum-cli signmessage "address" "test message"
```

Now lock the wallet again by removing the passphrase
```bash
 raptoreum-cli walletlock
```

As a JSON-RPC call
```bash
 curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "encryptwallet", "params": ["my pass phrase"] }' -H 'content-type: text/plain;' http://127.0.0.1:10225/
```

---
