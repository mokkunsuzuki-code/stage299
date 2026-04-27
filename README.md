# Stage299: Signature-Aware Verification Gate

Stage299 completes the QSP/VEP Gate engine.

It builds on the public verification URL structure from Stage288 and adds a clear decision layer:

- `accept`
- `pending`
- `reject`

## Core Gate Logic

```python
if signature_valid:
    decision = "accept"
elif verification_ok:
    decision = "pending"
else:
    decision = "reject"
Decision Meaning
Decision	Meaning
accept	Evidence is valid and signature is valid
pending	Evidence is valid, but signature is missing or not yet verified
reject	Evidence is invalid or unsafe
What Stage299 Adds

Stage288 showed a public verification URL.

Stage299 adds the Gate.

This means QSP/VEP can now move from:

showing evidence

to:

making a policy-based decision
Why This Matters

The Gate is the engine.

It allows a verification system to decide whether evidence should pass, wait, or fail.

This creates the foundation for Stage300:

AI vulnerability URL
→ Gate verification
→ accept / pending / reject
Security Policy

This repository does not include private keys.

The repository excludes:

keys/
*.pem
*.key
*.p12
*.pfx
.env
local SSH keys

Fail-closed behavior is enabled.

If required evidence is invalid, the Gate must not accept it.

Stage Role
Stage288 = public verification URL
Stage299 = Gate engine
Stage300 = AI vulnerability verification showcase
License

MIT License

Copyright (c) 2025 Motohiro Suzuki
