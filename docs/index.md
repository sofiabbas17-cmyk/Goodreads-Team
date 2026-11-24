---
layout: default
title: "GoodReads Data"
---

<!--
This website is public. Do not include private data, credentials, identifying
information, or material that you do not have permission to share.
-->

# Exploring GoodReads Reviews: Children Books' 1-Star Reviews

**Team:** [Keai, Melody, Sofia]

[In two or three sentences, state what you studied and the main result.]

## Research question and motivation

**Research question:** Among one-star reviews of children’s books on Goodreads, what portion of the reviews are complaints of appropriateness and which topics or themes do they judge as inappropriate, particularly for the intended child audience?

We expect a majority of these one-star reviews to consist of dissatisfaction towards quality of storytelling and objections towards content matter. We are interested in exploring how text analysis of one-star reviews may reveal the values and literary standards held by readers (particularly by parental figures/adults actually writing the reviews). What constitutes appropriate content for a children’s book can be a controversial topic that reflects slices of the present cultural moment. 

## Data

- **Source:** UCSD Goodreads Book Graph dataset
- **Unit of analysis:** One user review of one children's book
- **Coverage:** The cleaned dataset contains 9,725 English-language one-star reviews of books in the Goodreads children's category, dated 2007–2017. The analysis includes 8,801 reviews after excluding reviews with fewer than 10 words.
- **Access and ethics:** Although the dataset is publicly accessible, it contains user-generated content and user identifiers. We should avoid disclosing identifying information and report findings at an aggregate level.
Additionally, we cannot confirm whether users have actually read the books they reviewed, which raises concerns about the authenticity of some reviews.


We started with the children's-book subset of the UCSD Goodreads Book Graph and focused on one-star reviews to study the reasons behind the lowest ratings. We dropped reviews with missing text, used automated language detection to retain English reviews, and removed duplicate combinations of reviewer and review text. The cleaning notebook also explores reviews from 2015–2017. The analysis uses the cleaned export covering the full 2007–2017 period. See the [data cleaning notebook](https://github.com/sofiabbas17-cmyk/Goodreads-Team/blob/main/notebooks/01_clean_data.ipynb).

## Methods

**Keyword screening.** We searched the 8,801 eligible reviews for words and phrases such as “inappropriate,” “not suitable,” “too scary,” and “not for kids.” The case-insensitive search flagged 224 candidates, all of which were exported for review. The triggering phrase was retained to show why each review was flagged.

**Hand coding and comparison with Gemini.** We read the full text of each candidate and coded whether the reviewer raised an appropriateness concern. Complaints about the plot or characters alone were coded as no. Confirmed complaints could receive multiple theme labels, such as age-appropriateness, bad influence, or violence.The project also saved Gemini theme labels for the complaints as a comparison with the human labels. Reviews without a keyword match could still contain appropriateness concerns, so the confirmed share measures complaints identified by this procedure.

**Exploratory text analysis.** We compared the keyword-matched and unmatched reviews using one- and two-word phrases that appeared in at least 15 reviews. We ranked phrases by a weighted log-odds score and removed selected author names, book-title terms, and trigger words from the comparison. For the unmatched group, we also inspected a random sample of 15 review excerpts and used an eight-topic non-negative matrix factorization (NMF) model on TF–IDF-weighted words to explore recurring complaints. See the [exploration notebook](https://github.com/sofiabbas17-cmyk/Goodreads-Team/blob/main/notebooks/02_explore_data.ipynb) and the [figure notebook](https://github.com/sofiabbas17-cmyk/Goodreads-Team/blob/main/notebooks/04_make_figures.ipynb).

## Findings

### Finding 1: [Descriptive title]

[Add a readable figure or table and explain what it shows. Include units,
sample sizes, or evaluation metrics when relevant.]

### Finding 2: [Descriptive title]

[Add another result only if it helps answer the research question.]

## Interpretation and limitations

- **Strongest claim supported:** [What can you conclude from the evidence?]
- **Claim not supported:** [What tempting conclusion should readers avoid?]
- **Important limitations:** [Where can the data or method fail?]
- **Social-science implications:** [Why do the findings matter in context?]

## Reproducibility

- **Repository:** [Link to the project repository.]
- **Environment:** Run `uv sync --frozen` from the repository folder.
- **Run order:** [List the notebooks and scripts in the order a reader should
  run them, or link to the complete run order in the README.]
- **Data access:** [Explain how an authorized reader can obtain or reconstruct
  the data.]

## References

[List data sources, research literature, software, and other material cited on
this page. Include links where appropriate.]
