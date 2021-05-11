# Ad Perceptions Dataset
This is the dataset used in Survey 2 of our paper:

> Eric Zeng, Tadayoshi Kohno, Franziska Roesner. "What Makes a 'Bad' Ad? User Perceptions of Problematic Online Advertising." In CHI '21: Proceedings of the 2021 CHI Conference on Human Factors in Computing Systems. https://doi.org/10.1145/3411764.3445459.

**For more information about this project, and a user-friendly dataset viewer, please visit https://badads.cs.washington.edu/**

## Overview
This repository contains a dataset of 500 ads, labeled by 1025 annotators
with their opinions of the ads: things that they both like and dislike about
the ad.

### What's in the Dataset
- Screenshots of 500 ads randomly sampled from the web
- Users' labels for those ads (10+ users labeled ad)
- Clusters of ads based on distributions of users' labels, generated using
  Population Label Distribution Learning
- An HTML viewer for the clusters

### Required Software
- Web browser for HTML viewer
- PNG image viewer
- All other data is plaintext CSV or JSON, we suggest using pandas to
   work with the data

## Methodology
For a full description of our data collection methodology, please refer to the
paper.

## Description of Files
`data/` - This directory contains our full dataset from Survey 2.

Main files
- `ads_with_labels.json`: Start here, this file contains 500 ads, annotated with
the distribution of subjective opinion labels from participants, content labels,
user ratings, and opinion label cluster ids.
- `participant_context.csv`: This file includes supplemental information about
participants' demographics, general attitudes towards ads, and ad blocker usage.
- `ad_parent_urls.csv`: This file contains the URLs of the pages that the ads
in our dataset appeared on.

Additional files (the raw data joined into `ads_with_labels.json`)
- `cluster_id_to_paper_id.json`: Mapping of the cluster IDs in these files to the letter names used in the paper
- `content_labels.csv`: Table containing the researcher-generated content labels assigned to each ad
- `fmm_results.json`: Results of the FMM clustering algorithm. Contains a mapping of Ad IDs to cluster IDs (and other metadata)
- `label_dists_by_cluster.csv`: The opinion label distributions for each ad, grouped by cluster, and aggregated (mean).
- `opinion_label_dist.csv`: Table containing the opinion label distribution for each ad, as counts for each label. Also includes mappings of ad IDs to screenshot file name.
- `opinion_label_dist_norm.csv`: Table containing the opinion label distribution for each ad, normalized by the number of labelers per ad.
- `opinion_labels_per_participant.csv`: Raw opinion label data for each participant for each ad.
- `overall_ad_ratings.csv`: Table containing participants' overall ratings for each ad, and their optional free response opinion of the ad.
- `participant_context.csv`: Data from participants on their general feelings towards ads, and whether they use ad blockers.

`cluster_viewer/` - This directory contains an HTML viewer for easily viewing clusters
of ads generated in Section 4.2.3, including screenshots of ads, opinion labels and
content labels for each ad, and participant responses
- `index.html` - Open this file in your browser to use the cluster viewer interface.
- `screenshots/` - Directory where screenshots are kept. Some data files also reference these files.

