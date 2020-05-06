# Overview
 
 - [SIGIR2020 paper](#can-the-crowd-identify-misinformation-objectively-the-effects-of-judgment-scale-and-assessors-background)
 - [ECIR2020 paper](#crowdsourcing-truthfulness-the-impact-of-judgment-scale-and-assessor-bias)

<hr>

# Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background

This repository contains the crowdsourced judgments used in the SIGIR'20 full paper titled "Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor's Background"

## Citation

If you use this resource, please cite our paper:

*Kevin Roitero, Michael Soprano, Shaoyang Fan, Damiano Spina, Stefano Mizzaro, and Gianluca Demartini. 2020. Can The Crowd Identify Misinformation Objectively? The Effects of Judgment Scale and Assessor’s Background.In SIGIR ’20: The 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval, July 25–30, 2020, Xi’an, China. ACM.*


### BibTeX

```bibtex
@InProceedings{roitero2020can,
author = {Roitero, Kevin and Soprano, Michael and Fan, Shaoyang and Spina, Damiano
          and Mizzaro, Stefano and Demartini, Gianluca},
title = {Can The Crowd Identify Misinformation Objectively? 
         The Effects of Judgment Scale and Assessor’s Background},
booktitle = {Proceedings of SIGIR'20},
year={2020}
}
```

## Dadaset Description
the dataset contains the following data:

* `unit_id`: unit number (one worker for each unit);
* `S100_document_position`: position of the document in the task;
* `S100_amount_try`: number of attempts left to finish the task (counting backwards from 10);
* Answers to Questionnaire:
  * `S100_age`
  * `S100_degree`
  * `S100_money` 
  * `S100_consideration`
  * `S100_political_views` 
  * `S100_southern_border` 
  * `S100_climate`
* Answer to CRT Questions:
  * `S100_cognitive_1` 
  * `S100_cognitive_2` 
  * `S100_cognitive_3`
*`statement_id`: id of the statement;
* `name_unique`: unique name for documents;
* `statement` 
* `speaker`
* `job`: of the speaker;
* `context`: of the statement;
* `year`
* `party`:of the speaker;
* `source`: Politifact or ABC;
* `S100_time_elapsed`: time spent by the worker on the document (cumulative for each document);
* `S100_truth_level`: truthfulness value expressed by the worker (in the given scale);
* `S100_binger_query`: query issued by the worker;
* `S100_binger_url`: url selected by the worker; 
* `politifact_label`: truth label express by Politifact experts;
* `abc_label`: truth label express by ABC experts.


## Acknowledgements

This work is partially supported by a Facebook Research award
and by an Australian Research Council Discovery Project (DP190102141).
We thank Devi Mallal from RMIT ABC Fact Check for facilitating access to the ABC dataset.




<hr>


# Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias


This repository contains the crowdsourced judgments used in the ECIR'20 short paper titled "Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias", for two two different judgment scales: [S6](./ECIR2020/S6_data.csv) and [S100](./ECIR2020/S100_data.csv). 

The files also include the collected information about assessors’ background that allowed us to analyse assessment bias. 

## Citation

If you use this resource, please cite our paper:

*La Barbera D., Roitero K., Demartini G., Mizzaro S., Spina D. (2020) [Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias](https://link.springer.com/chapter/10.1007/978-3-030-45442-5_26). In: Jose J. et al. (eds) Advances in Information Retrieval. ECIR 2020. Lecture Notes in Computer Science, vol 12036. Springer, Cham.* **[Best Short Paper Award](https://ecir2020.org/awards/).**

### BibTeX

```bibtex
@inproceedings{labarbera2020crowdsourcing, 
   title={{Crowdsourcing Truthfulness: The Impact of Judgment Scale and Assessor Bias}},
   booktitle={Proceedings of ECIR'20},
   author={{La Barbera}, David and Roitero, Kevin and Demartini, Gianluca and Mizzaro, Stefano and Spina, Damiano},
   year={2020}
}
```

## Links of Interest
 - Presentation: http://www.youtube.com/watch?v=9wFFMcplvjk
 - Paper: https://link.springer.com/chapter/10.1007/978-3-030-45442-5_26


## Acknowledgements

This work is partially supported by an Australian Research Council Discovery Project (DP190102141) and a Facebook Research award.
