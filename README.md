# DocShield (RedactFlow SDK)

Ultra-fast, zero-server client-side PII/PHI Image & Document Redaction SDK. 
Designed for FinTech, InsurTech, and MedTech to detect and black-box mask sensitive data (< 50ms) entirely on-device.

Copyright (c) 2026 Emirhan CAMCI <byemir@live.com>

## Features

- **On-Device Execution**: Runs completely inside the browser (WASM) or natively (C-ABI) without sending unmasked data to any server.
- **Ultra-Fast Performance**: Zero-copy pixel buffer manipulation allowing redaction in under 50ms.
- **Zero Memory Leaks**: Predictable buffer allocations suitable for high-throughput mobile environments.

## Editions

| Feature | Community (AGPLv3) | Pro / Enterprise (Commercial) |
| --- | --- | --- |
| Basic Regex OCR (TCKN, IBAN) | ✅ | ✅ |
| Single-page Image Masking | ✅ | ✅ |
| Dynamic Signature & Face Detection | ❌ | ✅ |
| Multi-page Vector PDF Redaction | ❌ | ✅ |
| Contextual NLP Field Matching | ❌ | ✅ |
| SIMD Acceleration & Multi-threading| ❌ | ✅ |
| Offline Ed25519 License Validation| ❌ | ✅ |

> **Pro / Enterprise License**: Buy a license via [Polar.sh](https://polar.sh/) to unlock advanced features.

## Quickstart

```typescript
import { DocShieldClient } from 'docshield-wasm';

// 1. Initialize the engine (Loads WASM)
const shield = new DocShieldClient();

// 2. Pass your image buffer directly from a canvas or file
// Redacts PII in-place (zero-copy) in <50ms
shield.redact_document(imageData.data, imageWidth, imageHeight);

// 3. Render or upload the safe, redacted imageData
ctx.putImageData(imageData, 0, 0);
```

## Dual Licensing

- `docshield-core`: Open source under AGPLv3.
- `docshield-pro`: Proprietary closed-source extensions. Requires a valid offline license key.
