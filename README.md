Blog Post 8 — Simulation, Bootstrap Confidence Intervals, and Hypothesis Testing

This repository contains Blog Post 8, "Simulate It: Bootstrap CIs and p-Values Without the Black Box" 

Files 

blog8.Rmd — the source file of the blog post. It contains the full text and all R code; rendering it with R Markdown reproduces the complete post and all figures programmatically.

blog8.html — the rendered blog post. It contains the full text, all R code, all figures, and one interactive Plotly visualization. Open it with any web browser .

Contents of the post 

The post uses simulation to explain how statistical inference works:

1. Bootstrap confidence intervals — drawing one sample, repeatedly resampling from it, and plotting the resulting bootstrap distribution; the middle 95% of that distribution forms the 95% confidence interval.
2. Coverage — a repeated-simulation experiment (300 fresh samples) showing that a 95% confidence interval contains the true population parameter about 95% of the time (observed coverage: 0.953).
3. Hypothesis testing — simulating the null distribution of the t-statistic (5,000 draws) to explain rejection regions and p-values, with an observed t of 2.05 versus a critical value of 2.045 and a simulated p-value of 0.047.

An interactive Plotly figure lets the reader switch the sample size (n = 20, 40, 80, 160) and watch the bootstrap distribution and its 95% interval change.

Reproducibility

Requirements: R with the packages dplyr, ggplot2, and plotly.
No external data files are needed — the "population" is itself simulated (a log-normal distribution with 50,000 draws), which is exactly what makes it possible to compare intervals against the true parameter.
All analysis is embedded in the code chunks of blog8.Rmd and executed top to bottom; every random draw is fixed with set.seed() (seeds 2026, 123, 99, 1, and 7), so re-rendering reproduces the same figures and numbers, with results generated programmatically rather than copied by hand.

Key results 

True population mean: 2.224
Bootstrap 95% CI (n = 40): [1.99, 3.06]
Observed coverage over 300 simulations: 0.953 (nominal 0.95)
Rejection region (α = 0.05, t with 29 df): ±2.045
Observed t = 2.05, simulated p-value: 0.047
