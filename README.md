# basecred-sdk-skill

**OpenClaw skill for checking human reputation via Ethos Network, Talent Protocol, and Farcaster.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Quick Start

```bash
# Install dependencies
npm install

# Check reputation for an address
./scripts/check-reputation.mjs 0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045

# Run tests
npm test
```

## What This Does

Fetches neutral, composable reputation data from:

- ✅ **Ethos Network** - Social credibility (no API key needed)
- ✅ **Talent Protocol** - Builder & creator scores (requires API key)
- ✅ **Farcaster (Neynar)** - Account quality (requires API key)

Returns raw scores, levels, and signals—**no rankings, no judgments**.

## Example Output

```json
{
  "address": "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045",
  "timestamp": "2026-02-10T07:00:00.000Z",
  "availability": {
    "ethos": "not_found",
    "talent": "available",
    "farcaster": "available"
  },
  "data": {
    "talent": {
      "builderScore": 86,
      "builderLevel": "Practitioner",
      "builderRank": 8648,
      "creatorScore": 103,
      "creatorLevel": "Established"
    },
    "farcaster": {
      "score": 1,
      "passesQuality": true
    }
  },
  "recency": "recent"
}
```

## Setup

### Prerequisites

- Node.js 18+
- OpenClaw runtime

### Optional API Keys

Add to your `.env` file:

```bash
# Optional: Enables Talent Protocol scores
TALENT_API_KEY=your_talent_api_key

# Optional: Enables Farcaster quality scores
NEYNAR_API_KEY=your_neynar_api_key
```

Get keys:
- Talent Protocol: https://talentprotocol.com
- Neynar: https://neynar.com

**Note:** Ethos Network requires no API key.

## Usage

```bash
# Summary (default)
./scripts/check-reputation.mjs 0x...

# Full unified profile
./scripts/check-reputation.mjs 0x... --full

# Human-readable format
./scripts/check-reputation.mjs 0x... --human

# Help
./scripts/check-reputation.mjs --help
```

## Features

- ✅ Graceful degradation (works with partial data)
- ✅ Never crashes (structured error responses)
- ✅ JSON and human-readable output
- ✅ Summary and full profile modes
- ✅ Semantic levels (Novice → Master, etc.)
- ✅ Recency buckets (recent/stale/dormant)

## What This Does NOT Do

- ❌ Decide trustworthiness
- ❌ Rank users
- ❌ Compare users
- ❌ Produce composite scores
- ❌ Replace human judgment

## Documentation

See [SKILL.md](SKILL.md) for complete documentation.

## Source SDK

This skill wraps [@basecred/sdk](https://www.npmjs.com/package/@basecred/sdk).

Source repository: https://github.com/Callmedas69/basecred/tree/main/packages/sdk

## License

MIT

## Author

Built by **teeclaw** for OpenClaw.
