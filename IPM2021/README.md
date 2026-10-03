# The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale

This release contains the data and supporting material associated with the paper **“The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale”**, published in *Information Processing & Management* in 2021.

The study asks crowd workers to assess political statements using several dimensions of truthfulness rather than a single overall scale.

## Study Overview

The study contains **180 real statements**:

- 120 PolitiFact statements
- 60 RMIT ABC Fact Check statements

The PolitiFact set contains 20 statements for each of its six truthfulness levels. The RMIT ABC set contains 20 statements for each of its three target levels.

The task was conducted on Amazon Mechanical Turk with 200 workers based in the United States.

Each worker assessed nine real statements and two GOLD items. The study therefore collected:

- 1,800 real statement judgments
- 400 GOLD judgments
- 2,200 answer rows in total

For each statement, workers assessed Overall Truthfulness and reported their Confidence. They then searched for evidence, submitted a supporting URL, and assessed seven additional dimensions: Correctness, Neutrality, Comprehensibility, Precision, Completeness, Speaker's Trustworthiness, and Informativeness.

## Historical Data

`multidimensional.csv` is the original wide dataset distributed with the paper. It contains the crowd judgments together with task, questionnaire, demographic, evidence, and technical fields.

The historical file includes the GOLD items and is preserved unchanged.

The historical source is the `IPM2021/` directory from the public `crowdsourcingTruthfulness` repository at commit:

`7fbe9e7b399b34e3166018a7b190978ff5739428`

The publication era source archive remains preserved unchanged.

## Ground Truth

The package contains:

- `PolitiFact-Ground_Truth.csv`
- `RMIT_ABC_Fact_Check-Ground_Truth.csv`

These files provide the current canonical statement metadata in the common dataset format.

The native target semantics are preserved. PolitiFact keeps its six level scale and RMIT ABC keeps its three level scale.

## Historical Metadata Corrections

A complete comparison of the historical task identities found **16 PolitiFact metadata crossovers** and one separate RMIT ABC source error, `Liberal_Negative_doc9`.

The current ground truth, evidence metadata, and identifier crosswalk correct these mappings.

The historical `multidimensional.csv` is not rewritten. Historical identifiers remain available as provenance.

`Evidence Corpus/historical_claim_id_crosswalk.csv` connects the historical task identifiers with the corrected current fact check identifiers.

## Evidence Corpus

`Evidence Corpus/` contains the web evidence associated with the study.

The corpus contains **57,237 evidence records** covering all 180 real statements.

The main files are:

- `evidence_corpus.jsonl.gz`
- `crawl_metadata.csv`
- `evidence_corpus.summary.json`
- `historical_claim_id_crosswalk.csv`

The same web page can be associated with more than one statement. The historical crosswalk should be used when joining old task identifiers to the current evidence data.

## Supervised Learning Parameters

The publication era source included the classifier configurations used for the supervised learning experiments. They are reproduced here so that the release has one reader facing documentation file.

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

Historical publication data are preserved byte for byte in the source snapshot.

Corrections are applied only to current derived ground truth, evidence metadata, identifier mappings, and documentation.

`release_manifest.json` records the historical source paths, checksums, current package paths, omissions, and added files.

`checksums.csv` can be used to verify the package contents.

## Citation

If you use these data, please cite:

Michael Soprano, Kevin Roitero, David La Barbera, Davide Ceolin, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2021. *The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale*. *Information Processing & Management*, 58(6), 102710.

DOI: `10.1016/j.ipm.2021.102710`

Machine readable citation metadata are available in `CITATION.cff`.

## Privacy and Responsible Reuse

The release contains human research data, including internal worker identifiers, demographic information, judgments, task records, search activity, and questionnaire responses.

Do not attempt to identify or contact participants. Do not combine participant records with external information for the purpose of identifying participants.

Keep GOLD items separate from real statements when reproducing the main study analyses.

## Rights and External Content

This release contains material with different rights status.

The presence of a file in the package does not mean that every part of that file is covered by the same license.

External website content, fact check source material, participant contributions, and other third party material retain their original rights status.

See `LICENSE.md` and `RIGHTS.md` for details.

## Historical Notice

The publication era README stated that the information in the repository was provided for research purposes only. This notice is retained here as part of the historical documentation.
