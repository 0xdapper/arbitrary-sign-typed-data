# Sign Typed Data Debug Tool

> [!CAUTION] > **NEVER SIGN TYPED DATA WITHOUT CAREFULLY READING AND UNDERSTANDING THE CONTENT FIRST**
> Signing messages without verification can lead to loss of funds or unauthorized access to your assets. Always thoroughly review the typed data structure and content before signing.

A minimal utility dapp for testing and debugging EIP-712 typed structured data signing. Allows developers to quickly test typed data signatures by pasting JSON messages and signing them with a connected wallet.

## Features

- Connect any Web3 wallet
- Paste arbitrary EIP-712 typed data JSON
- Sign messages and view resulting signatures
- Simple error handling for JSON validation and signing issues

## Usage

1. Connect your Web3 wallet
2. Paste your typed data JSON into the textarea. Example format:

```json
{
  "types": {
    "Person": [
      { "name": "name", "type": "string" },
      { "name": "wallet", "type": "address" }
    ],
    "Mail": [
      { "name": "from", "type": "Person" },
      { "name": "to", "type": "Person" },
      { "name": "contents", "type": "string" }
    ]
  },
  "primaryType": "Mail",
  "message": {
    "from": {
      "name": "Cow",
      "wallet": "0xCD2a3d9F938E13CD947Ec05AbC7FE734Df8DD826"
    },
    "to": {
      "name": "Bob",
      "wallet": "0xbBbBBBBbbBBBbbbBbbBbbbbBBbBbbbbBbBbbBBbB"
    },
    "contents": "Hello, Bob!"
  }
}
```

3. Click "Sign Typed Data" to trigger the signing request
4. View the resulting signature displayed below

Built with React and wagmi hooks.
