# Changelog

## Version 1.2

- Added eight files in `Crowdsourcing Task/` from the historical thesis Chapter 5 task configuration, following the IPM2021 release organization.
- Preserved the original instructions, dimensions, questionnaires, assignments, search settings, and task settings byte for byte.
- Published `workers.json` with empty participant-control lists instead of repeating 572 original Mechanical Turk blacklist identifiers. The source file remains preserved in the OSF thesis archive.
- Documented the 99-unit task snapshot, GOLD assignments, task-scale versus PolitiFact-scale values, and the difference between the task snapshot and the complete longitudinal study.
- Updated the README, RIGHTS, manifest, and SHA256 checksums. All five scientific DataFrame tables, the 60-statement ground truth, and all 12 historical batch CSVs remain unchanged.

## Version 1.1

- Expanded the historical release with five `DataFrame/` tables containing detailed worker judgments, comments, dimension selections, questionnaires, and search activity.
- Added `PolitiFact-Ground_Truth.csv` with 60 statements and their original six truthfulness levels.
- Preserved 3,606 real statement judgments and stable pseudonymous identifiers for 410 workers across the collection rounds.
- Retained 12 exact duplicate judgment rows and 149 dimension selection events without a certain answer link. Documented these issues in the README.
- Added the current `README.md`, `CHANGELOG.md`, `CITATION.cff`, `LICENSE.md`, `RIGHTS.md`, `release_manifest.json`, and `checksums.csv`.
- Excluded the original worker identifier mapping and internal audit files from the package.
- Preserved the original study data without modification.

## Version 1.0

- Published the original crowdsourcing data associated with the study.
- Provided the historical assessment batches and subsets, including the original judgments and quality control material.
- Preserved the source records in their original form.
