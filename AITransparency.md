# AI Transparency

AI-assisted engineering tools were used during development of UE Seller Preflight Kit.

Version: 1.0.0
Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

UE Seller Preflight Kit is independent and unofficial. It is not affiliated with Epic Games, Unreal Engine, or Fab, and it does not guarantee Fab approval.

The shipped plugin itself does not:

- call AI services
- upload project files
- use cloud inference
- use cloud services
- intentionally collect telemetry

The plugin is a local Unreal Editor workflow: it scans local project/plugin structure, creates rule results, shows those results in Slate UI, and exports Markdown, CSV, and JSON reports.

## What Buyers Are Paying For

Buyers are paying for the tested, curated workflow:

- source-backed rule categories
- deterministic scan results
- readable UI triage
- safe suggested fixes
- report exports
- documentation
- known limitations
- support for plugin behavior

They are not paying for hidden AI behavior inside Unreal Editor. There is no AI assistant, AI scan, or cloud inference in the plugin.

## Testing And Review

Version 1.0.0 was checked through Unreal build and automation workflows, fixture-style scans, report export checks, actionability checks, and manual editor workflow review.

These checks support the shipped workflow, but they do not turn generated reports into approval certificates. Always compare findings against the current requirements published by the marketplace.

