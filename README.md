# Lab Testing Data Dashboard Updates

This public repository contains release metadata and update packages with SHA-256
checksums for Lab Testing Data Dashboard installations.

## Latest release: 0.2.5

[Download version 0.2.5](https://github.com/DexterQiu/Lab-Testing-Data-Dashboard-Updates/releases/tag/v0.2.5)
for the Windows installer, update patch, checksums, and validation details.

Version 0.2.5 fixes automatic ring measurement using small tissue holes as the
radial center and adds **Postprocessing → Image measurements → Ring Thickness
Measurement — Manual**. The manual workflow retains the original MATLAB tracing,
crop/zoom, post recoloring, saved-mask reuse, Manual/Semi-Auto cleanup, three-mask
averaging, overlays, circumferential plots, and `thickness.mat` outputs. Selections
are recorded, and completed manual measurements can supply thickness for biaxial
extraction. Pixel calibration remains an explicit user input. Automatic boundaries
remain experimental and must be reviewed against their overlays and any reference.

The installer and application-repair fixes from 0.2.4 are included. Use
**Settings → Updates → Application repair** when needed. Repair backs up the
catalog and settings before restoring available procedures, reconciling analysis
history, and re-indexing accessible test folders. Test metadata, notes, source
measurements, and records for disconnected folders are preserved.

Use the dashboard's **Check for updates** action to install the latest patch. If an
older installation cannot start, download and run
`LabTestingDataDashboard-Setup-0.2.5.exe` in its existing installation folder.
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
