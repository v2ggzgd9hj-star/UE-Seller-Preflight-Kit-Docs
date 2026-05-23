# Troubleshooting

Version: 1.0.0
Publisher: Toolsmith Studio
Support: toolsmithstudio@proton.me
Tested environment: Windows / Win64 with Unreal Engine 5.7.4

UE Seller Preflight Kit runs locally inside Unreal Editor. It does not upload files, call AI services, use cloud services, or intentionally collect telemetry.

UE Seller Preflight Kit is independent and unofficial. It is not affiliated with Epic Games, Unreal Engine, or Fab, and it does not guarantee Fab approval.

## Plugin Does Not Appear In Tools Menu

Check:

1. The plugin folder is under `%PROJECT_ROOT%/Plugins/UESellerPreflightKit`.
2. `UESellerPreflightKit.uplugin` exists inside that folder.
3. The plugin is enabled in `Edit > Plugins`.
4. Unreal Editor was restarted after enabling if prompted.
5. The plugin was built for your Unreal Engine version.

Expected menu path:

```text
Tools > UE Seller Preflight Kit
```

## Scan Returns No Results

No results can be valid for a very clean target, but most scans usually include at least the target classification Info result. Check that:

- You clicked `Scan`.
- The selected scope points at the intended project/plugin root.
- Filters are not hiding results. Set `Severity` to `All Severities` and `Category` to `All Categories`.
- The target path contains a `.uproject` or `.uplugin`.

## Manual Path Scan Fails

`Manual Path` accepts a project/plugin root folder, a `.uproject`, or a `.uplugin`.

If the scan returns a Blocker:

- Confirm the path exists.
- Confirm it is not a random file.
- Confirm the folder contains a top-level `.uproject` or `.uplugin`.
- Avoid pointing at `Content`, `Source`, or an individual asset file.

## Export Folder Cannot Be Created

The plugin creates the export folder if possible. If export fails:

- Choose a folder where your user account can write.
- Avoid protected engine install folders.
- Try a folder under the project `Saved` directory or another local report folder.
- Check whether antivirus or file-locking software blocked the write.

## Export Refused Because File Exists

Export files are not overwritten by default. If the UI says a file already exists:

- Pick a different export folder, or
- enable `Allow overwrite`, then export again.

Only enable `Allow overwrite` when you are comfortable replacing the previous report file.

## JSON Export Validation Fails

The plugin validates generated JSON before writing. If JSON export fails:

- Try exporting again after a new scan.
- Export Markdown and CSV to preserve the current result set.
- Record the visible export status text.
- Send support information listed in [Support](Support.html).

## Redirector Warning Appears

Redirector warnings mean the Asset Registry found redirector objects under scanned content paths.

V1 report behavior:

- The plugin reports redirectors only.
- It does not fix redirectors.
- It does not save packages.
- It does not delete assets.

Manual fix approach: use Unreal Editor's normal Content Browser Fix Up Redirectors workflow after reviewing the affected content.

## Documentation Warnings Appear

Documentation warnings mean expected buyer/reviewer files were missing or missing basic support/disclaimer text.

Use `Generate Doc Template` only after selecting a Documentation or Listing result. The plugin asks for confirmation, creates a template file, and refuses to overwrite existing files.

Templates are starting points. Replace all placeholder text before release.

## Results Seem Noisy

Try this:

- Use `Severity` to focus on Blocker and Error results first.
- Use `Category` to inspect one rule category at a time.
- Read the source reference before changing files.
- Treat Documentation and Listing warnings as review prompts, not automatic failures.
- Keep naming warnings manual. The plugin cannot fully judge descriptive English names.

## UE Version Or Build Issues

Current plugin version is `1.0.0`. If the plugin cannot build or load:

- Confirm the Unreal Engine version used to build the package. Version 1.0.0 was tested on Windows / Win64 with Unreal Engine 5.7.4.
- Confirm Visual Studio Build Tools are installed if you need to compile C++.
- Rebuild the plugin with the same UE version used by the project.

## Where To Send Support Info

Send support requests to Toolsmith Studio at toolsmithstudio@proton.me. Include:

- UE version.
- Plugin version.
- Operating system.
- Target type: project, code plugin, or manual path.
- Exported Markdown/CSV/JSON reports if available.
- Screenshots of the window and error/status text.
- Steps to reproduce.

Support is for the plugin workflow and plugin defects. It is not a promise of Fab approval.

