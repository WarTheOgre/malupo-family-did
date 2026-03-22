# Malupo Family Decentralized Identifiers

This repository hosts the **did:web** decentralized identifiers for the Malupo family.

## Family Members

- **Warren Malupo** - `did:web:malupo.family:warren`
- **Kim Malupo** - `did:web:malupo.family:kim`
- **Al Malupo** - `did:web:malupo.family:al`
- **Marcus Malupo** - `did:web:malupo.family:marcus`
- **Data Malupo** 🐕 - `did:web:malupo.family:data`
- **Claw Malupo** 🦞 - `did:web:malupo.family:agents:claw` *(OpenClaw Agent)*

## About

Established: **March 20, 2026**

The Malupo family DIDs are cryptographically verifiable identities anchored to the malupo.family domain and backed by Ed25519 key pairs.

Each family member has:
- A `did:web` identifier (web-resolvable via HTTPS)
- A `did:key` identifier (cryptographic self-sovereignty)
- Public/private key pair (Ed25519)

## Resolution

DIDs can be resolved via standard HTTPS:

```bash
curl https://malupo.family/warren/did.json
curl https://malupo.family/agents/claw/did.json
```

## Family Registry

View the complete family registry at:
- https://malupo.family/family-registry.json

## Motto

**"Ohana means family. Family means nobody gets left behind."**

---

*This repository is hosted on GitHub Pages and serves as the authoritative source for Malupo family decentralized identifiers.*
