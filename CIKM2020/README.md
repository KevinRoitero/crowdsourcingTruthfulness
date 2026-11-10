# The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?

This release contains the data and supporting material for the paper published at CIKM 2020. The study examines how people assess the truthfulness of recent statements about COVID-19.

## Study Overview

The study uses 60 PolitiFact statements, with ten statements for each of six truthfulness levels: Pants on Fire, False, Mostly False, Half True, Mostly True, and True.

The researchers collected data from May 1 to May 4, 2020, using Amazon Mechanical Turk. One hundred workers completed the task. Each worker assessed six real statements and two GOLD items for quality control. Workers provided a truthfulness judgment, a supporting URL and a written explanation. They also answered questions about their background and political views, and completed three cognitive reflection questions.

## Release Overview

The release covers the first crowdsourcing experiment, identified as MedicalTask-Set-1 in the study workspace. It contains 600 judgments on real statements and 200 GOLD judgments in the original data. Each of the 60 real statements has ten judgments.

### Historical Data

`Historical Data/S6.csv` contains the original 800 judgments and 58 columns, including the GOLD judgments, questionnaires, URLs and times. The original README is included in the same folder. Both files retain their original bytes.

### Crowdsourcing Task

`Crowdsourcing Task/` contains the assignment design and materials that describe the task:

- `hits.json` contains the original 100 units with eight statements each.
- `questionnaires.json` contains the questionnaire from the first experiment.
- `instructions.html`, `instructions.json`, `dimensions.json` and `search_engine.json` describe the task interface and search settings. These materials come from the task snapshot preserved with the later longitudinal study. They are provided as supporting material, not as a verified copy of the exact interface deployed in May 2020.
- `workers.json` contains empty lists for worker access. Worker identifiers used for participation controls are not distributed.

The task configuration does not include the live platform or search service.

### Worker Data

`DataFrame/` contains four tables:

- `workers_answers.csv`: 600 judgments on real statements from 100 workers.
- `workers_comments.csv`: 34 comments.
- `workers_questionnaires.csv`: 1,000 responses to ten questions.
- `workers_urls.csv`: 37,838 search and result records from 99 workers.

The detailed tables contain only records from the first experiment. They retain the pseudonyms used in the study workspace. The original file also contains the GOLD judgments, which are not included in the detailed answers table.

### Ground Truth and Release Metadata

`PolitiFact-Ground_Truth.csv` contains 60 statements with their PolitiFact labels, original document identifiers and fact check metadata. The original scale has six levels, with values from 0 (Pants on Fire) to 5 (True).

`release_manifest.json` describes the contents and sources. `checksums.csv` lists file sizes and SHA256 checksums. `CHANGELOG.md` records release changes. See `CITATION.cff`, `LICENSE.md` and `RIGHTS.md` for citation and reuse information.

## Using the Release

Use the original S6 file to reproduce the paper data, including GOLD judgments. Use the detailed tables for additional information about worker activity. Join judgments and ground truth using `doc_name` and `doc_id`. Use `worker_id`, `unit_id`, `batch_name` and document position to connect records where available.

The task form uses values from 1 to 6. The distributed judgments and PolitiFact labels use values from 0 to 5. Subtract 1 from the raw task value when comparing it with the ground truth.

The detailed answers match the original S6 judgments by unit, document position and document name. Their truthfulness values and labels agree. Some justification strings differ because the detailed tables use the curated study data; use S6.csv for the original text.

## Known Data Issues

Search activity is available for 99 of the 100 workers. Search logs also contain activity from earlier attempts. The search attempt counter starts at 0, whereas the answer attempt counter starts at 1. Do not assume every search record has a matching final judgment. The release preserves these records.

For `pants-on-fire_doc5`, the PolitiFact rating graphic indicates Pants on Fire, while the article text also uses False. The release retains the historical Pants on Fire label.

## Privacy and Responsible Reuse

The data contain participant contributions, including judgments, questionnaire responses, comments and search activity. Worker identifiers are pseudonyms. Do not attempt to identify or contact participants.

## Rights and Reuse

See `RIGHTS.md` and `LICENSE.md`. Participant contributions and material from PolitiFact, search services and other websites retain their own rights.

## Citation

Kevin Roitero, Michael Soprano, Beatrice Portelli, Damiano Spina, Vincenzo Della Mea, Giuseppe Serra, Stefano Mizzaro, and Gianluca Demartini. 2020. *The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?* Proceedings of the 29th ACM International Conference on Information and Knowledge Management (CIKM 2020), pages 1305 to 1314.

DOI: [10.1145/3340531.3412048](https://doi.org/10.1145/3340531.3412048)
