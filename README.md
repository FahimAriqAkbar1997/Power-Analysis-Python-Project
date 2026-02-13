How It Works
StepDescriptionMeans & VariancesComputed using numpy with Bessel's correction (ddof=1) for unbiased variancePooled Std DevWeighted average of both groups' standard deviationsCohen's dEffect size = (μ₁ − μ₂) / pooled std devPower AnalysisUses TTestIndPower from statsmodels to solve for required sample size
Default parameters:

Significance level (α): 0.05
Desired power: 0.80
Test type: two-sided


File Structure
.
└── power_analysis.py   # Main script — edit group values here

Customization
You can also adjust the analysis parameters near the top of the script:
pythonalpha = 0.05   # Significance level
power = 0.8    # Desired statistical power
The script supports unequal group sizes — the ratio is computed automatically from the lengths of group1 and group2.
Note: The numbers used for group1 and group2 are for demonstration purposes of the built in visualizations.

Dependencies

NumPy
Matplotlib
statsmodels


License
This project is open source and available under the MIT License.
