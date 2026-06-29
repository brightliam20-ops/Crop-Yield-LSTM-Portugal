## Data Sources

- **Crop yield and pesticide use:** [FAOSTAT](https://www.fao.org/faostat/en/) (Food and Agriculture Organization of the United Nations)
- **Climate data:** [NASA POWER](https://power.larc.nasa.gov/) (monthly temperature and precipitation, aggregated to growing-season features)

Crops studied: Grapes, Potatoes, Wheat (Portugal, 1990–2023).

## Method Summary

- Data was converted into 5-year sliding-window sequences per crop, used to predict the following year's yield.
- An LSTM with a crop embedding layer was trained using PyTorch, with early stopping and L2 regularization to address the small dataset size.
- A Random Forest Regressor (scikit-learn) was trained on the same data as a baseline for comparison.
- The dataset was split chronologically (not randomly) into training, validation, and test sets to avoid data leakage.

## Key Result

The LSTM and Random Forest achieved nearly identical test performance (R² ≈ 0.82 for both), suggesting that the added complexity of the LSTM did not provide a meaningful advantage on this dataset size (66 training sequences). Both models failed to anticipate a structural rise in potato yields after 2016, since this trend had no precedent in the training data. Full discussion is available in the final report.

## Use of AI

Code in this project was developed with the assistance of Claude (Anthropic). All AI-assisted code sections, along with the prompts used and modifications made, are documented in the notebook.
