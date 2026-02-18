# Assignment: Learning Probability Density Function using Roll-Number-Parameterized Non-Linear Model

## Objective
To learn the parameters of a probability density function (PDF) from transformed NO₂ air-quality data using a roll-number-based non-linear transformation.

---

## Dataset
- Source: India Air Quality Dataset (Kaggle)
- Feature used: **NO₂ concentration**
- File used in code: `data 2.csv`

---

## Methodology

### Step-1: Non-Linear Transformation

Each NO₂ value \(x\) is transformed into \(z\) using:

\[
z = T_r(x) = x + a_r * sin(b_r x)
\]

Where:

- \( a_r = 0.05 * (r % 7) \)
- \( b_r = 0.3 * ((r % 5) + 1) \)
- \( r \) = University Roll Number

---

### Step-2: Learning PDF Parameters

The transformed variable (z) is modeled using the pdf given in the assignment:



Parameters learned:

- mu: Mean of transformed data  
- lambda: Estimated as \( \frac{1}{2\sigma^2} \)  
- c: Normalization constant \( \sqrt{\frac{\lambda}{\pi}} \)

---

## Implementation Details

Libraries used:

- pandas  
- numpy  


Steps performed:

1. Load dataset using pandas  
2. Extract NO₂ values and remove missing entries  
3. Compute roll-number parameters \(a_r, b_r\)  
4. Transform \(x \rightarrow z\)  
5. Compute:
   - mean (\(\mu\))
   - variance
   - \(\lambda\)
   - normalization constant \(c\)
6. Print final parameters

---

## Output

Estimated parameters:

- **Lambda (λ):** 0.0014605519  
- **Mu (μ):** 25.81144621  
- **c:** 0.02156173  

These values define the learned probability density function for the transformed variable \(z\).

---

