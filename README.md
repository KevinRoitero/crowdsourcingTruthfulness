# Crowdsourcing Truthfulness

This repository collects datasets and supporting material for a series of studies on crowdsourced truthfulness assessment.

Each directory corresponds to a paper or study. Detailed dataset documentation is available inside the corresponding directory.

## Studies

| Data | Paper | Publication |
| --- | --- | --- |
| [IPM2021](./IPM2021/) | *The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale* | Information Processing & Management, 58(6), 102710, 2021. [DOI](https://doi.org/10.1016/j.ipm.2021.102710) |
| [PAUC2021](./PAUC2021/) | *Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19* | Personal and Ubiquitous Computing, 27, 59–89. [DOI](https://doi.org/10.1007/s00779-021-01604-6) |
| [CIKM2020](./CIKM2020/) | *The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?* | CIKM 2020, 1305–1314. [DOI](https://doi.org/10.1145/3340531.3412048) |
| [SIGIR2020](./SIGIR2020/) | *Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background* | SIGIR 2020, 439–448. [DOI](https://doi.org/10.1145/3397271.3401112) |
| [ECIR2020](./ECIR2020/) | *Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias* | ECIR 2020, 207–214. [DOI](https://doi.org/10.1007/978-3-030-45442-5_26) |

---

## The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale

The [IPM2021](./IPM2021/) directory contains the data and supporting material for the paper:

Michael Soprano, Kevin Roitero, David La Barbera, Davide Ceolin, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2021. *The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale*. Information Processing & Management, 58(6), 102710.

Paper: https://doi.org/10.1016/j.ipm.2021.102710

The current curated release is **version 1.4**. It contains:

- the original crowd judgment dataset
- canonical PolitiFact and RMIT ABC Fact Check ground truth
- the reconstructed evidence corpus and crawl metadata
- the historical identifier crosswalk
- integrity metadata and checksums
- citation, license, and rights documentation

See the [IPM2021 README](./IPM2021/README.md) for the study description, file documentation, provenance, historical corrections, supervised learning parameters, privacy guidance, and citation information.

Machine readable citation metadata are available in [IPM2021/CITATION.cff](./IPM2021/CITATION.cff).

Two large evidence files are stored with Git LFS:

- `IPM2021/Evidence Corpus/crawl_metadata.csv`
- `IPM2021/Evidence Corpus/evidence_corpus.jsonl.gz`

Install [Git LFS](https://git-lfs.com/) before cloning the repository if you need these files locally.

For rights and reuse information, see [IPM2021/LICENSE.md](./IPM2021/LICENSE.md) and [IPM2021/RIGHTS.md](./IPM2021/RIGHTS.md).

---

## Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19

The [PAUC2021](./PAUC2021/) directory contains the crowdsourced judgments used in the paper:

Kevin Roitero, Michael Soprano, Beatrice Portelli, Massimiliano De Luise, Damiano Spina, Vincenzo Della Mea, Giuseppe Serra, Stefano Mizzaro, and Gianluca Demartini. *Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19*. Personal and Ubiquitous Computing, 27, 59–89.

Paper: https://doi.org/10.1007/s00779-021-01604-6

Detailed information about the longitudinal crowdsourcing batches and dataset fields is available in the [PAUC2021 README](./PAUC2021/README.md).

### BibTeX

```bibtex
@article{roitero2021crowd,
  title = {Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19},
  author = {Kevin Roitero and Michael Soprano and Beatrice Portelli and Massimiliano De Luise and Damiano Spina and Vincenzo Della Mea and Giuseppe Serra and Stefano Mizzaro and Gianluca Demartini},
  journal = {Personal and Ubiquitous Computing},
  volume = {27},
  pages = {59--89},
  doi = {10.1007/s00779-021-01604-6}
}
```

---

## The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?

The [CIKM2020](./CIKM2020/) directory contains the crowdsourced judgments used in the CIKM 2020 full paper:

Kevin Roitero, Michael Soprano, Beatrice Portelli, Damiano Spina, Vincenzo Della Mea, Giuseppe Serra, Stefano Mizzaro, and Gianluca Demartini. 2020. *The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?* Proceedings of the 29th ACM International Conference on Information and Knowledge Management, 1305–1314.

Paper: https://doi.org/10.1145/3340531.3412048

Detailed dataset documentation is available in the [CIKM2020 README](./CIKM2020/README.md).

### BibTeX

```bibtex
@inproceedings{roitero2020infodemic,
  author = {Roitero, Kevin and Soprano, Michael and Portelli, Beatrice and Spina, Damiano and Della Mea, Vincenzo and Serra, Giuseppe and Mizzaro, Stefano and Demartini, Gianluca},
  title = {The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?},
  booktitle = {Proceedings of the 29th ACM International Conference on Information and Knowledge Management},
  pages = {1305--1314},
  year = {2020},
  doi = {10.1145/3340531.3412048}
}
```

---

## Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background

The [SIGIR2020](./SIGIR2020/) directory contains the data used in the SIGIR 2020 full paper:

Kevin Roitero, Michael Soprano, Shaoyang Fan, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2020. *Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background*. Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval, 439–448.

Paper: https://doi.org/10.1145/3397271.3401112

The study includes RMIT ABC Fact Check and PolitiFact statements together with crowdsourced judgments collected using different judgment scales. Detailed file and field documentation is available in the [SIGIR2020 README](./SIGIR2020/README.md).

### Talk

[Watch the SIGIR 2020 talk](https://www.youtube.com/watch?v=D10EtrThvbc)

### BibTeX

```bibtex
@inproceedings{roitero2020can,
  author = {Roitero, Kevin and Soprano, Michael and Fan, Shaoyang and Spina, Damiano and Mizzaro, Stefano and Demartini, Gianluca},
  title = {Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background},
  booktitle = {Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval},
  pages = {439--448},
  year = {2020},
  doi = {10.1145/3397271.3401112}
}
```

### Acknowledgements

This work was partially supported by a Facebook Research award and by an Australian Research Council Discovery Project (DP190102141).

We thank Devi Mallal from RMIT ABC Fact Check for facilitating access to the ABC dataset.

---

## Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias

The [ECIR2020](./ECIR2020/) directory contains the data used in the ECIR 2020 short paper for two different judgment scales:

- [S6](./ECIR2020/S6_Data.csv)
- [S100](./ECIR2020/S100_Data.csv)

The files also contain information about assessors' background used to analyze assessment bias.

David La Barbera, Kevin Roitero, Gianluca Demartini, Stefano Mizzaro, and Damiano Spina. 2020. *Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias*. Advances in Information Retrieval, ECIR 2020, Lecture Notes in Computer Science 12036, 207–214.

Paper: https://doi.org/10.1007/978-3-030-45442-5_26

**Best Short Paper Award, ECIR 2020.**

### BibTeX

```bibtex
@inproceedings{labarbera2020crowdsourcing,
  title = {Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias},
  booktitle = {Advances in Information Retrieval},
  author = {{La Barbera}, David and Roitero, Kevin and Demartini, Gianluca and Mizzaro, Stefano and Spina, Damiano},
  pages = {207--214},
  year = {2020},
  doi = {10.1007/978-3-030-45442-5_26}
}
```

### Links

- Presentation: http://www.youtube.com/watch?v=9wFFMcplvjk
- Paper: https://doi.org/10.1007/978-3-030-45442-5_26

### Acknowledgements

This work was partially supported by an Australian Research Council Discovery Project (DP190102141) and a Facebook Research award.

---

## Research Use

The study directories were created at different times and may follow different documentation and release conventions.

Please consult the documentation associated with the specific dataset you use. The current IPM 2021 release includes explicit citation, license, rights, privacy, provenance, and integrity documentation.
