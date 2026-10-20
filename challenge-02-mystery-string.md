# Challenge 02 — Mystery String

**Category:** Encoding vs Encryption

## Objective
Identify and decode an encoded string to recover the CTF flag.

## Payload
```text
Q09FUHtiYXN1NjRfaXNfbm90X2VuY3J5cHRpb259
```

The challenge hints at Base64 and suggests `base64 --decode`.

## Investigation
Run this in a Linux terminal:

```bash
echo 'Q09FUHtiYXN1NjRfaXNfbm90X2VuY3J5cHRpb259' | base64 --decode
```

The decoded output is:

```text
COEP{basu64_is_not_encryption}
```

Copy the decoded text exactly; the spelling in the challenge's flag is `basu64`.

## Flag
`COEP{basu64_is_not_encryption}`

## What I Learned
- Base64 is an encoding scheme, not encryption.
- Decoding Base64 does not require a secret key.
- Encoding should not be used to protect confidential information.

## Tool
- Linux `base64` command
- Alternative: CyberChef's “From Base64” operation
