# Lab Testing Data Dashboard Updates

This public repository contains signed-release metadata and update packages for
Lab Testing Data Dashboard installations.

The dashboard checks the latest published release through GitHub's public
release API. Releases must contain a patch-like asset named
`LabTestingDataDashboard-<version>.patch` and a SHA-256 digest (GitHub asset
digest or an adjacent `.sha256` sidecar). The running dashboard only downloads,
verifies, and stages the package; a separate updater or installer applies it
after the dashboard exits.

The update package is a ZIP-compatible archive with a `.patch` extension. It
contains the versioned Windows installer and update metadata. Laboratory data,
catalog databases, preferences, and notes are not included in this repository.
