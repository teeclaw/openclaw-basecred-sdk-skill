# Changelog

All notable changes to basecred-sdk-skill will be documented in this file.

## [1.0.1] - 2026-02-10

### Changed
- Updated `@basecred/sdk` from v0.6.1 to v0.6.2
- **Bug fix:** Neynar/Farcaster scores now return actual decimal values (e.g., 0.43) instead of rounded integers
- This provides more accurate Farcaster quality scores

### Verified
- ✅ All tests passing with v0.6.2
- ✅ Decimal precision working correctly (e.g., 0.43 instead of 0)
- ✅ No breaking changes to skill code
- ✅ Output format unchanged

## [1.0.0] - 2026-02-10

### Added
- Initial release
- CLI interface for checking reputation via Ethos, Talent Protocol, and Farcaster
- Summary and full profile output modes
- Human-readable and JSON output formats
- Graceful degradation with partial data sources
- Comprehensive documentation (SKILL.md, README.md)
- Test suite with known addresses
- Integration library for other skills
