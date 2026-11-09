# Crowdsourcing Truthfulness

This repository collects datasets and supporting material for studies on crowdsourced truthfulness assessment. Each study has its own directory with documentation of the data, experimental setup, and relevant limitations.

## Studies

| Dataset | Paper | Publication |
| --- | --- | --- |
| [ECIR2020](./ECIR2020/) | *Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias* | ECIR 2020, 207–214. [DOI](https://doi.org/10.1007/978-3-030-45442-5_26) |
| [SIGIR2020](./SIGIR2020/) | *Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background* | SIGIR 2020, 439–448. [DOI](https://doi.org/10.1145/3397271.3401112) |
| [CIKM2020](./CIKM2020/) | *The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?* | CIKM 2020, 1305–1314. [DOI](https://doi.org/10.1145/3340531.3412048) |
| [IPM2021](./IPM2021/) | *The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale* | *Information Processing & Management*, 58(6), 102710 (2021). [DOI](https://doi.org/10.1016/j.ipm.2021.102710) |
| [PAUC2021](./PAUC2021/) | *Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19* | *Personal and Ubiquitous Computing*, 27, 59–89 (2023; first published online in 2021). [DOI](https://doi.org/10.1007/s00779-021-01604-6) |

## Datasets

### ECIR2020

[ECIR2020](./ECIR2020/) contains crowd assessments collected using [six-level](./ECIR2020/S6_Data.csv) and [100-level](./ECIR2020/S100_Data.csv) judgment scales, including assessor background information.

The paper received the **Best Short Paper Award at ECIR 2020**. [Watch the presentation](https://www.youtube.com/watch?v=9wFFMcplvjk).

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

### Acknowledgements

This work was partially supported by an Australian Research Council Discovery Project (DP190102141) and a Facebook Research award.

### SIGIR2020

[SIGIR2020](./SIGIR2020/) contains PolitiFact and RMIT ABC Fact Check statements and crowd judgments collected using different truthfulness scales. See the [SIGIR2020 README](./SIGIR2020/README.md) for the datasets and field definitions.

[Watch the SIGIR 2020 talk](https://www.youtube.com/watch?v=D10EtrThvbc).

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

### CIKM2020

[CIKM2020](./CIKM2020/) contains the crowd judgments for *The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?*. See the [CIKM2020 README](./CIKM2020/README.md) for the dataset and its assessment fields.

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

### IPM2021

[IPM2021](./IPM2021/) contains the original multidimensional truthfulness judgments and the expanded **version 1.5** release. It includes the original paper dataset, eight crowdsourcing task files, six detailed tables of worker judgments and activity, PolitiFact and RMIT ABC Fact Check ground truth, and a reconstructed evidence corpus.

The study covers **180 real statements** (120 PolitiFact and 60 RMIT ABC Fact Check) and preserves the native truthfulness scales. The original study data and historical source materials remain preserved.

See the [IPM2021 README](./IPM2021/README.md) for file descriptions, provenance, corrections, privacy and reuse information. Machine-readable citation metadata are available in [CITATION.cff](./IPM2021/CITATION.cff).

### BibTeX

```bibtex
@article{soprano2021many,
  title = {The Many Dimensions of Truthfulness: Crowdsourcing Misinformation Assessments on a Multidimensional Scale},
  author = {Soprano, Michael and Roitero, Kevin and {La Barbera}, David and Ceolin, Davide and Spina, Damiano and Mizzaro, Stefano and Demartini, Gianluca},
  journal = {Information Processing & Management},
  volume = {58},
  number = {6},
  pages = {102710},
  year = {2021},
  doi = {10.1016/j.ipm.2021.102710}
}
```

### PAUC2021

[PAUC2021](./PAUC2021/) contains the longitudinal COVID-19 truthfulness study data. The study used **60 PolitiFact statements**, with ten statements per truthfulness level, and collected judgments across four monthly rounds between May and August 2020.

The directory provides two complementary resources:

- The **12 original batch CSVs**, preserved unchanged, including the study's historical tasks and returning-worker subsets.
- The [**extended dataset, version 1.1**](./PAUC2021/pauc2021_paper_extended_release_v1.1.zip), containing five curated tables of judgments and worker activity, the 60-statement ground truth, and release documentation and checksums.

The extended tables contain **3,606 judgments** on real statements by **410 pseudonymous workers**, along with dimension selections, questionnaires, comments, and search activity. The original batch files are not duplicated in the ZIP; they remain available separately in the same directory.

See the [PAUC2021 README](./PAUC2021/README.md) for the original and extended data, known irregularities, provenance, and reuse conditions.

### BibTeX

```bibtex
@article{roitero2021crowd,
  title = {Can the Crowd Judge Truthfulness? A Longitudinal Study on Recent Misinformation about COVID-19},
  author = {Kevin Roitero and Michael Soprano and Beatrice Portelli and Massimiliano De Luise and Damiano Spina and Vincenzo Della Mea and Giuseppe Serra and Stefano Mizzaro and Gianluca Demartini},
  journal = {Personal and Ubiquitous Computing},
  volume = {27},
  pages = {59--89},
  year = {2023},
  doi = {10.1007/s00779-021-01604-6}
}
```

## Access and reuse

Some large IPM2021 files are managed with [Git LFS](https://git-lfs.com/), as specified in [`.gitattributes`](./.gitattributes). Install Git LFS before cloning the repository if you need those files.

Please cite the corresponding paper when using a dataset. Consult the README and, where available, the license and rights documentation in each study directory for provenance, limitations, and reuse conditions.
