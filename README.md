# Lab Testing Data Dashboard Updates

This public repository contains release metadata and update packages with SHA-256
checksums for Lab Testing Data Dashboard installations.

## Latest release: 0.2.6

[Download version 0.2.6](https://github.com/DexterQiu/Lab-Testing-Data-Dashboard-Updates/releases/tag/v0.2.6)
for the Windows installer, update patch, checksums, and validation details.

Version 0.2.6 adds **Save as defaults**, **Revert to saved defaults**, and
**Restore original defaults** inside Postprocessing. Unloaded length and outer
diameter are read automatically from acquisition files. Ring measurement defaults
to **Automatic — bright tissue** with a **0.65** local edge intensity fraction.

File checks persist across tabs, TIFF images are ordered by earliest creation time,
and group selection is available in both individual and batch processing. Highlight
one test in Batch to edit only its parameters. The batch console retains complete
output from every run and colors progress, completion, review, and error messages.

A finished ring run copies the latest `thickness.mat` into its test folder, keeping
the previous copy in `Archive`. Both extraction methods use the current test-folder
copy. A successful rerun archives previous results of the same procedure while
preserving run history. Failed or cancelled calculations retain the prior results.

The manual ring workflow and original MATLAB measurement functions from 0.2.5 are
retained, including tracing, crop/zoom, post removal, mask reuse, and three-mask
averaging. Pixel calibration must match the acquisition. Review automatic boundaries
against their overlays and available reference measurements.

The installer and application-repair fixes from 0.2.4 are included. Use
**Settings → Updates → Application repair** when needed. Repair backs up the
catalog and settings before restoring available procedures, reconciling analysis
history, and re-indexing accessible test folders. Test metadata, notes, source
measurements, and records for disconnected folders are preserved.

Use the dashboard's **Check for updates** action to install the latest patch. If an
older installation cannot start, download and run
`LabTestingDataDashboard-Setup-0.2.6.exe` in its existing installation folder.
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
