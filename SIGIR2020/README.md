# Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background

This release contains the data and supporting materials associated with the paper **“Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background”**, published at SIGIR 2020.

The study examines how the choice of judgment scale and the background of crowd workers affect crowdsourced assessments of the truthfulness of political statements.

## Study Overview

The study uses 180 real statements:

- 120 PolitiFact statements, with 20 statements for each of the six truthfulness levels.
- 60 RMIT ABC Fact Check statements, with 20 statements for each of the three truthfulness levels.

The crowdsourcing experiments compare three judgment scales: S3, S6, and S100. Each task asks a worker to assess nine real statements and two GOLD items used for quality control. Workers search for evidence and provide a truthfulness assessment and a supporting URL. They also answer demographic, political background, and cognitive reflection questions.

The paper reports 5,400 real judgments and 1,200 GOLD judgments. The detailed data included in this release cover a larger set of retained assessments.

## Release Overview

The release contains the original task design, detailed worker data, statement ground truths, and the data distributed with the original publication.

The detailed worker data include:

- **7,733** judgments, including 6,327 real statement judgments and 1,406 GOLD judgments
- **695** pseudonymous worker identifiers and 703 task completions
- **359** worker comments
- **7,030** questionnaire responses
- **347,503** search and result records

The detailed data cover three task modalities. Each modality uses the same set of real statements, but a different scale for worker judgments. The counts by modality are:

| Task modality | Worker scale | Judgment rows |
| --- | --- | ---: |
| S3 | 0 to 2 | 2,222 |
| S6 | 0 to 5 | 2,200 |
| S100 | 0 to 100 | 3,311 |

These counts describe the detailed data in this release, not the exact analysis sample reported in the paper.

### Ground Truth

The root contains two ground truth tables:

- `PolitiFact-Ground_Truth.csv` contains 120 statements and their PolitiFact labels, using the native six level scale from 0 (Pants on Fire) to 5 (True).
- `RMIT_ABC_Fact_Check-Ground_Truth.csv` contains 60 statements and their native three level study labels: 0 (Negative), 1 (In-Between), and 2 (Positive). The original RMIT ABC Fact Check verdict is retained separately from the three level label.

Both tables contain statement identifiers, texts, and related fact check and speaker metadata.

### Crowdsourcing Task

`Crowdsourcing Task/` contains two files from the original task material:

- `hits.json` contains 200 task units with eleven documents each, including six PolitiFact statements, three RMIT ABC Fact Check statements, and two GOLD items.
- `questionnaire_mapping.json` contains the response-code mappings for demographic and political background questions.

The units contain 1,800 real statement assignments and 400 GOLD assignments. Each of the 180 real statements appears ten times. These assignments describe the task design, not all retained task completions across the three scales.

The task configuration is provided to support understanding and reuse of the experimental design. It does not include a live crowdsourcing platform or search service.

### Worker Data

`DataFrame/` contains four tables:

- `workers_answers.csv` contains individual judgments, task and statement information, worker assigned truthfulness values and labels, supporting URLs, and expert ground truth fields.
- `workers_comments.csv` contains comments associated with task completions.
- `workers_questionnaires.csv` contains questionnaire responses, including seven demographic and political background questions and three cognitive reflection questions per completion.
- `workers_urls.csv` contains records of searches and results, including queries and result URLs, linked to individual document assessment attempts. In the original working repository, this file is stored as `workers_urls.csv.gz` to reduce its size. Decompress it to obtain the same CSV, or read the compressed file directly with pandas.

### Historical Data

`Historical Data/` preserves the original data distributed with the paper: `ABC.csv`, `Politifact.csv`, `README.md`, and `crowdsourced-data/S3.csv`, `S6.csv`, and `S100.csv`.

The historical judgment tables contain 6,556 rows in total (2,189 for S3, 2,189 for S6, and 2,178 for S100). Use them when working with the original public dataset. The detailed worker data are a separate, larger snapshot; do not combine the two as independent observations.

### Release Metadata

`release_manifest.json` records release metadata, expected counts, and provenance. `checksums.csv` contains file sizes and SHA256 checksums. `CHANGELOG.md` records changes to the release. `CITATION.cff`, `LICENSE.md`, and `RIGHTS.md` provide citation and reuse information.

## Using the Release

Use the ground truth tables to inspect the statements and their expert labels, and `workers_answers.csv` to analyze the detailed crowd judgments.

The worker's assessment is stored in `doc_overall-truthfulness_value`, with the corresponding response label in `doc_overall-truthfulness_label`. All four worker tables contain `task_modality`. Filter this field to `S3`, `S6`, or `S100` to analyze one modality. The same field should be used when joining tables. For example, `answers[answers["task_modality"] == "S6"]` selects the judgments collected with S6. The worker scales are distinct from the native expert scales. If comparing judgments across modalities, choose and document a transformation. The historical tables already separate the three modalities into individual CSV files.

For real statements, link the answers to the ground truth using the pair `doc_ground_truth_source`, `doc_ground_truth_fact_check_id` in the answer table and `fact_check_source`, `fact_check_id` in the ground truth tables. Read identifiers as strings. Historical document names are not reliable universal claim identifiers.

GOLD items have `source = gold_question` and no expert fact check identifier. Keep them separate from real statements when analyzing truthfulness judgments.

The `worker_id` field contains stable pseudonyms. To link records for a particular completion, also use `task_modality`, `batch_name`, `unit_id`, and the attempt field (`amount_try` in the answers and `try_current` in the ancillary tables). For search records, additionally use `doc_index` in the answers and `document_index` in the URL table.

## Integrity and Provenance

The detailed data were prepared from the study's assessment records in the [original working repository](https://github.com/Miccighel/FakeNewsABCPolitifact). The original publication files and original task configuration are preserved unchanged. The task files originate from the [thesis research materials](https://osf.io/jr6vc/).

The release preserves the native expert labels and the worker judgment scales. The ground truth and detailed worker tables have been checked for statement and identifier alignment, and the ancillary tables for valid links to task completions and assessments.

The manifest records source references, file roles, and the provenance of the curated data. The checksums can be used to verify the package.

## Privacy and Responsible Reuse

The release contains research data from human participants, including judgments, questionnaire responses, comments, and search activity. Worker identifiers are pseudonyms, but this does not guarantee that participants cannot be identified when data are combined with other information.

Do not attempt to identify or contact participants. Do not combine these records with external data for the purpose of identifying individuals.

## Rights and Reuse

The package contains material with different rights status. The original publication made its data available for research purposes. Participant contributions, fact check source material, and material from external websites retain their applicable rights. See `LICENSE.md` and `RIGHTS.md` for details.

## Citation

If you use these data, please cite the associated paper:

Kevin Roitero, Michael Soprano, Shaoyang Fan, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2020. *Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background*. Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval, 439–448.

DOI: [10.1145/3397271.3401112](https://doi.org/10.1145/3397271.3401112)

Citation metadata are also available in `CITATION.cff`.
