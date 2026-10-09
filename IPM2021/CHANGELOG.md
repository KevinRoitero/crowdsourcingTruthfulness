# Changelog

## Version 1.5 (planned)

- Extend the standalone paper release with 14 useful official Chapter 7 files: eight task files and six detailed DataFrame tables.
- Omit the two redundant thesis ground truth files (121 PolitiFact and 59 RMIT ABC records) from the public package while preserving them unchanged in the immutable thesis source archive; use the corrected ground truths at the package root.
- Preserve the original paper `multidimensional.csv` and all previously verified scientific package members.
- A read only comparison matched all 2,200 records between `multidimensional.csv` and `DataFrame/workers_answers.csv` by unique task and statement keys. The same ten rows from one statement differ in `doc_statement` and `doc_ground_truth_politifact_label`; the other shared values match and no source values are silently rewritten.
- Omit `AssignmentId` and `HITId` from the public `DataFrame/workers_mturk_data.csv` while retaining all 200 rows, `worker_id`, and 22 other columns. Verify the original 24-column file and record source/package hashes and field changes in the release manifest.
- Document the expanded source coverage and known irregularities. Complete privacy review, dry run, build, and package checks before public publication.
- Preserve v1.4 and all source archives unchanged.

## Version 1.4

- Consolidated the reported supervised learning parameters from `parameters/parameters.md` into the root `README.md`.
- Omitted `parameters/parameters.md` from the new package after preserving its useful content in the root README.
- Removed the historical BibTeX block from the root README; the paper citation remains in concise text form and machine readable metadata are provided in `CITATION.cff`.
- Added `CITATION.cff`, `LICENSE.md`, and `RIGHTS.md`.
- Preserved verified version 1.3 and the publication era source snapshot unchanged.
- No scientific data changes are intended.

## Version 1.3

- Consolidated the useful content of the publication-era README into the root `README.md`.
- Omitted `Historical Source/README.md` from the new package so that the release has one public README.
- Preserved the publication-era source archive and verified version 1.2 unchanged.
- No scientific data changes are intended.

## Version 1.2

- Updated the public README after the complete historical mapping audit.
- Documented the final correction state of 16 PolitiFact metadata crossovers plus `Liberal_Negative_doc9`.
- Simplified the description of the study, historical source, ground truth, evidence, and provenance.
- Uses the same validated canonical study data and evidence as version 1.1.

Version 1.1 remains unchanged as an earlier verified release.

## 1.0

- Reconstructed the standalone paper release from the publication-era `IPM2021/` Git snapshot.
- Preserved `multidimensional.csv`, the historical README, and the reported model parameters without modifying their bytes.
- Added canonical PolitiFact and RMIT ABC ground-truth projections and the harmonized Evidence Corpus.
- Documented the `DEM_BARELYTRUE_doc7` historical metadata misalignment while preserving the original crowd judgments.
- Corrected the derived mapping of `Liberal_Negative_doc9` to RMIT ABC fact-check `5270252` (Kelly O'Dwyer refugee-intake claim), with native label `negative` and value 0, while preserving the historical source bytes unchanged.
