# QuickStart

This guide gets a first-time user from installation to an exported report.

Version: 1.0.0
Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

UE Seller Preflight Kit is unofficial and independent. It is not affiliated with Epic Games, Unreal Engine, or Fab. It does not guarantee Fab approval and does not replace the requirements published for Fab.

The plugin runs locally inside Unreal Editor. It does not upload data, call AI services, use cloud services, or intentionally collect telemetry.

## Install From A Packaged Plugin

1. Close Unreal Editor.
2. Extract or copy the packaged plugin folder named `UESellerPreflightKit`.
3. Put it here:

```text
%PROJECT_ROOT%/Plugins/UESellerPreflightKit
```

4. Open your `.uproject` in Unreal Editor.
5. If Unreal asks to rebuild modules, allow it only if you are set up to build C++ plugins.
6. Open `Edit > Plugins`.
7. Search for `UE Seller Preflight Kit`.
8. Enable the plugin.
9. Restart Unreal Editor if prompted.

## Install From A Project Plugins Folder

Use this when you are testing a local copy of the plugin source:

1. Close Unreal Editor.
2. Create a `Plugins` folder beside your `.uproject` if it does not exist.
3. Copy the plugin folder into:

```text
%PROJECT_ROOT%/Plugins/UESellerPreflightKit
```

4. Open the project in Unreal Editor.
5. Enable `UE Seller Preflight Kit` in the Plugins window if needed.
6. Restart when prompted.

## First Scan In 5 Minutes

1. Open your project in Unreal Editor.
2. Choose `Tools > UE Seller Preflight Kit`.
3. In `Scan scope`, choose one option:
   - `Current Project`: scan the currently open Unreal project root.
   - `This Plugin`: scan the installed UE Seller Preflight Kit plugin folder.
   - `Manual Path`: scan a typed project or plugin root path.
4. If using `Manual Path`, type the root folder that contains the `.uproject` or `.uplugin`.
5. Click `Scan`.
6. Read the summary line. It shows total results plus Blocker, Error, Warning, and Info counts.
7. Use `Severity` and `Category` filters to narrow the result list.
8. Select a result row.
9. Read the details panel:
   - affected path
   - details
   - suggested fix
   - source reference
10. Choose an `Export folder`.
11. Click `Export Markdown`, `Export CSV`, and `Export JSON` as needed.

Normal scan/export does not modify project assets. It does not delete, rename, move, save packages, check out files, fix redirectors, or generate documentation templates.

## Result Review

The results table shows:

- `Severity`
- `Rule ID`
- `Title`
- `Affected Path`

The details panel shows the selected issue in more detail, including the suggested fix and source reference.

Use `Copy Suggested Fix` to copy the suggested fix text to your clipboard.

Use `Open Location` to open a local folder in your file browser. If the affected path is a file, the plugin opens the parent folder. Object paths such as `/Game/...` are not opened.

Use `Generate Doc Template` only when a selected Documentation or Listing result points to a missing `.md`, `.markdown`, or `.txt` file. The plugin asks for confirmation, writes a clearly marked template, and refuses to overwrite an existing file.

## Export Reports

Set `Export folder` before exporting. If the field is empty, the plugin uses a default folder under the project's `Saved` directory.

Export files use this pattern:

```text
UESellerPreflightKit_<ScanLabel>_<Timestamp>.<extension>
```

Formats:

- Markdown: human-readable review checklist.
- CSV: spreadsheet or audit triage.
- JSON: structured output for tooling.

Existing files are not overwritten unless `Allow overwrite` is enabled. If a file already exists and `Allow overwrite` is off, export fails with a visible message.

## Safety Notes

- Generated reports are guidance/checklists, not approval certificates.
- Redirectors are report-only in V1. Use Unreal Editor's normal Content Browser Fix Up Redirectors workflow manually.
- Documentation template generation is explicit, confirmation-gated, and refuses overwrites.
- Export overwrite requires user opt-in through `Allow overwrite`.
- This plugin does not submit anything to Fab.

