# Start Here

UE Seller Preflight Kit is a local Unreal Engine 5 editor plugin for checking common project and code-plugin submission-readiness issues before you package your work.

It is for Unreal Engine sellers, technical artists, solo developers, and small teams who want a practical local report for structure, metadata, naming, redirectors, documentation, listing support, and package hygiene.

Version: 1.0.0
Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

This plugin is independent and unofficial. It is not affiliated with Epic Games, Unreal Engine, or Fab. It does not guarantee Fab approval and does not replace the requirements published for Fab.

## 5-Step First Workflow

1. Install the plugin into your project `Plugins/UESellerPreflightKit` folder and enable it in Unreal Editor.
2. Open `Tools > UE Seller Preflight Kit`.
3. Choose `Current Project`, `This Plugin`, or `Manual Path`.
4. Click `Scan`, then select a result to read the details, suggested fix, and source reference.
5. Choose an export folder and use `Export Markdown`, `Export CSV`, or `Export JSON`.

## What To Read Next

- New user: read [QuickStart](QuickStart.html).
- Understanding results: read [RuleReference](RuleReference.html).
- Something failed: read [Troubleshooting](Troubleshooting.html).
- Checking limits: read [KnownLimitations](KnownLimitations.html).
- Support and trust: read [Support](Support.html) and [AITransparency](AITransparency.html).

## Safety Notes

- Normal scan/export is non-destructive.
- The plugin does not upload files.
- The plugin does not call AI services.
- The plugin does not use cloud services.
- The plugin does not intentionally collect telemetry.
- Redirectors are report-only in V1; use Unreal Editor's normal Content Browser Fix Up Redirectors workflow manually.
- Documentation template generation is explicit, confirmation-gated, and refuses overwrites.
- Export overwrite requires user opt-in through `Allow overwrite`.
- Reports are guidance/checklists, not approval certificates.

