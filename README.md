# Disaster Tweet Analysis

An R-based text analysis project that explores disaster-related tweets and compares clustering, topic modeling, and classification methods.

## Overview

Disaster-related words do not always describe real emergencies. For example, “The street is flooded” may describe a disaster, while “My inbox is flooded” uses the same word figuratively.

This project examines whether text features can help distinguish tweets about actual disasters from posts using similar language in other contexts.

The analysis combines exploratory visualizations, text preprocessing, numerical representations of text, and several modeling approaches.

## Methods

| Method | Purpose |
| --- | --- |
| Text preprocessing | Remove punctuation, common stop words, and other noise. |
| Stemming | Reduce related word forms to a shared root. |
| Unigrams and bigrams | Represent text using individual words and pairs of adjacent words. |
| Document-term matrices | Record word occurrences for each tweet in a numerical table. |
| Singular Value Decomposition (SVD) | Reduce a large text matrix to fewer numerical dimensions. |
| K-means clustering | Group tweets according to similarity. |
| Gaussian mixture modeling | Model groups as overlapping statistical distributions. |
| Latent Dirichlet Allocation (LDA) | Discover recurring topics from word patterns. |
| Logistic regression and random forests | Predict the disaster label using labeled examples. |

Cluster numbers are arbitrary. A cluster must be compared with known labels before interpreting it as disaster-related or non-disaster-related.

## Workflow

1. Load the training and test data.
2. Explore missing values, keywords, locations, and text length.
3. Visualize word frequencies and word clouds.
4. Clean the text and construct numerical features.
5. Apply dimensionality reduction and clustering.
6. Explore latent topics.
7. Train classifiers and examine their predictions.

## Repository Contents

| File | Description |
| --- | --- |
| `Project.Rmd` | Main analysis document containing R code and written explanations. |
| `推特文字探勘.pdf` | Detailed project report in Chinese. |
| `PPT.pdf` | Presentation slides. |

## Data Requirements

The analysis reads `train.csv` and `test.csv` from its working directory. These files are not included in the repository.

The code expects fields such as `id`, `keyword`, `location`, and `text`, with `target` labels available for the training data.

The original analysis attributes the data to Appen. When obtaining a replacement copy, verify that its columns and label definitions match the code.

## Tools

The analysis uses R and R Markdown (a format combining executable code with written documentation).

Core packages include:

- `tidyverse` and `tm` for data preparation and text processing
- `irlba` for dimensionality reduction
- `mclust` for mixture modeling
- `text2vec` for topic modeling
- `caret`, `randomForest`, and `ranger` for modeling
- `wordcloud` for text visualization

Additional package calls appear throughout `Project.Rmd`.

## Getting Started

1. Obtain the repository files.
2. Place compatible `train.csv` and `test.csv` files in the working directory.
3. Open `Project.Rmd` in RStudio or another R Markdown environment.
4. Install the packages referenced in the document.
5. Review the data-loading and preprocessing sections, then run the analysis section by section.

PDF rendering uses XeLaTeX (a PDF typesetting engine) and a configured Chinese font. The document also contains Windows-specific graphics calls that may require changes on other operating systems.

## Scope and Reproducibility

The task concerns whether a tweet describes a disaster; it does not independently verify that an event occurred.

The repository preserves the original analysis. Package versions are not pinned, and a fresh execution may require environment or code adjustments.
