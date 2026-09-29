# Lab Testing Data Dashboard Updates

This public repository contains release metadata and update packages with SHA-256
checksums for Lab Testing Data Dashboard installations.

## Latest release: 0.3.7

[Download version 0.3.7](https://github.com/DexterQiu/Lab-Testing-Data-Dashboard-Updates/releases/tag/v0.3.7)
for the Windows installer, update patch, checksums, and validation details.

Version 0.3.7 accepts **Specimen segment**, **Segment**, and **Test Segment**
spreadsheet headers in any column order. Right-click a folder in the file tree
to **Open in File Explorer**. Right-click a complete generated procedure result
folder for **Archive result folder**. Archived folders, notes, and run history
remain available through **Show archived files**.

Automatic/manual **Biaxial Data Extraction** now share one latest-result history;
the same applies to automatic/manual **Ring thickness measurement**. A successful
new run archives older verified outputs of either variant. Failed or cancelled
runs keep the previous result available. Use **Settings → Repair application**
to consolidate existing paired histories after the usual catalog backup.

Archiving verifies generated files and provenance, preserves raw data and
untracked/edited files, and rolls back if saving its catalog changes fails.
Scientific MATLAB functions are unchanged.

Version 0.3.6 restores the original MATLAB runner's **three random starts on
unloading**, with results organized in **2D_obj6_run1**, **run2**, and **run3**
folders. The combined MAT file preserves the original variables and every fit.
Initial guesses and objective values are recorded; the summary selects the
lowest objective value without mixing fits or phases.

Default target pressures are **[80 100 120] mmHg**. The summary maps 80 to
diastolic, 100 to MAP, and 120 to systolic, including all four matching linearized
stiffness components in MPa. **H (µm) comes directly from the test folder's
thickness.mat**. Selecting a preview cell shows the source file, native field,
fit, and pressure row. Existing template formulas and formatting are retained.

All three MATLAB fits matched the original runner with **zero numerical
difference**, including every native loaded-property and stiffness array. The
calculation functions and source datasets remain unchanged. Three starts seek
a better minimum; they do not guarantee a global minimum. Python retains its
independent optimizer and compact plot, with the same output structure.

After updating, choose **Restore original defaults** in Passive Biaxial
Mechanical Analysis if an older saved preset remains, then run the analysis to
produce the three-fit, three-pressure results. Existing results are retained
through the app's archive workflow.

Version 0.3.5 displays run and project timestamps in the **system time zone**.
The archive toggle now controls **Recent runs** in Postprocessing and Batch as
well as archived ring-result selections. Archived runs are clearly labelled
when shown, and status colors remain readable after switching themes.

Archiving now follows the specimen folder when a different parent folder is
scanned, including after the previous scan root is removed. File links and notes
are retained across archive moves. To repair older results already on disk, use
**Settings → Repair application** after updating. Repair backs up the catalog,
reconciles archive links, and archives older verified results behind the latest
successful run. Modified or unproven folders stay in place with an explanation.
Raw data remains unchanged.

Version 0.3.4 repairs **Passive Biaxial Mechanical Analysis** input discovery.
Extracted MAT datasets remain available after rescans and restarts even without
their original run-history association. Automatic and Manual extraction results
are distinguished by their folders. Validation rejects a ring `thickness.mat`
or an incomplete dataset before starting MATLAB and explains which file to use.

In v0.3.4, **Target pressure (mmHg)** defaulted to **93.33** and also accepted a list
such as **[80 100 120 140]**. Each phase was fitted once, then analyzed at every
requested pressure. Loading and unloading results include MAT arrays, CSV
tables, original MATLAB figures, and plot-data workbooks. The original MATLAB
scientific functions are preserved; both phases of specimen 1714 matched the
original runner exactly at all four pressures with the same initial parameters.
Raw inputs and the reference source remain unchanged. Python supports the same
pressure list, but its independent optimizer can return different fitted
parameters from MATLAB.

Version 0.3.3 adds a per-test report **Type** in **Projects → Edit test**.
Leave it blank to use **Project + Genotype**, the existing default. The project
table keeps long Types compact and shows the complete value on hover. The same
Type drives report previews, Excel exports, and cohort statistics. The previous
Type classification (such as Biaxial) is now labelled **Testing Type** throughout
the app. Saved Types survive rescans, spreadsheet refreshes, and restarts.

The **Pi16-Cre** and **ROSA** spreadsheet columns now appear in Projects,
**Projects → Columns**, Edit test, and specimen details. They are read by header
regardless of column order, and manual edits remain preserved during refresh.
The source workbook and raw data remain unchanged.

Version 0.3.2 finds `.xlsx` specimen workbooks with **Samples** in their name,
including **Samples.xlsx**, **ProjectSamples.xlsx**, and project-specific names.
It checks the scanned folder and then its immediate parent. Column order may
vary: **Mouse** / **Mouse ID** and **Age at Testing (wks)** / **Age (weeks)** are
recognized by their headers. KLF4 and Fbn1 retain their genotype mappings when
the Stanford workbook's other gene columns are reordered. Manual edits and
source workbook formulas remain preserved.

**Projects → Columns** opens a checkbox list of test and specimen fields.
**Save** remembers the visible columns across refreshes and restarts; **Cancel**
discards edits and **Restore Defaults** selects every field. Project / Test
always stays visible. Hidden fields remain available for search and exports.

Import notices now appear directly in Projects. Multiple matching workbooks in
one folder produce a clear notice instead of choosing one arbitrarily. Keep one
current specimen workbook in each folder. An invalid or locked save retains
previous imports until the next successful refresh. Shared parent workbooks do
not duplicate pending rows, and removing a scanned folder removes its pending
specimens from the view without changing any source files.

Version 0.3.1 names scanned tests after the folder containing their raw data,
including when that folder is scanned directly. Known legacy filename-based
names are corrected on upgrade, and deliberate renames are retained on rescan.
Postprocessing and Batch use the same test name while detecting acquisition
filename prefixes independently.

The specimen workbook reads **Age (weeks)** and **Specimen segment** wherever
those columns appear. A missing age uses `(test date − DOB) / 7`; manual age edits
remain preserved. **Projects → Show untested specimens** shows workbook mice
without an associated test folder. These have no test date and use today's date
to calculate their age. Once their test folder is scanned, they leave this group.

The saved age window defaults to **25 weeks ± 5 days** (170–180 days). Ages are
green within range, yellow during the **3 days** before the upper limit, and red
outside the range. The upper limit itself is yellow; unknown ages stay neutral.
The **Range** button beside the checkbox opens a compact popup with
Save and Cancel. The switch, target age, tolerance, and warning window persist
across restarts. Ages display two decimals while comparisons use exact days.

Version 0.3.0 adds **Import → Scanned folders → Remove folder from app** and the
same action on scanned roots in the File Explorer. Removing a folder changes only
the app catalog and matching navigation preferences. Rescanning restores its test
IDs, manual edits, notes, project assignments, and run history; source files stay
unchanged. A canceled rescan keeps the folder removed.

New note images are **at least 1920 × 1080** with their aspect ratio preserved.
Larger images and native video frames retain their resolution. Charts render at
higher resolution before annotation, including on high-DPI displays.

Exports of tables, workbooks, PDFs, comparison charts, and parameters protect all
existing files. Save a new export under a new filename. Postprocessing uses staged
copies and Windows sharing locks on selected inputs. Current ring measurements
are retained in a verified per-test location; existing original or edited
`thickness.mat` files stay unchanged, and both extraction workflows use the latest
verified measurement. Archiving leaves mixed or externally edited result folders
in place. The review also fixes transaction rollback and note-save error handling.

Version 0.2.12 adds movable Overview panels. Drag a panel's title or six-dot grip
to another panel's side to share a row, or its top/bottom edge to create a new row.
The arrangement and sizes persist across tests and restarts. **Reset layout**
restores the initial positions. Test Summary adapts to narrow widths; existing
table selections and module visibility are retained.

Age in weeks displays **two decimal places**. Unloaded configuration and its
values are **right-aligned** beside Key Metrics, with blue length, amber outer
diameter, and green wall thickness values for light and dark themes.

The summary's **TTESTS** section now uses the template's native conditional rules:
green below 0.05 and yellow from 0.05 to below 0.1. Ranges expand with the current
comparisons in Structural Properties, Material Properties, and Hysteresis. The
preview uses the same rules and updates after measurement edits. Native Excel
and the preview agree on all 420 conditional cells in the review workbooks.

Version 0.2.11 places **Unloaded configuration** and its values beside **Key Metrics**,
above the Specimen and Measurements tabs. Length and outer diameter come from raw
acquisition headers, including both LabVIEW layouts and their units. The project
summary uses the same values; available measured MAT thickness and saved manual
overrides are retained. Conflicting raw geometry is reported for review.

**Edit test** is beside **Rename** in Projects, and shared action names are consistent
across modules. The summary's Material Properties and Hysteresis merged titles now
align with their table columns. The extra Specimen information block is removed
from the workbook; specimen details remain available in the application.

The Analysis column reads 2D/3D from mechanics results, including legacy result
filenames. Mechanics procedure 1.2.1 records the analysis type in both Python and
MATLAB outputs. The current calculation workflow remains 2D. Its 14 MATLAB
calculation files match the supplied reference; extraction and both loading and
unloading calculations passed separate Python/licensed-MATLAB comparisons.

Version 0.2.10 replaces the Reports catalog export controls with **Export project
Excel…** and embeds the workbook preview in **Report contents**. Select a project,
review its tabs, and export the same workbook. **Refresh preview** reloads external
postprocessing changes. Project changes discard obsolete previews before export.

Exports and previews use the supplied template's font families, bold styling,
number formats, merged groups, gray statistics rows, and border colors and weights.
Groups, statistics, and formulas expand to fit the project's tests. Every cell
in the Type columns is horizontal and centered, including Average Data labels.
Columns widen first; any font reduction is limited
to one point, with taller rows when necessary. Content is centered and no worksheet
has frozen or split panes. All 11 template tabs remain, with an additional tab for
custom or unspecified segments. Editing measurements preserves their full precision.
Native Excel and the preview agree on all 2,716 formulas in the validation workbook.

Version 0.2.9 fixes the MATLAB mask-selector callback error and makes saved-mask
reuse follow the selected mask. Manual procedure 1.0.2 is activated on upgrade.

Age is now in **weeks**, calculated as (test date − DOB) / 7. Existing day-based
overrides are converted without losing manual edits. Projects adds a sortable
**Specimen segment** column, supplied by the specimen workbook or **Edit test**.

**Projects → Edit test → Analysis workbook** includes all 11 reference analysis
tabs. Measurement edits persist across refreshes, segment changes, and restarts.
**Reports → Export project summary** previews and exports the same tabs with live Excel
equations, original variable names, and group sizes that expand to fit the tests.
Specimen metadata and supported postprocessing MAT values fill automatically;
unavailable data stays blank. Mouse # is the numeric suffix of Mouse ID, and Type
currently combines Project + Genotype. The supplied historical specimen records
are not included in the software or update package.

Version 0.2.8 fixes manual MATLAB ring measurement ending after an intermediate
operation. The review now finishes only with explicit confirmation or cancellation,
and retains tracing, crop/zoom, post recoloring, saved-mask reuse, cleanup options,
three-mask averaging, plots, and thickness outputs.

Place **SU_ProjectSamples.xlsx** in the testing main folder to automatically load
Mouse ID, Sex, Weight, Shipment, DOB, Age, and the two genotype columns. Saved Excel
changes are detected in the background, with leading-zero test numbers supported.
Ambiguous matches remain unmatched until an exact Mouse ID is entered.

Projects supports sorting these fields. **Key Metrics → Specimen** is the first tab;
the existing statistics are under **Measurements**. Unloaded configuration appears
beside the Key Metrics heading in version 0.2.11.
**Edit test → Specimen** edits all specimen fields and preserves manual changes
through refreshes and restarts. Age defaults to test date minus DOB, in weeks.
Disable **Calculate from test date and DOB** to enter a manual age, or use
**Use workbook values** to remove overrides when saving. Month-only shipment
labels stay as labels and missing weights stay blank.

Version 0.2.7 renames the viewers to **Data** and **Media**. Files in `Archive`
folders are hidden by default; **Show archived files** below the explorer controls
turns their visibility on or off and remembers the preference.

In Postprocessing and Batch, Ctrl/Shift highlights complete rows. **Right-click the
highlighted group**, then choose **Check selected files/tests** or **Uncheck selected
files/tests**. Opening the menu preserves the group and does not change checkboxes.
These actions are only in the right-click menu. Highlight one Batch test to view and
edit that test's individual settings.

The package includes the missing XLS, XLSB, and ODS spreadsheet readers. This release
also protects source files during export, preserves existing CSVs if an export fails,
and saves run history and archive links atomically. Page implementations and module
metadata are separated to support future modules without changing saved preferences.

The workflows from 0.2.6 include **Save as defaults**, **Revert to saved defaults**, and
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
`LabTestingDataDashboard-Setup-0.2.10.exe` in its existing installation folder.
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
