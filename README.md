Core Steps and Methods Used

Data Loading & Inspection: Standard Python libraries (pandas, numpy, matplotlib, seaborn) are used to load and explore the TMDB 5000 Movies dataset. Initial exploration includes examining shape, .head(), .info(), .describe(), and null value counts to understand the data structure and detect missing or invalid values.

Cleaning & Preparation: The dataset is cleaned by:

Filling missing runtimes with the median.

Dropping records with missing or zero budget or revenue.

Ensuring numeric columns are correctly typed.

Adding a new profit column as revenue - budget for business analysis.

Feature Parsing: Complex fields such as genres (stored as JSON-like strings) are parsed so each genre appears as its own row, enabling accurate genre-based analyses.

Data Filtering: Rows with zero or non-informative values for critical business metrics are dropped, ensuring analyses (e.g., profit calculations) are meaningful.

Visualizations and Analytical Outputs
Distribution Visualizations
Budget, Revenue, Runtime Histograms: Most films have smaller budgets and revenues, indicating a highly skewed distribution with a long tail for blockbusters. Runtimes cluster around 100 minutes.

Top Genre Analysis
Top 10 Movie Genres Barplot: After extracting and exploding the genres JSON, the most common genres are visualized as a horizontal bar chart. Leading genres are Action, Drama, and Comedy.

Budget vs. Revenue/Profit
Scatterplot: Budget vs Revenue colored by Profit: This scatterplot reveals that while higher budgets often bring higher revenues, there is substantial variance; not all big-budget films are highly profitable. Profitability (color scale) shows some high-budget films incurring losses and some small/mid-budget films being highly profitable.

Data Quality & Missing Value Handling
Columns like homepage and tagline have substantial missing data, but all core numerical and categorical columns for EDA (budget, revenue, runtime, genre, language, production companies, etc.) are largely intact after cleaning.

Key Takeaways for Business/Analytics
Data Insights
Skewed Distributions: Distributions of budget, revenue, and profit are right-skewed; median values are far lower than the max, indicating a handful of outliers (blockbusters).

Most Popular Genres: Action, Drama, and Comedy are most represented, reflecting industry bias and possibly audience preferences.

Budget-Revenue Dynamics: Correlation exists but is not linear. Outliers show budget alone is not a guarantee of commercial success.

EDA Best Practices Applied
Consistent Data Cleaning: Ensures numeric stability and analytic accuracy by imputing/filling or removing problematic entries and ensuring all computations use valid values.

Feature Engineering: Addition of profit as a crucial metric for deeper business insights, moving beyond just revenue reporting.
