# Changelog

## 1.0.0

Initial buyer-facing release of UE Seller Preflight Kit.

Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

Included:

- Editor-only Unreal Engine plugin with `Tools > UE Seller Preflight Kit` menu entry.
- Local scan workflow for `Current Project`, `This Plugin`, and `Manual Path`.
- Result summary, severity/category filters, result table, details panel, suggested fixes, and source references.
- V1 rule categories:
  - target classification
  - required structure
  - `.uplugin` metadata
  - naming hygiene
  - redirectors
  - folder hygiene
  - documentation readiness
  - listing helpers
- Markdown, CSV, and JSON report exports.
- Safe helper actions for copying suggested fixes, opening affected folders, and confirmation-gated documentation template generation.
- Buyer documentation for install, use, rules, troubleshooting, support, known limits, and AI transparency.

## Important Limits

- UE Seller Preflight Kit is unofficial and independent.
- It is not affiliated with Epic Games, Unreal Engine, or Fab.
- It does not guarantee Fab approval.
- It does not upload data, call AI services, use cloud services, or intentionally collect telemetry.
- Redirectors are report-only in V1 and must be fixed manually through Unreal Editor if needed.

