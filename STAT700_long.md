# STAT 700 Full Notes - 30-Page Transcription

> **Purpose:** GitHub/AI-readable reconstruction of the full handwritten-note transcription.  
> **Fidelity:** The substantive note content, original page order, repeated derivations, blanks, annotations, and question marks are preserved. Only Markdown/math formatting and obvious transcription-label artifacts were cleaned.  
> **Math rendering:** Equations use GitHub-compatible LaTeX delimiters (`$...$` and `$$...$$`).

Below is a faithful, cleaned transcription of all 30 pages in the original order. I have **not filled in blanks, corrected equations, removed repetitions, or silently fixed inconsistencies**. I also preserved handwritten annotations such as “unbiased,” question marks, and color notes. For readability, I use **bold symbols for vectors that were marked with an under-tilde in the handwriting**.

## Pages 1–11: Least Squares, Fitted Values, Residuals, and $t$-Statistics

### Page 1 — January 27, 2014

#### LS

$$
\mathbf Y=X\boldsymbol\beta+\boldsymbol\epsilon,
\qquad
E(\boldsymbol\epsilon)=\mathbf 0,
\qquad
\operatorname{Var}(\boldsymbol\epsilon)=I\sigma^2
$$

**① Find $\boldsymbol\beta$ that min.**

$$
RSS(\boldsymbol\beta)
=
(\mathbf Y-X\boldsymbol\beta)
(\mathbf Y-X\boldsymbol\beta)'
$$

**② Find soln of L-S normal eqns:**

$$
X'X\boldsymbol\beta=X'\mathbf Y
$$

**③ Soln is**

$$
\hat{\boldsymbol\beta}
=
(X'X)^{-1}X'\mathbf Y
$$

if $X'X$ has an inverse!

---

### Page 2 — January 27, 2014

**[Purple annotation:]**

$$
\text{l.c.}=\text{linear combination}
$$

#### ④ Fitted values

$$
\hat{\mathbf Y}=X\hat{\boldsymbol\beta}
$$

Would to express $\hat{\mathbf Y}$ as a l.c. of $\mathbf Y$

$$
\hat{\mathbf Y}
=
X\left[(X'X)^{-1}X'\mathbf Y\right]
$$

$$
=
\left[X(X'X)^{-1}X'\right]\mathbf Y
$$

$$
=P\mathbf Y
$$

$P$ is a projection matrix, i.e.

$$
P\text{ is symmetric: }P'=P
$$

$$
P\text{ is idempotent: }PP=P
$$

---

### Page 3 — January 27, 2014

#### ⑤ Residual Vector

$$
\mathbf e
=
\mathbf Y-\hat{\mathbf Y}
=
\mathbf Y-P\mathbf Y
=
(I-P)\mathbf Y
$$

$$
\hat{\mathbf Y}+\mathbf e
=
P\mathbf Y+(I-P)\mathbf Y
=
(P+I-P)\mathbf Y
=
\mathbf Y
$$

$$
(\mathbf Y\text{ is partitioned into 2 parts})
$$

---

### Page 4 — January 27, 2014

$$
\mathbf Y=X\boldsymbol\beta+\boldsymbol\epsilon,
\qquad
E(\boldsymbol\epsilon)=\mathbf 0,
\qquad
\operatorname{Var}(\boldsymbol\epsilon)=I\sigma^2
$$

$$
\left(
\text{when }\boldsymbol\epsilon\sim N(\mathbf 0,I\sigma^2)
\right)
$$

$$
E(\mathbf Y)=X\boldsymbol\beta
$$

$$
\operatorname{Var}(\mathbf Y)=I\sigma^2
$$

When $\boldsymbol\epsilon$ is normally dist., $\mathbf Y$ is also multivariate normal  
(proof in HW)

$$
\mathbf Y\sim N(X\boldsymbol\beta,\sigma^2I)
$$

---

### Page 5 — January 27, 2014

#### ⑥

$$
\hat{\boldsymbol\beta}
=
\underbrace{\left[(X'X)^{-1}X'\right]}_{\text{purple: }A}\mathbf Y
$$

$$
E(\hat{\boldsymbol\beta})
=
\left[(X'X)^{-1}X'\right]E(\mathbf Y)
$$

$$
=
\left[(X'X)^{-1}X'\right]X\boldsymbol\beta
$$

$$
=\boldsymbol\beta
$$

**[Purple annotation:] unbiased**

For the variance, the first matrix is labeled $A$ and the transposed one is labeled $A'$:

$$
\operatorname{Var}(\hat{\boldsymbol\beta})
=
\left[(X'X)^{-1}X'\right]
\operatorname{Var}(\mathbf Y)
\left[(X'X)^{-1}X'\right]'
$$

$$
=
\left[(X'X)^{-1}X'\right]
I\sigma^2
\left[(X'X)^{-1}X'\right]'
$$

$$
=
(X'X)^{-1}X'X(X'X)^{-1}\sigma^2
$$

$$
=
(X'X)^{-1}\sigma^2
$$

---

### Page 6 — January 27, 2014

#### ⑦

$$
\hat{\mathbf Y}=P\mathbf Y
$$

**[Purple $A$ written above $P$]**

$$
E(\hat{\mathbf Y})=?
$$

$$
PX=?
$$

$$
=
\underbrace{\left[X(X'X)^{-1}X'\right]}_{\text{purple: }P}X
=
X
$$

Therefore,

$$
E(\hat{\mathbf Y})
=
E(P\mathbf Y)
=
PE(\mathbf Y)
=
PX\boldsymbol\beta
=
X\boldsymbol\beta
$$

$$
\operatorname{Var}(\hat{\mathbf Y})
=
P\operatorname{Var}(\mathbf Y)P'
=
PP'\sigma^2
=
P\sigma^2
$$

Also,

$$
\hat{\mathbf Y}=X\hat{\boldsymbol\beta}
$$

with the parenthetical derivation

$$
\left(
\operatorname{Var}(\hat{\mathbf Y})
=
X[\operatorname{Var}(\hat{\boldsymbol\beta})]X'
\right.
$$

$$
\left.
=
X(X'X)^{-1}X'\sigma^2
=
P\sigma^2
\right)
$$

---

### Page 7 — January 27, 2014

When

$$
\boldsymbol\epsilon\sim N(\mathbf 0,I\sigma^2)
$$

then

$$
\hat{\mathbf Y}
\sim
N(X\boldsymbol\beta,P\sigma^2)
$$

What about $\mathbf e$?

$$
\mathbf e=(I-P)\mathbf Y
$$

$$
E(\mathbf e)
=
(I-P)E(\mathbf Y)
=
(I-P)X\boldsymbol\beta
$$

$$
=
(X-PX)\boldsymbol\beta
$$

$$
=
(X-X)\boldsymbol\beta
$$

$$
=\mathbf 0
$$

---

### Page 8 — January 27, 2014

$$
\operatorname{Var}(\mathbf e)=?
$$

$$
(I-P)\text{ is symmetric \& idempotent}
$$

$$
(I-P)(I-P)=(I-P)
$$

$$
\operatorname{Var}(\mathbf e)
=
(I-P)\sigma^2
$$

If $\mathbf e$ are normally dist., then

$$
\mathbf e
\sim
N\left(\mathbf 0,(I-P)\sigma^2\right)
$$

---

### Page 9 — January 27, 2014

$$
T=\frac{Z}{\sqrt{U/\nu}}
$$

**Def:** If

$$
Z\sim N(0,1)
$$

and

$$
U\sim\chi_\nu^2
$$

and $Z$ & $U$ are indep,

$$
T=\frac{Z}{\sqrt{U/\nu}}
$$

has a $t$ dist w/ $\nu$ degrees of freedom.

$$
T\sim t_\nu
$$

---

### Page 10 — January 27, 2014

Back to $\hat{\boldsymbol\beta}$:

$$
\frac{\hat{\boldsymbol\beta}-\boldsymbol\beta}
{\sqrt{(X'X)^{-1}\sigma^2}}
$$

Need a

$$
\chi_\nu^2
$$

Back to $\mathbf e$:

$$
\mathbf e
\sim
N\left(\mathbf 0,(I-P)\sigma^2\right)
$$

Therefore,

$$
\left(\frac{1}{\sigma}\right)\mathbf e
\sim
N(\mathbf 0,I-P)
$$

---

### Page 11 — January 27, 2014

$$
\frac{1}{\sigma^2}(\mathbf e'\mathbf e)
\sim
\chi^2_{n-p'}
$$

Then the handwritten ratio is

$$
\frac{
\dfrac{\hat{\boldsymbol\beta}-\boldsymbol\beta}
{\sqrt{(X'X)^{-1}\sigma^2}}
}{
\sqrt{
(\mathbf e'\mathbf e)
\frac{1}{\sigma^2}
\frac{1}{n-p'}
}
}
$$

with the denominator quantity associated with the handwritten label $S^2$, giving

$$
=
\frac{
\hat{\boldsymbol\beta}-\boldsymbol\beta
}{
S\sqrt{(X'X)^{-1}}
}
$$

and

$$
\sim t_{n-p'}
$$


## Pages 12–16: Quadratic Forms and ANOVA Decomposition

### Page 12

#### Quadratic Forms

- Sum of squares are QF

#### Facts

**1.** Any Sum of Squares can be written

$$
\mathbf Y'A\mathbf Y
$$

$A$ is a square symmetric nonnegative definite matrix.

**2.** The d.f. associated w/ any QF is equal to the rank of the defining matrix, which equals its trace when the matrix is idempotent.

**3.** 2 QF are orthogonal if the product of their defining matrices is the null matrix $0$.

---

### Page 13

At the top:

$$
\begin{cases}
\mathbf Y=X\boldsymbol\beta+\boldsymbol\epsilon,
& \text{where }\boldsymbol\beta_{p'\times1}\\[4pt]
\mathbf e=\mathbf Y-\hat{\mathbf Y}
\end{cases}
$$

#### ANOVA - Analysis of Variance

$$
\mathbf Y'\mathbf Y
=
\sum_{i=1}^{n}Y_i^2
=
\text{total sum of squares}
$$

QF:

$$
\mathbf Y'\mathbf Y
=
\mathbf Y'I\mathbf Y
$$

Goal:

$$
\mathbf Y'\mathbf Y
=
SS_\mu+SS_{\text{Reg}}+SS_{\text{Res}}
$$

$$
(3\text{ orthog components})
$$

Under $\mathbf Y'\mathbf Y$, the note says:

$$
SS_{\text{total}}\text{ uncor.}
$$

Degrees of freedom:

$$
n
=
1+(p'-1)+n-p'
\qquad
(df)
$$

with a note under $p'-1$:

$$
p
$$

---

### Page 14

$$
\mathbf Y'\mathbf Y
=
(\hat{\mathbf Y}+\mathbf e)'
(\hat{\mathbf Y}+\mathbf e)
$$

$$
=
\hat{\mathbf Y}'\hat{\mathbf Y}
+
\hat{\mathbf Y}'\mathbf e
+
\mathbf e'\hat{\mathbf Y}
+
\mathbf e'\mathbf e
$$

Substitute

$$
\hat{\mathbf Y}=P\mathbf Y
\qquad\&\qquad
\mathbf e=(I-P)\mathbf Y
$$

gives

$$
\mathbf Y'\mathbf Y
=
(P\mathbf Y)'(P\mathbf Y)
+
(P\mathbf Y)'[(I-P)\mathbf Y]
$$

$$
+
[(I-P)\mathbf Y]'(P\mathbf Y)
+
[(I-P)\mathbf Y]'[(I-P)\mathbf Y]
$$

$$
=
\mathbf Y'P'P\mathbf Y
+
\mathbf Y'P'(I-P)\mathbf Y
$$

$$
+
\mathbf Y'(I-P)'P\mathbf Y
+
\mathbf Y'(I-P)'(I-P)\mathbf Y
$$

**[There is a small handwritten mark/asterisk at the end of the last term.]**

2 middle terms $=0$ since

$$
P'(I-P)=P-P=0
$$

Therefore,

$$
\mathbf Y'\mathbf Y
=
\mathbf Y'P\mathbf Y
+
\mathbf Y'(I-P)\mathbf Y
$$

$$
SS_{\text{Total}}\;(\text{uncorrected})
=
\text{sum of 2 QF}
=
SS_{\text{Model}}+SS_{\text{Res}}
$$

Degrees of freedom written underneath:

$$
SS_{\text{Total}}:\quad n
$$

$$
SS_{\text{Model}}:\quad
\operatorname{rank}(P)=p'
$$

with

$$
p'=p+1
$$

$$
SS_{\text{Res}}:\quad n-p'
$$

Usually interested in explaining variation of $\mathbf Y$ about its mean rather than $\underline{0}$.

---

### Page 15

$$
SS_{\text{model}}
\quad
\text{when indep variables included}
$$

$$
SS_{\text{model}}
\quad
\text{when no indep. variables included}
\quad
(\text{only 1 param})
$$

- only 1 param, overall mean $\mu$ or $\beta_0$
- call $SS_\mu$ & is the correction factor

Consider model w/ $\mu$ is only parameter:

$$
(\beta_0)
$$

$$
\mathbf Y=X\boldsymbol\beta+\boldsymbol\epsilon
$$

$X$ is a col vector of 1's &

$$
\boldsymbol\beta=\mu,
$$

a single elt.

$$
\hat{\boldsymbol\beta}
=
(\mathbf 1'\mathbf 1)^{-1}\mathbf 1'\mathbf Y
=
\frac1n\mathbf 1'\mathbf Y
=
\bar Y
$$

$$
SS_\mu
=
\hat{\boldsymbol\beta}'(X'\mathbf Y)
$$

$$
=
\hat{\boldsymbol\beta}'(\mathbf 1'\mathbf Y)
=
\frac1n
(\mathbf 1'\mathbf Y)'
(\mathbf 1'\mathbf Y)
$$

$$
=
\mathbf Y'
\left(
\frac1n\mathbf 1\mathbf 1'
\right)
\mathbf Y
$$

Also,

$$
\frac1n\mathbf 1\mathbf 1'
=
\frac1n
\begin{bmatrix}
1 & \cdots & 1\\
\vdots & & \vdots\\
1 & \cdots & 1
\end{bmatrix}_{n\times n}
=
\frac1nJ
$$

---

### Page 16

$$
\operatorname{rank}\left(\frac1nJ\right)
=
\operatorname{trace}\left(\frac1nJ\right)
=
1
$$

Therefore, correction factor has d.f. $=1$.

$$
SS_{\text{Reg}}
=
SS_{\text{Model}}-SS_\mu
$$

$$
=
\mathbf Y'P\mathbf Y
-
\mathbf Y'
\left(\frac1nJ\right)
\mathbf Y
$$

$$
=
\mathbf Y'
\left(
P-\frac1nJ
\right)
\mathbf Y
$$

Handwritten note:

> defining matrix $\frac1nJ$ is orthogonal to  
> $$
> \left(P-\frac Jn\right)
> \quad\&\quad
> (I-P)
> $$

Usually reported by ANOVA:

$$
\begin{cases}
SS_{\text{total corrected}}
=
SS_{\text{total uncorrected}}
-
SS_\mu\\[4pt]
SS_{\text{Reg}}\\[4pt]
SS_{\text{Res}}
\end{cases}
$$


## Pages 17–18: Estimating $\sigma^2$

### Page 17 — `feb2lecture.pdf`, February 03, 2014

For CI's & testing $\boldsymbol\beta$, we need an estimator for $\sigma^2$.

TRSS is

$$
\mathbf e'\mathbf e
$$

$$
\sum_{i=1}^{n}(Y_i-\hat Y_i)^2
=
\mathbf e'\mathbf e
=
\mathbf Y'(I-P)'(I-P)\mathbf Y
$$

$$
=
\mathbf Y'(I-P)\mathbf Y
$$

$$
E\left[
\mathbf Y'(I-P)\mathbf Y
\right]
=
[E(\mathbf Y)]'(I-P)[E(\mathbf Y)]
+
\sigma^2\operatorname{trace}(I-P)
$$

Know

$$
E(\mathbf Y)=X\boldsymbol\beta
$$

$$
(I-P)E(\mathbf Y)=0
$$

**[Red brace under the first expectation term, labeled $0$.]**

---

### Page 18 — `feb2lecture.pdf`, February 03, 2014

$$
\operatorname{trace}(I-P)=?
$$

$$
=
\operatorname{trace}(I_n)
-
\operatorname{trace}(P)
$$

$$
=
n-p'
$$

Also,

$$
\operatorname{trace}(P)
=
\operatorname{trace}
\left[
X(X'X)^{-1}X'
\right]
$$

$$
=
\operatorname{trace}
\left[
(X'X)(X'X)^{-1}
\right]
$$

A side note gives the cyclic form

$$
\left(
\operatorname{trace}
\left[
(X'X)^{-1}(X'X)
\right]
\right)
$$

Then,

$$
=
\operatorname{trace}(I_{p'})
$$

$$
=p'
$$

Therefore,

$$
E\left[
\mathbf Y'(I-P)\mathbf Y
\right]
=
0+\sigma^2(n-p')
$$

Therefore:

$$
\text{An unbiased estimator of }\sigma^2\text{ is }\underline{\hspace{2cm}}
$$

**The blank is left blank in the notes.**


## Pages 19–25: One-Way ANOVA and Identifiability

### Page 19 — `feb10lecture.pdf`, February 10, 2014

#### ANOVA - Analysis Of Variance

- predictors - called factors, which have some number of levels
- regression parameters - often called effects

Consider: models where parameters are **fixed** but unknown - called fixed effects.

#### One-way ANOVA w/ fixed effects (Classical Effects Model)

$$
Y_{ij}
=
\mu+\alpha_i+\epsilon_{ij},
$$

$$
i=1,\ldots,t
$$

$$
j=1,\ldots,r
$$

To the right:

**Model**

$$
(\text{each level is a “treatment”})
$$

At the bottom:

$$
t\text{ is \# of levels}
$$

$$
r\text{ is \# of responses at }i^{th}\text{ level }(r_i)
$$

---

### Page 20

$$
Y_{11}
=
\mu+\alpha_1+\epsilon_{11}
$$

$$
Y_{12}
=
\mu+\alpha_1+\epsilon_{12}
$$

$$
\vdots
$$

$$
Y_{1r}
=
\mu+\alpha_1+\epsilon_{1r}
$$

$$
Y_{21}
=
\mu+\alpha_2+\epsilon_{21}
$$

$$
\vdots
$$

$$
Y_{2r}
=
\mu+\alpha_2+\epsilon_{2r}
$$

$$
\vdots
$$

$$
Y_{tr}
=
\mu+\alpha_t+\epsilon_{tr}
$$

---

### Page 21 — `feb10lecture.pdf`, February 10, 2014

The same expansion is written again:

$$
Y_{11}
=
\mu+\alpha_1+\epsilon_{11}
$$

$$
Y_{12}
=
\mu+\alpha_1+\epsilon_{12}
$$

$$
\vdots
$$

$$
Y_{1r}
=
\mu+\alpha_1+\epsilon_{1r}
$$

$$
Y_{21}
=
\mu+\alpha_2+\epsilon_{21}
$$

$$
\vdots
$$

$$
Y_{2r}
=
\mu+\alpha_2+\epsilon_{2r}
$$

$$
\vdots
$$

$$
Y_{tr}
=
\mu+\alpha_t+\epsilon_{tr}
$$

---

### Page 22 — `feb10lecture.pdf`, February 10, 2014

$$
\mathbf Y=X\boldsymbol\beta+\boldsymbol\epsilon
$$

Dimension written under $\mathbf Y$:

$$
\left(\sum_{i=1}^{t}n_i\right)\times1
$$

$$
\boldsymbol\beta
=
\begin{bmatrix}
\mu\\
\alpha_1\\
\vdots\\
\alpha_t
\end{bmatrix}
$$

Assume

$$
E(\epsilon_{ij})=0
$$

Therefore,

$$
E(Y_{ij})
=
\mu+\alpha_i
$$

Can not estimate both $\mu$ & $\alpha_i$ separately,

problem w/ identifiability.

---

### Page 23 — `feb10lecture.pdf`, February 10, 2014

$$
\mu_i=\mu+\alpha_i:
$$

have 2 components, but don't know

> “how much of each we see”

$$
*\quad
\text{Common to add restriction }
\sum_{i=1}^{t}\alpha_i=0
$$

If think of

$$
\mu
=
\frac1t
\sum_{i=1}^{t}\mu_i
$$

with the note:

$$
(\text{mean of indiv. treatment means})
$$

then

$$
\Rightarrow
\mu
=
\frac1t
\sum_{i=1}^{t}
(\mu+\alpha_i)
=
\mu+
\frac1t
\sum_{i=1}^{t}\alpha_i
$$

Therefore,

$$
\sum_{i=1}^{t}\alpha_i=0
$$

Therefore interpretation of $\alpha_i$ as “deviation” from overall mean.

---

### Page 24 — `feb10lecture.pdf`, February 10, 2014

#### 2 Models

#### Classical Effects Model

$$
Y_{ij}
=
\mu+\alpha_i+\epsilon_{ij}
$$

Let

$$
\mu_i=\mu+\alpha_i,
$$

then have

#### Means Model

$$
Y_{ij}
=
\mu_i+\epsilon_{ij}
$$

#### CEM

$$
H_0:
\alpha_1=\alpha_2=\cdots=\alpha_t=0
$$

vs.

$$
H_A:
\text{at least one }\alpha_i\neq0
$$

#### MM

$$
H_0:
\mu_1=\mu_2=\cdots=\mu_t=C
$$

vs.

$$
H_A:
\text{at least one }\mu_i\neq C
$$

**[The $C$ in the alternative hypothesis is circled/highlighted in pink.]**

---

### Page 25 — `feb10lecture.pdf`, February 10, 2014

Example:

$$
t=4
\qquad
4\text{ treatments}
$$

$$
r=2
\qquad
2\text{ replicates}
$$

#### CEM

$$
\mathbf Y
=
\begin{bmatrix}
Y_{11}\\
Y_{12}\\
Y_{21}\\
Y_{22}\\
Y_{31}\\
Y_{32}\\
Y_{41}\\
Y_{42}
\end{bmatrix}
\qquad
8\times1
$$

$$
X
=
\begin{bmatrix}
1&1&0&0&0\\
1&1&0&0&0\\
1&0&1&0&0\\
1&0&1&0&0\\
1&0&0&1&0\\
1&0&0&1&0\\
1&0&0&0&1\\
1&0&0&0&1
\end{bmatrix}
\qquad
8\times5
$$

$$
\boldsymbol\beta
=
\begin{bmatrix}
\mu\\
\alpha_1\\
\alpha_2\\
\alpha_3\\
\alpha_4
\end{bmatrix}
\qquad
5\times1
$$

At the bottom:

$$
(X'X)^{-1}=???
$$

**[The three question marks are written in different colors, including pink and green.]**


## Page 26: Two-Way ANOVA

### Page 26 — `feb17lecture.pdf`, February 17, 2014

#### Two-way ANOVA

$$
Y_{ijk}
=
\mu+\alpha_i+\beta_j+\gamma_{ij}+\epsilon_{ijk}
$$

$k^{th}$ obs. in cell $ij$

Assume

$$
\epsilon_{ijk}
\text{ are indep. }
N(0,\sigma^2)\text{ RVs}
$$

$$
E(\epsilon_{ijk})=0,
\qquad
\operatorname{Var}(\epsilon_{ijk})=\sigma^2
$$

Therefore,

$$
E(Y_{ijk})
=
\mu+\alpha_i+\beta_j+\gamma_{ij}
$$

#### Constraints

$$
\sum_{i=1}^{r}\alpha_i=0
$$

$$
\sum_{j=1}^{c}\beta_j=0
$$

and

$$
\sum_{i=1}^{r}\gamma_{ij}
=
\sum_{j=1}^{c}\gamma_{ij}
=
0
$$


## Page 27: Tests in Two-Way ANOVA

### Page 27 — `feb19lecture.pdf`, February 19, 2014

$$
Y_{ijk}
=
\mu+\alpha_i+\beta_j+\gamma_{ij}+\epsilon_{ijk}
$$

$$
(\epsilon_{ijk}\text{ iid }N(0,\sigma^2)\text{ RVs})
$$

Operator:

$$
\text{Operator}_i=\alpha_i,
\qquad
i=1,\ldots,3
$$

Resin:

$$
\text{Resin}_j=\beta_j,
\qquad
j=1,\ldots,8
$$

$$
k=1,2
$$

#### Test for interaction effect

$$
H_0:
\gamma_{ij}=0
\text{ for all }i\text{ and }j
$$

vs.

$$
H_A:
\text{the }\gamma_{ij}\text{ are not all }0
$$

#### Test for operator effect

$$
H_0:
\alpha_i=0
\text{ for all }i
\quad
(i=1,\ldots,3)
$$

vs.

$$
H_A:
\text{the }\alpha_i\text{ are not all }0
\quad
(i=1,\ldots,3)
$$

#### Test for resin effect

$$
H_0:
\beta_j=0
\text{ for all }j
\quad
(j=1,\ldots,8)
$$

vs.

$$
H_A:
\text{the }\beta_j\text{ are not all }0
\quad
(j=1,\ldots,8)
$$


## Pages 28–29: Linear Mixed Models

### Page 28

#### Book: 2.3.3 Matrix Specification (LMM)

$$
\mathbf Y
=
X\boldsymbol\beta
+
Z\mathbf u
+
\boldsymbol\epsilon
$$

The handwritten braces identify

$$
X\boldsymbol\beta
\quad\text{as “fixed”}
$$

and

$$
Z\mathbf u+\boldsymbol\epsilon
\quad\text{as “random”}.
$$

$$
\mathbf u\sim N(\mathbf 0,D)
$$

$$
\boldsymbol\epsilon\sim N(\mathbf 0,R)
$$

#### Linear Mixed Models (LMM)

$$
E(\mathbf Y)
=
X\boldsymbol\beta
$$

The conditional expectation is written as

$$
E(\mathbf Y\mid \mathbf u=\mathbf u)
=
X\boldsymbol\beta+Z\mathbf u
$$

$$
E(\mathbf u)=\mathbf 0
\qquad;\qquad
\operatorname{Var}(\mathbf u)=D
$$

$$
\operatorname{Var}(\mathbf Y)=?
$$

$$
=
ZDZ'+R
=
V
=
V(\theta)
$$

$$
\mathbf Y
\sim
N(X\boldsymbol\beta,V)
$$

---

### Page 29

$$
\mathbf Y
=
X\boldsymbol\beta
+
Z\mathbf u
+
\boldsymbol\epsilon
$$

$$
\operatorname{Var}(\mathbf Y)
=
E\left[
(\mathbf Y-E(\mathbf Y))
(\mathbf Y-E(\mathbf Y))'
\right]
$$

$$
=
E\left[
(Z\mathbf u+\boldsymbol\epsilon)
(Z\mathbf u+\boldsymbol\epsilon)'
\right]
$$

Know:

$$
(Z\mathbf u)'
=
\mathbf u'Z'
$$

Expanding:

$$
=
Z\,E(\mathbf u\mathbf u')\,Z'
+
Z\,E(\mathbf u\boldsymbol\epsilon')
$$

$$
+
E(\boldsymbol\epsilon\mathbf u')\,Z'
+
E(\boldsymbol\epsilon\boldsymbol\epsilon')
$$

Know:

$$
E(\mathbf u\mathbf u')=D,
\qquad
E(\boldsymbol\epsilon\boldsymbol\epsilon')=R
$$

$$
\operatorname{Cov}(\mathbf u,\boldsymbol\epsilon)=\mathbf 0,
\qquad
E(\boldsymbol\epsilon\mathbf u')=\mathbf 0
$$

Therefore,

$$
\operatorname{Var}(\mathbf Y)
=
\operatorname{Cov}(\mathbf Y)
=
ZDZ'+R
$$

## Page 30: MLE for the Linear Model

### Page 30

#### MLE for LM

$$
\mathbf Y
=
X\boldsymbol\beta+\boldsymbol\epsilon,
\qquad
\boldsymbol\epsilon
\sim
N(\mathbf 0,\sigma^2I_n)
$$

$$
\mathbf Y
\sim
N(X\boldsymbol\beta,\sigma^2I_n)
$$

#### ①

$$
L(\boldsymbol\beta,\sigma^2\mid\mathbf y)=
$$

**[left blank]**

#### ②

$$
\log L
=
\ell(\boldsymbol\beta,\sigma^2)
=
$$

**[left blank]**

#### ③ Expand the quadratic form

$$
RSS(\boldsymbol\beta)
=
(\mathbf y-X\boldsymbol\beta)'
(\mathbf y-X\boldsymbol\beta)
$$

#### ④

Max. over $\boldsymbol\beta$

#### ⑤

Max over $\sigma^2$
