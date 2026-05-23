# Rule Sources

Version: 1.0.0  
Publisher: Toolsmith Studio  
Support: toolsmithstudio@proton.me  
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

Every scan result includes a source reference. A source reference tells you which buyer-facing note explains why the finding exists and how to interpret it.

Source references are not approval certificates. They are short pointers for review. Always verify current marketplace requirements before final submission.

## Source Reference Files

- `Docs/RuleReference.md`: rule categories, severities, examples, safe fix approach, and current rule IDs.
- `Docs/RuleSources.md`: public-requirement areas and how the plugin uses them.
- `Docs/KnownLimitations.md`: product limits, heuristic checks, and report-only behavior.
- `Docs/Troubleshooting.md`: practical scan/export failure handling.

## Public Requirement Areas Used By V1

The V1 checks are based on public Unreal Engine marketplace/Fab preparation themes recorded for this product:

| Area | How the plugin uses it |
|---|---|
| Code plugin structure | Code plugin roots are expected to have a `.uplugin`, `Source/`, `Content/`, `Config/`, and at least one code module. |
| Content project structure | Content product candidates are expected to be Unreal projects with `.uproject`, `Content/`, and `Config/`. |
| Pack folder organization | Content products are easier to review and package when product content sits under one top-level pack folder. |
| Plugin metadata | `.uplugin` files should parse as JSON and contain clear name, description, category, version, and module metadata. |
| Naming hygiene | File and folder names should be consistent, descriptive, and safe for Unreal workflows. The plugin flags spaces, non-ASCII names, unusual symbols, numeric-only names, and obvious placeholders for review. |
| Redirectors | Redirector assets are packaging hygiene findings. V1 reports them only and tells users to use Unreal Editor's normal fix-up workflow manually. |
| Documentation readiness | Buyer/reviewer docs should explain installation, usage, rules/features, limitations, support, and version changes. |
| Listing support | Media checklists, technical details, version notes, and demo/overview notes help prepare a clear listing. Some listing helpers are review prompts, not mandatory claims. |

## Safe Interpretation

- Blockers and errors should be reviewed before packaging a release candidate.
- Warnings are review prompts. Some may be acceptable after manual review.
- Info results provide context or reminders.
- Suggested fixes are intentionally non-destructive. The plugin does not delete, rename, move, save, or fix assets automatically during scan/export.

