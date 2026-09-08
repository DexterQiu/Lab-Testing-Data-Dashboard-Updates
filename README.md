# Lab Testing Data Dashboard Updates

This public repository contains release metadata and update packages with SHA-256
checksums for Lab Testing Data Dashboard installations.

## Latest release: 0.2.4

[Download version 0.2.4](https://github.com/DexterQiu/Lab-Testing-Data-Dashboard-Updates/releases/tag/v0.2.4)
for the Windows installer, update patch, checksums, and validation details.

This release fixes missing Python dependencies and bundled MATLAB/Python procedure
files in the installer, improves recovery of test and analysis records after a
restart, and adds **Settings → Updates → Application repair**. Repair backs up the
catalog and settings before restoring available procedures, reconciling analysis
history, and re-indexing accessible test folders. Test metadata, notes, source
measurements, and records for disconnected folders are preserved.

Use the dashboard's **Check for updates** action to install the latest patch. If an
older installation cannot start, download and run
`LabTestingDataDashboard-Setup-0.2.4.exe` in its existing installation folder.
After it opens, use **Repair application** to repair the catalog and check the
installation. **Reinstall from update package…** also accepts the current version's
patch when installed application files need to be restored.

MATLAB and licensed toolboxes remain separate requirements for MATLAB procedures.

## Update package format

The dashboard checks the latest published release through GitHub's public
release API. Releases must contain a patch-like asset named
`LabTestingDataDashboard-<version>.patch` and a SHA-256 digest (GitHub asset
digest or an adjacent `.sha256` sidecar). The running dashboard only downloads,
verifies, and stages the package; a separate updater or installer applies it
after the dashboard exits.

The update package is a ZIP-compatible archive with a `.patch` extension. It
contains the versioned Windows installer and update metadata. Laboratory data,
catalog databases, preferences, and notes are not included in this repository.
