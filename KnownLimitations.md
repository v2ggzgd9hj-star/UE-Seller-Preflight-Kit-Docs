# Known Limitations

Version: 1.0.0  
Publisher: Toolsmith Studio  
Support: toolsmithstudio@proton.me  
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

UE Seller Preflight Kit is independent and unofficial. It is not affiliated with Epic Games, Unreal Engine, or Fab. It does not guarantee approval and does not replace the current requirements published by the marketplace.

The plugin runs locally in Unreal Editor. Normal scan/export does not modify assets or packages. The plugin does not upload project files, call AI services, use cloud services, or intentionally collect telemetry.

## Product Limits

- Generated reports are guidance/checklists, not approval certificates.
- The plugin does not submit listings or upload project files.
- Documentation and listing checks are heuristic. They can tell whether expected files or text signals exist, but they cannot judge whether every document is complete or persuasive.
- Naming checks can find spaces, non-ASCII names, symbols, numeric-only names, and obvious placeholder names. They cannot fully judge whether a name is descriptive English.
- Redirectors are report-only in V1. Use Unreal Editor's normal Content Browser Fix Up Redirectors workflow manually after reviewing the warning.
- The plugin does not judge listing media quality, image composition, trailer quality, or marketing strength.
- The plugin does not detect legal, licensing, trademark, copyright, tax, payout, or account issues.
- The plugin does not determine whether every asset is unused.
- `Open Location` supports local file/folder paths only. Object paths such as `/Game/...` are not opened.
- `Generate Doc Template` creates starter text only after confirmation and refuses overwrites. Replace template text with product-specific information before release.

## How To Use These Limits

Treat findings as a structured review pass before packaging/submission. Fix clear structure and manifest issues first, then use warnings as prompts for manual review. Always compare final decisions against current marketplace requirements.

