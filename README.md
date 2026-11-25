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

## Maintainer: build and publish a release

The build workflow runs in this **public** repository so standard GitHub-hosted runners are eligible for free usage. The application source remains in the private `greatPHPer/FilteredDelete` repository.

### One-time setup

1. Create a fine-grained personal access token for `greatPHPer/FilteredDelete`.
2. Give it access to **Only select repositories** → `FilteredDelete`.
3. Grant **Contents: Read-only**. Do not grant write access.
4. In this public repository, open **Settings → Secrets and variables → Actions** and add a repository secret named `SOURCE_READ_TOKEN` with that token.

### Test a build without publishing

Open **Actions → Build and publish FilteredDelete → Run workflow**. Select `main` as `source_ref` and leave `publish_release` unchecked. The workflow builds and tests Windows x64, Linux x64 and Linux ARM64, then stores temporary artifacts for 7 days.

### Publish a version

First, create and push a version tag in the private source repository, after validating that source revision:

```bash
git tag v1.0.0
git push origin v1.0.0
```

Then run the workflow in this public repository with `source_ref` set to `v1.0.0` and `publish_release` checked. After all three build jobs pass, it creates the public release and uploads the platform archives and `SHA256SUMS.txt`.

The workflow uses this repository's automatically provided `GITHUB_TOKEN` to publish the release; no release-write PAT is required.
