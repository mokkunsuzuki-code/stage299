# Stage299: Signature-Aware Gate

Stage299 builds on the public verification URL structure from Stage288 and adds the QSP/VEP Gate engine.

## Core Decision

```python
if signature_valid:
    decision = "accept"
elif verification_ok:
    decision = "pending"
else:
    decision = "reject"
Meaning
Decision	Meaning
accept	Evidence is valid and signature is valid
pending	Evidence is valid, but signature is missing or not yet verified
reject	Evidence is invalid or unsafe
Why This Stage Matters

Stage288 showed a public verification URL.

Stage299 adds the Gate engine.

This means the verification page can now decide:

accept
pending
reject

This is the bridge to Stage300, where an AI vulnerability verification URL can pass through the Gate and display accept.

Security Policy

Private keys are not included in this repository.

The repository excludes:

keys/
*.pem
*.key
*.p12
*.pfx
.env
local SSH keys
License

MIT License

Copyright (c) 2025 Motohiro Suzuki
