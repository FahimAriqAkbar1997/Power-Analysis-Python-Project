# 📊 Two-Group Power Analysis Tool

A lightweight Python script for comparing two groups using **Cohen's d effect size** and **independent samples t-test power analysis**. Designed for simplicity — just swap in your data and run.

---

## 🔍 What It Does

Given two groups of numerical data, this script will:

- Calculate the **effect size (Cohen's d)** between the two groups
- Determine the **minimum sample size** needed per group to achieve 80% power at α = 0.05
- Generate a **distribution comparison histogram** for visual inspection
- Plot a **power curve** showing how power changes across effect sizes

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python installed along with the following packages:

```bash
pip install statsmodels numpy matplotlib
```

### Usage

1. Open the script
2. Replace the values in `group1` and `group2` with your own data:

```python
group1 = [5, 6, 7, 5, 6, 7, 8, 6, 5, 7]   # ← Replace with your Group 1 values
group2 = [7, 8, 9, 8, 7, 9, 10, 8, 9, 7]  # ← Replace with your Group 2 values
```

3. Run the script:

```bash
python power_analysis.py
```

That's it! The script handles everything else automatically.

---

## 📈 Example Output

Using the default sample data:

```
Effect size (Cohen's d): -1.9365
Sample size needed in each group: 5.34
```

### Distribution Comparison

A histogram comparing the spread and central tendency of both groups, with dashed vertical lines marking each group's mean.

### Power Curve

A curve showing statistical power across a range of effect sizes (0.1–1.5), with reference lines for the 80% power threshold and the observed Cohen's d.

---

## 📐 How It Works

| Step | Description |
|------|-------------|
| **Means & Variances** | Computed using `numpy` with Bessel's correction (`ddof=1`) for unbiased variance |
| **Pooled Std Dev** | Weighted average of both groups' standard deviations |
| **Cohen's d** | Effect size = (μ₁ − μ₂) / pooled std dev |
| **Power Analysis** | Uses `TTestIndPower` from `statsmodels` to solve for required sample size |

**Default parameters:**
- Significance level (α): `0.05`
- Desired power: `0.80`
- Test type: two-sided

---

## 📁 File Structure

```
.
└── power_analysis.py   # Main script — edit group values here
```

---

## 🛠 Customization

You can also adjust the analysis parameters near the top of the script:

```python
alpha = 0.05   # Significance level
power = 0.8    # Desired statistical power
```

The script supports **unequal group sizes** — the ratio is computed automatically from the lengths of `group1` and `group2`.

---

## 📚 Dependencies

- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [statsmodels](https://www.statsmodels.org/)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
