# FilteredDelete — Downloads

Public release downloads for **FilteredDelete**, a cross-platform folder-cleanup utility built with .NET 10 and Avalonia.

The application source code is maintained separately in the private [FilteredDelete source repository](https://github.com/greatPHPer/FilteredDelete).

## Downloads

| Platform | Architecture | Download |
|---|---|---|
| Windows | x64 | `FilteredDelete-win-x64-<version>.zip` |
| Linux | x64 | `FilteredDelete-linux-x64-<version>.tar.gz` |
| Linux | ARM64 | `FilteredDelete-linux-arm64-<version>.tar.gz` |

Download the archive for your platform from the [Releases page](https://github.com/greatPHPer/FilteredDelete_release/releases). Verify downloads with the accompanying `SHA256SUMS.txt`.

## Installation

### Windows
1. Download and extract the Windows x64 ZIP.
2. Run `FilteredDelete.exe` from the extracted folder.

### Linux
1. Download the archive matching your CPU architecture.
2. Extract it with `tar -xzf <downloaded-archive>.tar.gz`.
3. Run `chmod +x FilteredDelete` if needed, then launch `./FilteredDelete`.

Linux desktop environments must provide the system graphics/input libraries required by Avalonia.

## Safety
- Preview proposed operations before execution.
- Trash / Recycle Bin is the default deletion mode.
- Permanent deletion is a separate, explicitly confirmed operation.
- The application does not silently fall back from Trash to permanent deletion.

See the release notes for version-specific changes and known limitations.

## Selection behavior

- **Checked** means the item is selected for deletion.
- **Unchecked** means the item is kept.
- **Indeterminate** means a folder contains a mixture of items to delete and keep.
- All deletable items start checked; uncheck anything you want to retain.
- The selected root folder is always kept.

## Preview and safety

Generate and review a preview before executing any operation. The default action moves approved items to the operating system's Recycle Bin / Trash. Permanent deletion is a separate option and requires typing `DELETE`. The application does not silently fall back to permanent deletion.

## Copy and move

Copy To and Move To operate on manually kept (unchecked) files and folders. Pattern-based or inherited keeps are not automatically treated as transfer selections.

## Source code

The application source is maintained in the private [FilteredDelete source repository](https://github.com/greatPHPer/FilteredDelete). This public repository is for downloads and release notes.
