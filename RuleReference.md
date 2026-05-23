# Rule Reference

This reference explains the UE Seller Preflight Kit 1.0.0 rule categories. Exported reports are versioned guidance for the installed plugin version.

Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

UE Seller Preflight Kit is independent and unofficial. Results are local guidance only and do not guarantee Fab approval.

## Severities

| Severity | Meaning | Typical response |
|---|---|---|
| Blocker | The scan target or input is unusable, or a manifest cannot be parsed. | Fix before relying on later results. |
| Error | A required structure or manifest issue is likely to block packaging or review readiness. | Fix before packaging a release candidate. |
| Warning | A hygiene, documentation, listing, or review issue needs attention. | Review and fix when relevant. |
| Info | Context or review reminder. | Read and decide whether action is needed. |

## Rule Areas

| Rule area | What it checks | Typical severity | Fix approach | Limitation |
|---|---|---|---|---|
| Target classification | Whether the scan path exists and looks like an Unreal project or code plugin root. | Blocker for missing/invalid paths; Info for recognized targets. | Choose a folder containing a `.uproject` or `.uplugin`, or use `Current Project`. | Classification does not prove the product is ready; later rules handle details. |
| Structure | Required plugin/project layout. Code plugin structure checks include `.uplugin`, `Source`, `Content`, `Config`, and at least one code module. Content product checks include `.uproject`, `Content`, and `Config`; content should be under one top-level pack folder. | Error or Blocker for missing required items. | Add missing folders/manifests/modules manually and rescan. | It checks filesystem shape, not whether every asset inside is useful. |
| Metadata | `.uplugin` JSON parsing, required metadata fields, module type, and `EnabledByDefault` review. | Blocker for invalid JSON; Error for missing modules or non-Editor module review; Warning for missing fields; Info for `EnabledByDefault`. | Fix the manifest in source control and rebuild/package. | It does not validate every possible Unreal plugin descriptor field. |
| Naming hygiene | File and folder names using ASCII letters, numbers, underscores, and hyphens; spaces; non-ASCII characters; invalid symbols; number-only names. | Warning. | Rename through Unreal Editor or normal source-control workflows so references stay intact. | It cannot fully judge English wording or descriptive intent. |
| Placeholder names | Obvious placeholder names such as `NewFolder`, `Untitled`, `Temp`, `Test`, `Copy`, `Placeholder`, `Example`, and `Default`. | Warning. | Replace placeholder names with specific product, feature, or asset names. | Some placeholder-like names may be intentional; review manually. |
| Redirectors | `UObjectRedirector` assets discovered under scanned content package paths. Redirectors are packaging hygiene findings. | Warning. | Use Unreal Editor's normal Content Browser Fix Up Redirectors workflow manually after review. | V1 reports redirectors only. It does not fix, save, delete, or modify assets. |
| Folder hygiene | Empty folders and generated/output folders such as `Saved`, `Intermediate`, `DerivedDataCache`, `.vs`, `Binaries`, report folders, and packaged output folders. | Warning. | Review release package contents and remove accidental output manually outside the scan. | Empty folders can be intentional; the tool only flags them for review. |
| Documentation readiness | Expected buyer docs such as README, QuickStart, RuleReference or FeatureReference, Changelog, KnownIssues or KnownLimitations, support/contact information, and unofficial/no-guarantee wording. | Warning. | Add or complete documentation. Use `Generate Doc Template` only after selecting a documentation result and confirming the write. | The tool checks presence and basic text signals; it cannot judge full documentation quality. |
| Listing helpers | Demo script review, media checklist, technical details, and version notes. For Tools & Plugins, a demo map is not required by default unless demonstrable elements exist. | Info or Warning. | Add review files such as `Docs/DemoScript.md`, `Listing/MediaChecklist.md`, `Listing/TechnicalDetails.md`, and `Listing/VersionNotes.md` when relevant. | These are listing-support reminders, not mandatory claims unless backed by current marketplace requirements. |

## Appendix: Current Rule IDs

The current source includes these rule IDs:

- `SPK.PATH.TARGET_CLASSIFICATION`
- `SPK.PATH.TARGET_MISSING`
- `SPK.PATH.TARGET_INVALID`
- `SPK.PATH.TARGET_UNCLASSIFIED`
- `SPK.STRUCTURE.REQUIRED_LAYOUT`
- `SPK.STRUCTURE.PLUGIN_MANIFEST`
- `SPK.STRUCTURE.PLUGIN_REQUIRED_DIRS`
- `SPK.STRUCTURE.PLUGIN_MODULE`
- `SPK.STRUCTURE.MODULE_LAYOUT`
- `SPK.STRUCTURE.PROJECT_MANIFEST`
- `SPK.STRUCTURE.PROJECT_REQUIRED_DIRS`
- `SPK.STRUCTURE.CONTENT_PACK_ROOT`
- `SPK.METADATA.UPLUGIN`
- `SPK.METADATA.UPLUGIN_JSON`
- `SPK.METADATA.UPLUGIN_REQUIRED_FIELDS`
- `SPK.METADATA.MODULE_TYPE`
- `SPK.METADATA.ENABLED_BY_DEFAULT`
- `SPK.HYGIENE.NAMING`
- `SPK.HYGIENE.PLACEHOLDER_NAME`
- `SPK.HYGIENE.REDIRECTOR`
- `SPK.HYGIENE.FOLDER`
- `SPK.HYGIENE.EMPTY_FOLDER`
- `SPK.HYGIENE.RELEASE_JUNK_FOLDER`
- `SPK.DOCS.READINESS`
- `SPK.DOCS.REQUIRED_FILES`
- `SPK.DOCS.SUPPORT_CONTACT`
- `SPK.DOCS.UNOFFICIAL_DISCLAIMER`
- `SPK.LISTING.READINESS`
- `SPK.LISTING.DEMO_REVIEW`
- `SPK.LISTING.SUPPORT_FILES`

## Source References

Every result includes a source reference. References may point to:

- `Docs/RuleReference.md`
- `Docs/RuleSources.md`
- `Docs/KnownLimitations.md`
- `Docs/Troubleshooting.md`

Where rules mention marketplace requirements, the wording is summarized in `Docs/RuleSources.md`. Always verify current public requirements before submission.

