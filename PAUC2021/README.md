# Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19

This release contains the data and supporting material associated with the paper **“Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19”**, first published online in 2021 and appearing in *Personal and Ubiquitous Computing*, volume 27 (2023), pages 59 to 89.

The study examines how people assess the truthfulness of statements about COVID-19 and how their judgments change over time.

## Study Overview

The study uses **60 PolitiFact statements**, with ten statements for each of the six truthfulness levels: Pants on Fire, False, Mostly False, Half True, Mostly True, and True.

The data were collected through crowdsourcing between May and August 2020. The researchers ran the task in four monthly rounds, involving both new workers and workers who had participated in earlier rounds.

Each task asked a worker to assess six real statements and two GOLD items used for quality control. For each real statement, workers gave a truthfulness judgment, a written explanation, and a supporting URL.

The study reports seven crowdsourcing tasks. The data in this release cover **12 sets and subsets** derived from those tasks. These are not 12 separate studies.

## Release Overview

This release contains detailed records of the crowd judgments and worker activity collected during the study.

The data include:

- **3,606** judgments on real statements
- **410** pseudonymous worker identifiers
- **5,511** dimension selection events
- **5,990** questionnaire records
- **276** worker comments
- **254,867** search and result records

These counts describe the data included in this release. They should not be confused with the overall participation and judgment totals reported in the paper, which also include GOLD items.

## Package Structure

`DataFrame/` contains five tables:

- `workers_answers.csv` contains the 3,606 judgments, including truthfulness assessments, explanations, supporting URLs, and task information.
- `workers_comments.csv` contains 276 comments submitted during the tasks.
- `workers_dim_sel.csv` contains 5,511 records of dimension selections.
- `workers_questionnaires.csv` contains 5,990 questionnaire responses.
- `workers_urls.csv` contains 254,867 records of searches and results, including queries, URLs, titles, and snippets.

`PolitiFact-Ground_Truth.csv` contains the 60 statements, their PolitiFact labels, and related metadata.

`release_manifest.json` records the release metadata, historical source references, and expected record counts.

`checksums.csv` contains the file sizes and SHA256 checksums used to verify the package.

`CHANGELOG.md` records changes to the release. `CITATION.cff` provides citation metadata. `LICENSE.md` and `RIGHTS.md` explain the terms of reuse.

## Using the Release

Use `PolitiFact-Ground_Truth.csv` to inspect the statements and their original PolitiFact labels.

Use `workers_answers.csv` to analyze the crowd judgments. The other tables provide additional information about comments, questionnaires, dimension selections, and search activity.

The `worker_id` field contains stable pseudonyms and can be used to follow the same participant across collection rounds. To connect individual records, also use the relevant fields such as `batch_name`, `unit_id`, and statement identifiers.

The original six level PolitiFact scale is preserved, with values from 0 (Pants on Fire) to 5 (True).

## Known Data Issues

Some irregularities in the collected records have been preserved:

- **149 dimension selection events** cannot be linked with certainty to a judgment. They remain in `workers_dim_sel.csv`.
- **12 exact duplicate judgment rows** are retained in `workers_answers.csv`.
- For `pants-on-fire_doc5`, the PolitiFact rating graphic indicates Pants on Fire, while the article text also uses False. The release preserves the historical Pants on Fire label.

These details should be considered when joining tables or reproducing record counts.

## Integrity and Provenance

The release was prepared from the study assessments. The historical source files remain unchanged, while the distributed tables contain curated data and pseudonymous worker identifiers.

`release_manifest.json` documents provenance and record counts. `checksums.csv` lists the packaged files and can be used to check their integrity.

## Privacy and Responsible Reuse

The release contains research data from human participants, including judgments, questionnaire responses, comments, and search activity.

Worker identifiers are pseudonyms, but this does not guarantee that participants cannot be identified when the data are combined with other information.

Do not attempt to identify or contact participants. Do not combine these records with external data to identify individuals.

## Rights and Reuse

The package contains material with different rights status.

Material created by the release authors is covered by `LICENSE.md` where the authors have the right to grant those terms.

Participant contributions, PolitiFact information, and material from external websites are not automatically covered by the same license.

See `RIGHTS.md` for details.

## Citation

If you use these data, please cite the associated paper:

Kevin Roitero, Michael Soprano, Beatrice Portelli, Massimiliano De Luise, Damiano Spina, Vincenzo Della Mea, Giuseppe Serra, Stefano Mizzaro, and Gianluca Demartini. 2023. *Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19*. *Personal and Ubiquitous Computing*, 27, 59 to 89.

DOI: `10.1007/s00779-021-01604-6`

Citation metadata are also available in `CITATION.cff`.
