# Bitcoin_Natural_Langauge_Processing
Bitcoin tweet analysis using LDA and NMF topic modelling, CryptoBERT sentiment analysis, and regression and random forest models to test whether sentiment improves next-day volatility forecasts. Includes the Python notebook and executive report.
# Bitcoin Topics, Sentiment and Volatility

**EDAB6808 · Assignment 4 · University of the Free State**

## Project overview

This project analyses Bitcoin-related tweets to identify recurring discussion themes and assess whether estimated sentiment improves forecasts of next-day Bitcoin market movement. It combines topic modelling, transformer-based sentiment analysis, manual validation and chronological forecast evaluation.

## Data and scope

The supplied Kaggle Bitcoin Tweets Dataset 2025–2026 provides the text corpus. After removing unusable dates or text, **4,689,239 tweets** remain in the common modelling base.

- Topic fitting uses **26,000 unique English texts**, balanced across the supplied months.
- CryptoBERT scores a reproducible daily sample of **40,083 tweets**.
- **100 tweets** receive independent manual labels for comparison with the model.
- The forecasting experiment uses **200 usable origins**: 160 for training and 40 for testing, in chronological order.

## Analytical approach

### Topic modelling

Clean and represent the text using CountVectorizer and TF–IDF. Compare Latent Dirichlet Allocation (LDA) with Non-negative Matrix Factorisation (NMF), assess topic-count diagnostics, interpret the selected themes and examine their distribution over time.

### Sentiment and forecasting

Apply CryptoBERT to estimate bullish, bearish or neutral outlook. Compare its predictions with manual labels, aggregate daily sentiment and test its incremental value alongside market variables and tweet volume. Linear regression and Random Forest models are assessed on the same chronological test origins. Next-day absolute return serves as the market-movement/volatility proxy.

## Key findings

- **Nine-topic NMF** was selected for descriptive interpretation, with stronger final coherence and keyword diversity than the compared LDA model.
- Trading and market discussion represented **42.13% of the balanced topic-fitting sample**. This is not its estimated share of every collected tweet.
- CryptoBERT agreed with the 100 manual labels in **43%** of cases, highlighting uncertainty in the sentiment measure.
- Adding sentiment reduced Random Forest MAE by approximately **5.62%**, while its RMSE improved by only approximately **0.04%**.
- Market-only linear regression achieved the lowest MAE overall; regression with market variables and tweet volume achieved the lowest RMSE.

The evidence supports topic modelling as a descriptive tool, while sentiment produced a modest, model-dependent forecasting gain.

## Repository materials

| Material | Contents |
| --- | --- |
| Jupyter notebook (`.ipynb`) | Corpus preparation, topic models, sentiment analysis, manual-label comparisons, forecasts and saved outputs. |
| Executive report (`.pdf`) | Topic interpretation, charts, validation results, forecast comparisons and limitations. |

## Tools and skills

Python, pandas, NumPy, scikit-learn, Transformers/CryptoBERT, matplotlib and seaborn. The work develops large-corpus preparation, text representation, topic interpretation, sentiment validation and time-aware model comparison.

## Interpretation and limitations

Some text refers to 2021–2022 despite supplied timestamps in 2025–2026. Collection gaps occur on **161 of 362 calendar days**, and missing collection days cannot be interpreted as zero tweet activity. Balanced topic samples do not represent full-corpus topic shares, manual sentiment validation is small, and the forecasting comparison covers only 40 test origins.

These results describe an academic experiment; they do not establish robust trading performance or a consistently useful sentiment signal. The central lesson is to validate an NLP measure before relying on it as a forecasting input.

## Credits

Collaborative coursework by **Mamello Malape and Reatile Seekoei** for EDAB6808 at the University of the Free State. The executive report includes dataset references and detailed analytical decisions.
