# What Makes Countries Happy? Global Happiness and Development Indicators

## Authors

- [Luan Nguyen](https://github.com/Luan-N) — Author #1 (solo project)

## Project Description

This project analyzes World Happiness Report scores alongside World Bank indicators to find which factors are linked to national happiness. The data covers many countries and includes variables such as GDP per capita, life expectancy, social support, and freedom.

After cleaning the data, I will use correlation, regression, and ANOVA to examine which factors are most strongly associated with happiness and whether happiness differs by region. The results will be presented through static charts and an interactive dashboard. The project will also discuss bias, missing data, and the limits of drawing causal conclusions from observational data.

## Project Outline and Plan

- **Milestone 0:** Choose a dataset and audit its quality
- **Milestone 1:** Clean the data and run statistical analyses
- **Milestone 2:** Build five or more static visualizations
- **Milestone 3:** Build an interactive dashboard
- **Final:** Write the final report and prepare the presentation
- **Optional:** Build a machine-learning regression model to predict happiness scores

## Interface Plan

The project will include an interactive Plotly dashboard. Users will be able to filter the data by region and year and hover over charts to see additional country-level details.

## Data Collection and Storage Plan

This section was written by Author #1.

World Happiness Report data, along with World Bank indicators when needed, will be downloaded as CSV files.

- Raw files will be stored in `data/raw/`.
- Cleaned datasets will be stored in `data/cleaned/`.

## Data Analysis and Visualization Plan

Because this is a solo project, Author #1 is also responsible for this section.

Python will be used for data cleaning and statistical analysis:

- `pandas` for loading, cleaning, and transforming data
- `scipy` for statistical tests
- `matplotlib` and `seaborn` for static charts
- `plotly` for interactive visualizations and the dashboard

Planned visualizations include:

- Happiness score versus GDP per capita
- A correlation heatmap
- Happiness scores by region
- Additional comparisons across years and development indicators

## Repository Structure

```text
.
├── data/
│   ├── raw/
│   └── cleaned/
├── notebooks/
├── src/
├── README.md
├── LICENSE
└── .gitignore
```

## Limitations

The analysis will identify associations, not prove that any particular factor causes happiness. Results may also be affected by survey methodology, differences in data availability between countries and years, missing values, and regional or cultural measurement bias.
