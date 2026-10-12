---
title: "STAT 700 | Exam 1 Supplemental Cheat / Note Sheet"
subtitle: "Least Squares, Projection Geometry, ANOVA Models, LMM, MLE"
format: "GitHub Markdown with LaTeX math"
---

# STAT 700 | Exam 1 Supplemental Cheat / Note Sheet

**Least Squares - Projection Geometry - ANOVA Models - LMM - MLE**

## 1. Least Squares, Projection Matrix, and Residual Inference

| Concept | Key result / note |
|---|---|
| Least-squares objective | $RSS(\beta)=(Y-X\beta)'(Y-X\beta)$. Minimize with respect to $\beta$. |
| Normal equations | $X'X\hat\beta=X'Y$. |
| LS estimator | $\hat\beta=(X'X)^{-1}X'Y$, provided $X$ has full column rank so $X'X$ is invertible. |
| Projection matrix | $P=X(X'X)^{-1}X'$; $P'=P$; $P^2=P$; $PX=X$. |
| Fitted / residual | $\hat Y=PY$; $e=Y-\hat Y=(I-P)Y$; $Y=\hat Y+e$. |
| $\hat\beta$ moments | $E(\hat\beta)=\beta$ (unbiased); $\operatorname{Var}(\hat\beta)=\sigma^2(X'X)^{-1}$. |
| Fitted values | $E(\hat Y)=X\beta$; $\operatorname{Var}(\hat Y)=\sigma^2P$; under normal errors, $\hat Y\sim N(X\beta,\sigma^2P)$. |
| Residuals | $E(e)=0$; $\operatorname{Var}(e)=\sigma^2(I-P)$; under normal errors, $e\sim N(0,\sigma^2(I-P))$. |

### Inference

| Inference | Compact form |
|---|---|
| $t$ construction | If $Z\sim N(0,1)$, $U\sim\chi^2_\nu$, and $Z\perp U$, then $T=Z/\sqrt{U/\nu}\sim t_\nu$. |
| Residual $\chi^2$ | $e'e/\sigma^2\sim\chi^2_{n-p'}$, where $p'$ = number of columns of $X$. |
| Unbiased $\sigma^2$ estimator | $S^2=e'e/(n-p')=RSS(\hat\beta)/(n-p')$. This fills the blank in the notes. |
| Coefficient SE | $SE(\hat\beta_j)=S\sqrt{[(X'X)^{-1}]_{jj}}$. |
| Coefficient $t$ statistic | $T_j=(\hat\beta_j-\beta_j)/SE(\hat\beta_j)\sim t_{n-p'}$. |

## 2. Quadratic Forms and ANOVA Geometry - Material Not Tabulated on Formula Sheet

| Concept | Key result / note |
|---|---|
| Sum-of-squares matrix | For a sum of squares $Y'AY$, the defining matrix $A$ is symmetric and nonnegative definite. |
| QF d.f. | d.f. $=\operatorname{rank}(A)$. If $A$ is idempotent, $\operatorname{rank}(A)=\operatorname{trace}(A)$. |
| Orthogonal QFs | $Y'AY$ and $Y'BY$ are orthogonal when $AB=0$ (for the symmetric defining matrices used here). |
| Fitted/residual geometry | $P(I-P)=0$, so fitted and residual components are orthogonal; equivalently $\hat Y'e=0$. |
| Interpretation | ANOVA typically explains variation of $Y$ about its mean, rather than variation about $0$. |

### ANOVA Defining Matrices

| ANOVA component | Defining matrix / key relation |
|---|---|
| Mean / correction factor | $A_\mu=J/n=(1/n)11'$. |
| Corrected total | $A_T=I-J/n$. |
| Regression | $A_R=P-J/n$. |
| Residual | $A_E=I-P$. |
| Orthogonality | $J/n$, $P-J/n$, and $I-P$ are mutually orthogonal defining matrices when the model contains an intercept. |

## 3. One-Way ANOVA: Fixed Effects, Identifiability, and Parameterizations

| Concept | Key result / note |
|---|---|
| Terminology | Predictors are factors; factor values are levels; regression parameters are effects. Fixed effects are unknown but nonrandom parameters. |
| Classical effects model | $Y_{ij}=\mu+\alpha_i+\varepsilon_{ij}$, $i=1,\ldots,t$; $j=1,\ldots,r_i$. Each level $i$ is a treatment. |
| Treatment mean | $\mu_i=E(Y_{ij})=\mu+\alpha_i$. |
| Identifiability | $\mu$ and all $\alpha_i$ cannot be estimated separately without a constraint: adding $c$ to $\mu$ and subtracting $c$ from every $\alpha_i$ leaves $\mu+\alpha_i$ unchanged. |
| Common constraint | $\sum_{i=1}^{t}\alpha_i=0$. Then $\mu=(1/t)\sum_i\mu_i$ and $\alpha_i$ is the deviation of treatment $i$ from the overall mean. |

### Equivalent Parameterizations and Tests

| Parameterization | Model and test |
|---|---|
| Classical Effects Model (CEM) | $Y_{ij}=\mu+\alpha_i+\varepsilon_{ij}$. **$H_0$:** $\alpha_1=\cdots=\alpha_t=0$. **$H_A$:** at least one $\alpha_i\neq0$. |
| Means Model (MM) | $Y_{ij}=\mu_i+\varepsilon_{ij}$. **$H_0$:** $\mu_1=\cdots=\mu_t$ $(=C)$. **$H_A$:** not all treatment means equal $C$. |
| Equivalence | The two models describe the same treatment means through $\mu_i=\mu+\alpha_i$; the parameterization differs. |

### Worked Setup: $t=4$ Treatments, $r=2$ Replicates

$$
Y=
\begin{bmatrix}
Y_{11}&Y_{12}&Y_{21}&Y_{22}&Y_{31}&Y_{32}&Y_{41}&Y_{42}
\end{bmatrix}'
$$

$$
\beta=
\begin{bmatrix}
\mu&\alpha_1&\alpha_2&\alpha_3&\alpha_4
\end{bmatrix}'
$$

The design matrix is

$$
X=
\begin{bmatrix}
1&1&0&0&0\\
1&1&0&0&0\\
1&0&1&0&0\\
1&0&1&0&0\\
1&0&0&1&0\\
1&0&0&1&0\\
1&0&0&0&1\\
1&0&0&0&1
\end{bmatrix}_{8\times5}.
$$

**$(X'X)^{-1}$?** It does not exist. $X$ is rank-deficient because the intercept column equals the sum of the four treatment-indicator columns. A constraint (such as $\sum\alpha_i=0$) or a reduced-rank parameterization is required.

## 4. Two-Way ANOVA

| Concept | Key result / note |
|---|---|
| Model | $Y_{ijk}=\mu+\alpha_i+\beta_j+\gamma_{ij}+\varepsilon_{ijk}$; $k$ indexes replicate/observation within cell $(i,j)$. |
| Cell mean | $E(Y_{ijk})=\mu+\alpha_i+\beta_j+\gamma_{ij}$. |
| Identifiability constraints | $\sum_i\alpha_i=0$; $\sum_j\beta_j=0$; for each $j$, $\sum_i\gamma_{ij}=0$; for each $i$, $\sum_j\gamma_{ij}=0$. |
| Error assumption | Use the same independent $N(0,\sigma^2)$ error assumption stated on the provided formula sheet. |

### Example Labels and Hypothesis Tests

| Test / example | Statement |
|---|---|
| Example labels | $\mathrm{Operator}_i=\alpha_i$, $i=1,\ldots,3$; $\mathrm{Resin}_j=\beta_j$, $j=1,\ldots,8$; $k=1,2$. |
| Interaction test | **$H_0$:** $\gamma_{ij}=0$ for all $i,j$. **$H_A$:** the $\gamma_{ij}$ are not all $0$. |
| Operator main effect | **$H_0$:** $\alpha_i=0$ for all $i$. **$H_A$:** the $\alpha_i$ are not all $0$. |
| Resin main effect | **$H_0$:** $\beta_j=0$ for all $j$. **$H_A$:** the $\beta_j$ are not all $0$. |

## 5. Linear Mixed Models (LMM)

| Concept | Key result / note |
|---|---|
| Matrix specification | $Y=X\beta+Zu+\varepsilon$. $X\beta$ is fixed; $Zu+\varepsilon$ is random. |
| Random effects / error | $u\sim N(0,D)$; $\varepsilon\sim N(0,R)$; $\operatorname{Cov}(u,\varepsilon)=0$. |
| Marginal mean | $E(Y)=X\beta$. |
| Conditional mean | $E(Y\mid u)=X\beta+Zu$. |
| Random-effect moments | $E(u)=0$; $\operatorname{Var}(u)=D$. |
| Marginal variance | $\operatorname{Var}(Y)=ZDZ'+R=V=V(\theta)$. |
| Marginal distribution | $Y\sim N(X\beta,V)$. |

### Variance Derivation

$$
\operatorname{Var}(Y)=E[(Zu+\varepsilon)(Zu+\varepsilon)']
$$

Expand:

$$
\operatorname{Var}(Y)
=ZE(uu')Z'
+ZE(u\varepsilon')
+E(\varepsilon u')Z'
+E(\varepsilon\varepsilon').
$$

Use

$$
E(uu')=D,
\qquad
E(\varepsilon\varepsilon')=R,
$$

with the cross terms equal to $0$. Therefore,

$$
\boxed{\operatorname{Var}(Y)=ZDZ'+R}.
$$

## 6. MLE for the Normal Linear Model - Completed from the Notes

| Concept | Key result / note |
|---|---|
| Likelihood | $L(\beta,\sigma^2\mid y)=(2\pi\sigma^2)^{-n/2}\exp\{-[(y-X\beta)'(y-X\beta)]/(2\sigma^2)\}$. |
| Log-likelihood | $\ell(\beta,\sigma^2)=-(n/2)\log(2\pi)-(n/2)\log(\sigma^2)-RSS(\beta)/(2\sigma^2)$. |
| Expand RSS | $RSS(\beta)=y'y-2\beta'X'y+\beta'X'X\beta$. |
| Max over $\beta$ | $\partial\ell/\partial\beta=X'(y-X\beta)/\sigma^2=0 \Rightarrow \hat\beta_{\mathrm{MLE}}=(X'X)^{-1}X'y$ (full-rank $X$). |
| Max over $\sigma^2$ | $\hat\sigma^2_{\mathrm{MLE}}=RSS(\hat\beta)/n$. |
| Important contrast | $\hat\sigma^2_{\mathrm{MLE}}$ uses denominator $n$; the unbiased estimator $S^2$ uses $n-p'$. |

> **High-value exam check:** Intercept + every treatment dummy creates exact collinearity. If $X'X$ is singular, do not try to invert it; impose a constraint or change parameterization.
