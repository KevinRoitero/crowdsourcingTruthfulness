# The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale

This release contains the data and supporting material associated with the paper **“The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale”**, published in *Information Processing & Management* in 2021.

The study examines how crowd workers assess political statements using several dimensions of truthfulness rather than a single overall scale.

## Study Overview

The study uses 180 real statements:

- 120 PolitiFact statements, with 20 statements for each of its six truthfulness levels.
- 60 RMIT ABC Fact Check statements, with 20 statements for each of its three target levels.

The crowdsourcing task involved 200 workers based in the United States on Amazon Mechanical Turk. Each worker assessed nine real statements and two GOLD items used for quality control. The available answer records contain 2,200 judgments: 1,800 on real statements and 400 on GOLD items.

For each statement, workers assessed Overall Truthfulness and reported their Confidence. They then searched for evidence, submitted a supporting URL, and assessed seven additional dimensions: Correctness, Neutrality, Comprehensibility, Precision, Completeness, Speaker's Trustworthiness, and Informativeness.

## Dataset Structure

`multidimensional.csv` contains the 2,200 judgments distributed with the original paper, including GOLD items, in a single table.

`Crowdsourcing Task/` contains eight configuration files describing the instructions, questionnaires, dimensions, assignments, and search interface.

`DataFrame/` contains six tables:

- `workers_answers.csv`: individual judgments and supporting URLs for the real statements and GOLD items.
- `workers_comments.csv`: worker comments.
- `workers_dimensions_selection.csv`: records of dimension selections.
- `workers_mturk_data.csv`: task metadata for 200 workers, with 22 columns including the internal `worker_id`. External Mechanical Turk `AssignmentId` and `HITId` are not distributed.
- `workers_questionnaires.csv`: questionnaire responses.
- `workers_urls.csv`: recorded search activity and result metadata.

`PolitiFact-Ground_Truth.csv` and `RMIT_ABC_Fact_Check-Ground_Truth.csv` contain the corrected metadata and native truthfulness labels for the 180 real statements.

`Evidence Corpus/` contains the web evidence, crawl metadata, corpus summary, and statement identifier crosswalk.

## Ground Truth

PolitiFact uses its native six-level truthfulness scale. RMIT ABC Fact Check uses its native three-level target semantics. The scales have not been harmonized.

The corrected statement metadata resolve 16 PolitiFact metadata crossovers and a separate RMIT ABC source error, `Liberal_Negative_doc9`.

`Evidence Corpus/historical_claim_id_crosswalk.csv` connects recorded task identifiers to the corrected fact-check identifiers. Use this mapping to join task records, ground truth, and evidence rather than assuming that historical document names alone identify the correct statements.

## Evidence Corpus

The corpus contains 57,237 evidence records covering all 180 real statements.

- `evidence_corpus.jsonl.gz`: text extracted from web pages associated with the study.
- `crawl_metadata.csv`: metadata connecting recorded search activity to page content.
- `evidence_corpus.summary.json`: corpus counts and validation information.
- `historical_claim_id_crosswalk.csv`: the statement identifier mapping.

The same web page can be associated with more than one statement. Extracted content originates from external websites, which may have changed or become unavailable since collection.

## Known Data Issues

- `Crowdsourcing Task/hits.json` contains 150 distinct real statement identifiers, whereas `DataFrame/workers_answers.csv` contains all 180. The PolitiFact and GOLD assignments agree with the performed answers, but the RMIT ABC assignments differ in 99 of the 200 worker units. Use the answer table as the record of the assignments actually performed.
- Of the 180 real statements, 174 have ten judgments, three have nine, and three have eleven.
- One real PolitiFact answer is tagged `gold_question` in the recorded data. The tag is preserved; the corrected statement identity identifies it as a real statement.
- The search records cover 198 of the 200 workers. Two workers have answers but no recorded search activity.
- One worker and unit pair has different attempt numbers in the answer, dimension selection, and questionnaire logs. Do not assume those attempts should be merged.

The records in `multidimensional.csv` and `DataFrame/workers_answers.csv` match using the combination of `unit_id`, `doc_index`, and `doc_name`. These keys identify all 2,200 rows uniquely in both tables. Of the 37 shared columns, only `doc_statement` and `doc_ground_truth_politifact_label` differ, in the same ten rows belonging to one statement. All other shared values, including the workers' judgments, agree. The recorded values in both tables are preserved.

## Using the Dataset

Use `multidimensional.csv` to reproduce the analyses based on the dataset distributed with the paper. Use `DataFrame/` and `Crowdsourcing Task/` to investigate the detailed task and worker activity. The two answer tables describe the same judgments but should not be silently substituted for one another.

Use the corrected ground truth and identifier crosswalk when joining judgments to fact-check labels or evidence. Keep GOLD items separate from real statements when reproducing the main analyses.

## Supervised Learning Parameters

The following classifier configurations were used in the supervised learning experiments reported in the paper.

### Random Forest

```text
RandomForestClassifier(
    n_estimators=100,
    criterion="gini",
    max_depth=None,
    min_samples_split=2,
    min_samples_leaf=1,
    min_weight_fraction_leaf=0.0,
    max_features="auto",
    max_leaf_nodes=None,
    min_impurity_decrease=0.0,
    min_impurity_split=None,
    bootstrap=True,
    oob_score=False,
    n_jobs=None,
    random_state=0,
    verbose=0,
    warm_start=False,
    class_weight=None,
    ccp_alpha=0.0,
    max_samples=None
)
```

### Logistic Regression

```text
LogisticRegression(
    penalty="l2",
    dual=False,
    tol=0.0001,
    C=1.0,
    fit_intercept=True,
    intercept_scaling=1,
    class_weight=None,
    random_state=None,
    solver="lbfgs",
    max_iter=100,
    multi_class="auto",
    verbose=0,
    warm_start=False,
    n_jobs=None,
    l1_ratio=None
)
```

### AdaBoost

```text
AdaBoostClassifier(
    base_estimator=None,
    n_estimators=50,
    learning_rate=1.0,
    algorithm="SAMME.R",
    random_state=None
)
```

### Gaussian Naive Bayes

```text
GaussianNB(
    priors=None,
    var_smoothing=1e-09
)
```

### Support Vector Machine

```text
SVC(
    C=1.0,
    kernel="rbf",
    degree=3,
    gamma="scale",
    coef0=0.0,
    shrinking=True,
    probability=False,
    tol=0.001,
    cache_size=200,
    class_weight=None,
    verbose=False,
    max_iter=-1,
    decision_function_shape="ovr",
    break_ties=False,
    random_state=None
)
```

These settings are preserved as reported with the original study and are not updated to newer scikit learn defaults.

## Provenance and Integrity

The original paper dataset comes from the [IPM2021 collection](https://github.com/KevinRoitero/crowdsourcingTruthfulness/tree/7fbe9e7b399b34e3166018a7b190978ff5739428/IPM2021). The detailed task and worker records come from the same study. The evidence and corrected statement identities are documented in the release metadata.

`release_manifest.json` records file sources, documented transformations, and checksums. `checksums.csv` provides file sizes and SHA256 hashes.

## Privacy and Responsible Reuse

The release contains human research data, including pseudonymous internal worker identifiers, demographic information, judgments, task records, comments, search activity, and questionnaire responses. Internal identifiers link records within the study. External Mechanical Turk assignment and HIT identifiers are not distributed in the worker metadata table.

A preliminary screening found no email patterns in the comments, questionnaire answers, or search queries checked, but some search result titles and snippets contain email patterns. These may come from external web pages. This screening is not a guarantee that the material is free of personal information. Exercise care when reusing free text and search results.

Do not attempt to identify or contact participants. Do not combine participant records with external information for the purpose of identifying participants. Report participant characteristics at an appropriate level of aggregation.

## Rights and Reuse

Different types of material have different rights status. The data associated with the paper were originally made available for research purposes. See `LICENSE.md` and `RIGHTS.md` for the scope of permissions and responsibilities. External website content, search results, fact-check source material, participant contributions, and other third-party material are not automatically covered by the license for author-created material.

## Citation

Michael Soprano, Kevin Roitero, David La Barbera, Davide Ceolin, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2021. *The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale*. **Information Processing & Management**, 58(6), Article 102710. DOI: [10.1016/j.ipm.2021.102710](https://doi.org/10.1016/j.ipm.2021.102710).

Machine readable citation metadata are available in `CITATION.cff`.
