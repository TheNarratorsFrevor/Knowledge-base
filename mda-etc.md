# MDA Cheatsheet

A comprehensive, information-dense reference for Mathematics for Data Analysis (MDA).

---

## Descriptive Statistics

- **Population & Sample:**
  - $Population$: Entire set of items/individuals. $Sample$: Subset representing the population.
  - $Statistical~unit$: Element of population; can measure $characters/variables$ (numerical or categorical).
- **Types of Variables:**
  - Numerical: $Discrete$ (finite/countable values) or $Continuous$ (real numbers or intervals).
  - Categorical: Non-numeric (e.g. gender, color); can be $ordinal$ (ordered) or $nominal$ (unordered).

### Frequency & Distributions
- **Absolute frequency**: $f_k = $ count of value $x_k$
- **Relative frequency**: $f_k = \frac{f_k}{N}$
- $\sum_k f_k = N$, $\sum_k \frac{f_k}{N} = 1$
- **Cumulative frequency**: Running total up to class $k$.
- **Histogram**: Graphical display of frequency for continuous/dense data.
- **Pie Chart**: Circular representation for categorical data, angle $g = $ frequency $\div$ total $\times$ $360^\circ$
- **Bar Chart**: Categorical/discrete data, heights/widths $\propto$ frequency; bars not touching.

### Data Grouping
- Group continuous/discrete values into $classes$ (intervals).
- Rules for number of classes:
  - Sturges: $1+\log_2 N$
  - Rice: $2 \sqrt[3]{N}$
  - Freedman-Diaconis: $\text{size}=2\,IQR/\sqrt[3]{N}$

---

## Summary Statistics

### Central Tendency
- **Mean:** $\overline{x} = \frac{1}{N} \sum_{k=1}^N x_k$
- **Weighted mean:** $\overline{x} = \frac{\sum_i w_i x_i}{\sum_i w_i}$
- **Geometric mean:** $G = \left( \prod x_k \right)^{1/N}$
- **Harmonic mean:** $H = \left( \frac{1}{N} \sum_{k=1}^N \frac{1}{x_k} \right)^{-1}$
- **Median:**
  - Odd: $x_{(N+1)/2}$
  - Even: $\frac{x_{N/2} + x_{N/2+1}}{2}$
- **Mode:** Most frequent value(s).

### Position Indices
- **Quantiles (p-quantile):** Value s.t. $p\%$ data $\leq$ q.
- **Quartiles:** $Q_1$ (25%), $Q_2$ (Median), $Q_3$ (75%)
- **Interquartile Range (IQR):** $Q_3 - Q_1$

### Dispersion
- **Variance:** $\sigma^2 = \frac{1}{N} \sum (x_k-\overline{x})^2$
- **Sample variance (unbiased):** $s^2=\frac{1}{N-1} \sum (x_k-\overline{x})^2$
- **Standard deviation:** $\sigma = \sqrt{\sigma^2}$
- **Range:** $\max(x) - \min(x)$
- **Coefficient of variation (CV):** $CV = \frac{\sigma}{\overline{x}}$
- **MAD (Median absolute deviation):** $\text{Median}(|x_i-\text{median}|)$
- **Skewness:** $\frac{1}{N\sigma^3} \sum (x_k-\overline{x})^3$
- **Kurtosis:** $\frac{1}{N\sigma^4} \sum (x_k-\overline{x})^4$

### Standardization
- Standardized value: $z_k=\frac{x_k-\overline{x}}{\sigma}$

---

## Probability Theory
- **Concept:** Probability measures uncertainty of events.
- **Definitions:**
  - Classical: $P(A)=\frac{\text{favorable cases}}{\text{possible cases}}$
  - Frequentist: $P(A)\approx\text{relative frequency (infinite trials)}$
  - Axiomatic (Kolmogorov):
    1. $0 \leq P(A) \leq 1$
    2. $P(\Omega)=1$
    3. If $A_i$ are disjoint, $P(\bigcup_i A_i) = \sum_i P(A_i)$
- **Sample space ($\Omega$):** All possible outcomes.
- **Event ($A\subseteq\Omega$):** Set of outcomes.
- **Union/Intersection/Complement:** $A \cup B$, $A \cap B$, $A^C$

### Important Results
- $P(A^C) = 1 - P(A)$
- $P(\varnothing)=0$
- $P(A\cup B)=P(A)+P(B)-P(A\cap B)$
- **Conditional Probability:** $P(A|B)=\frac{P(A\cap B)}{P(B)}$
- **Independence:** $P(A\cap B)=P(A)P(B)$

### Bayes Theorem
$$P(A|B)=\frac{P(B|A)P(A)}{P(B)}$$

---

## Combinatorics

### Basics
- **Permutations (no repetitions):** $P_{n,k}=\frac{n!}{(n-k)!}$
- **Full permutation:** $P_{n,n}=n!$
- **Combinations (no repetitions):** $C_{n,k} = \binom{n}{k} = \frac{n!}{k!(n-k)!}$
- **Permutations (with repetition):** $n^k$
- **Combinations (with repetition):** $C_{n+k-1,k} = \binom{n+k-1}{k}$

---

## Distances & Similarity

### Metric Axioms ($d(x, y)$)
1. Non-negativity: $d(x,y)\geq 0$
2. Identity: $d(x,y)=0\iff x=y$
3. Symmetry: $d(x,y)=d(y,x)$
4. Triangle inequality: $d(x,y)+d(y,z)\geq d(x,z)$

### Important Distances
- **Euclidean (L2):** $d_2(x,y) = \sqrt{\sum_k (x_k - y_k)^2}$
- **Manhattan (L1):** $d_1(x,y) = \sum_k |x_k - y_k|$
- **Chebyshev:** $\max_k |x_k-y_k|$
- **Mahalanobis:** $d_M(x,y) = \sqrt{(x-y)^T M (x-y)}$
- **Hamming:** Count of differing positions in vectors/strings.
- **Jaccard for sets:** $d_J(A,B)=1-\frac{|A\cap B|}{|A\cup B|}$
- **Cosine similarity:** $1-\frac{x\cdot y}{\|x\|\|y\|}$

---

## Principal Component Analysis (PCA)

- **Purpose:** Reduce dimensionality while retaining variance.
- **Procedure:**
  1. Standardize data:
     - $z_{ij} = \frac{x_{ij} - \mu_j}{\sigma_j}$
  2. Compute covariance matrix $C$.
  3. Find eigenvalues/eigenvectors.
  4. Order components by eigenvalue (variance explained).
  5. Select $q$ PCs: Usually those capturing $>80\%$ variance.
  6. Project data: $\text{FinalDataSet} = \text{StandardizedData} \cdot \text{FeatureVector}$
- **Variance explained per PC:** $\text{Explained ratio for }i = \frac{\lambda_i}{\sum_k\lambda_k}$

---

## Useful Formulas & Properties

- **Sum formulas:** $\sum_{i=1}^n i = \frac{n(n+1)}{2}$
- **Binomial theorem:** $(a+b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k$
- **Properties of means/variances under transformations:**
   - $\text{Mean}(ax+b)=a\,\text{Mean}(x)+b$
   - $\text{Var}(ax+b)=a^2\,\text{Var}(x)$

---

## Common Data Analysis Steps

1. **Define the problem and collect data**
2. **Summarize data (descriptive stats, plots)**
3. **Inferential statistics (e.g., hypothesis testing, confidence intervals)**
4. **Modeling (regression, PCA, clustering)**
5. **Validation and interpretation**

---

