# The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?

This repository contains the crowdsourced judgments used in the CIKM'20 full paper titled "The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?"

## Crowdsourced Dataset 

The dataset obtained from our crowdsourcing experiments is organised in one file for the scale used: [S6](./crowdsourced-data/S6.csv).

The file contains the following information:

* `unit_id`: unit number (one worker for each unit);
* `tries_amount`: number of attempts left to finish the task (counting backwards from 10);
* `questionnaire_amount`: number of questionnaire to be performed;
* `dimensions_amount`: number of dimensions to be assessed;
* `document_amount`: number of statements to be assessed;
* `current_try`: number of the current worker try;
* Standard questionnaire data:
  * `q_0_age_question`
  * `q_0_age_answer`
  * `q_0_age_value`
  * `q_0_school_question`
  * `q_0_school_answer`
  * `q_0_school_value`
  * `q_0_taxes_question`
  * `q_0_taxes_answer`
  * `q_0_taxes_value`
  * `q_0_political_views_question`
  * `q_0_political_views_answer`
  * `q_0_political_views_value`
  * `q_0_consideration_question`
  * `q_0_consideration_answer`
  * `q_0_consideration_value`
  * `q_0_southern_border_question`
  * `q_0_southern_border_answer`
  * `q_0_souther_border_value`
  * `q_0_environment_question`
  * `q_0_enviroment_answer`
  * `q_0_environment_value`
  * `q_0_time_elapsed`: number of seconds needed to finish the questionnaire;
  * `q_0_accesses`: number of accesses to the questionnaire page;
* First CTR questionnaire data:
  * `q_1_farmers_question`
  * `q_1_farmers_value`
  * `q_1_time_elapsed`: number of seconds needed to finish the questionnaire;
  * `q_1_accesses`: number of accesses to the questionnaire page;
* Second CTR questionnaire data:
  * `q_2_marks_question`
  * `q_2_marks_value`
  * `q_2_time_elapsed`: number of seconds needed to finish the questionnaire;
  * `q_2_accesses`: number of accesses to the questionnaire page;
* Third CTR questionnaire data:
  * `q_3_athletics_question`
  * `q_3_athletics_value`
  * `q_3_time_elapsed`: number of seconds needed to finish the questionnaire;
  * `q_3_accesses`: number of accesses to the questionnaire page;
* `doc_index`: index of the statement;
* `doc_name`: unique name for documents;
* `doc_statement` 
* `doc_claimant`
* `doc_date`
* `doc_originatedFrom`: context of the statement;
* `doc_ground_truth_value`: ground truthfulness label expressed by the expert fact checker (in the given scale);
* `doc_ground_truth_label`: ground truthfulness label expressed by the expert fact checker (in the given scale);
* `doc_truthfulness_value`: truthfulness value expressed by the worker (in the given scale);
* `doc_truthfulness_label`: truthfulness label expressed by the worker (in the given scale);
* `doc_truthfulness_justification`: justification provided by the worker; 
* `doc_truthfulness_url`: url selected by the worker; 
* `doc_accesses`: number of accesses to each statement;
* `doc_time_elapsed`: time spent by the worker on the statement (cumulative for each document);

## Citation

If you use this resource, please cite our paper:

*Kevin Roitero, Michael Soprano, Beatrice Portelli, Damiano Spina, Vincenzo Della Mea, Giuseppe Serra, Stefano Mizzaro and Gianluca Demartini. 2020. The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?. In CIKM ’20: 29th ACM International Conference on Information and Knowledge Management (CIKM2020), Online. October 19-23, 2020.*

### BibTeX

```bibtex
@InProceedings{roitero2020infodemic,
author = {Roitero, kevin and Soprano, Michael and  Portelli, Beatrice and  Spina, Damiano and Della Mea, Vincenzo and   Serra, Giuseppe and   Mizzaro, Stefano and Demartini, Gianluca},
title = {The COVID-19 Infodemic: Can the Crowd Judge Recent Misinformation Objectively?},
booktitle = {Proceedings of CIKM'20},
year={2020}
}
```

## Disclaimer Notice

The information included in this repository is for research purposes only.
