# U.S. Happiness and Survey Responses

## Project question

How are self-reported health, family income, marital status, age, and schooling associated with reported happiness among U.S. adults surveyed in 2024?

This is an observational analysis. The results describe associations in survey responses and do not establish causes.

## Data

The project uses the 2024 General Social Survey (GSS), release 3a, collected by NORC at the University of Chicago. The official source and documentation are available from the [GSS data page](https://gss.norc.org/get-the-data/stata.html) and [2024 codebook](https://gss.norc.org/content/dam/gss/get-documentation/pdf/codebook/GSS%202024%20Codebook%20R3a.pdf).

`dataset.csv` is the project input: a 9-column respondent-level extract with 3,986 rows. `cleaned_dataset.csv` is a separate working copy produced by the notebook. Both retain all respondents and blank missing answers. The cleaned copy represents age `89` as the top-coded answer “89 or older,” and education `20` as “20 or more years.” Neither code is an exact value for calculations requiring exact age or schooling years.

The project retains the `amerstatus` sample indicator and `wtssnrps_as` combined-sample weight. The current charts and chi-square tests are unweighted; their results are descriptions/tests of the observed sample, not design-adjusted U.S. population estimates.

## Project files

- `happiness_analysis.ipynb`: milestone documentation, data cleaning, descriptive statistics, inferential tests, five static visualizations, and the interactive dashboard export code.
- `dataset.csv`: selected input extract; do not overwrite it during cleaning.
- `cleaned_dataset.csv`: cleaned working copy created by the notebook.
- `milestone2_1_health.png`: happiness distribution by self-rated health.
- `milestone2_2_marital.png`: happiness distribution by marital status.
- `milestone2_3_income.png`: happiness distribution across seven ordered income bands.
- `milestone2_4_age.png`: age distributions by happiness answer; code 89 represents 89+.
- `milestone2_5_education.png`: happiness percentages by schooling-year ranges.
- `milestone3_dashboard.html`: standalone interactive dashboard with health/happiness, age, and income views; a marital-status dropdown filters all three views.

## Reproduce

From this directory, install the notebook dependencies in your Python environment:

```bash
python -m pip install pandas scipy matplotlib plotly jupyter
```

Open `happiness_analysis.ipynb` in Jupyter and run its code cells from top to bottom. The cleaning cell regenerates `cleaned_dataset.csv`; the static-visualization cell regenerates the five PNGs; the final dashboard cell regenerates `milestone3_dashboard.html`. The HTML dashboard is self-contained and works offline.

## Analysis summary

- Cleaning preserves unanswered values rather than inventing responses. It converts age and completed schooling labels to numeric codes while documenting their top-coded values.
- Descriptive statistics report numeric summaries only where values are meaningful, and counts/percentages for categorical or bracketed responses.
- Two exploratory Pearson chi-square tests compare happiness with self-rated health and marital status. Both show associations in the unweighted sample. The tests do not account for the GSS sample design and do not demonstrate causation.
- Static plots use a colorblind-friendly sequential blue palette for the ordered happiness responses. Their design rationale and accessibility/bias critique are documented in the notebook.
- The interactive dashboard provides a marital-status dropdown and hover/zoom interactions. Peer usability feedback has **not yet been collected**; the notebook records a plan for obtaining and documenting actual feedback.

## Limitations and responsible interpretation

- Happiness, health, income, and education are based on respondent answers; they are not objective clinical or financial measurements.
- `income16` contains family-income brackets, not exact dollar amounts. Its highest category is open-ended, and 423 respondents (10.6%) have no reported income bracket.
- Age `89` means 89 or older; education `20` means 20 or more years. Use caution when a plot treats these codes numerically.
- The 2024 survey is a single-year snapshot. It cannot show changes over time or establish causal effects.
- Static visualizations and ordinary chi-square tests are unweighted and do not include survey-design-adjusted uncertainty. Do not present them as precise national population estimates.
- Grouping categories aids readability but can hide within-group variation. Smaller subgroups have less stable percentages.
- Peer feedback for the dashboard remains outstanding and should be collected before claiming the usability requirement is complete.
