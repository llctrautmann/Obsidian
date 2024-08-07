---
modified: 2024-08-07
---
> [!Tasks]-
> ```tasks
> not done
> path includes {{query.file.path}}
> ```

# 07-08-2024
- #python: `.clear()` to empty lists 

# 03-08-2024
- #todo 

---
# 02-08-2024
- #python Data loaders in Lightning might need to be defined in the global scope and not in the training function. I have run into weird behaviours that are so regular that they look like some major implementation error. 

---

# 01-08-2024
- #python PyTorch has now an implementation of the Gated Linear Unit (GLU)
- #python Initialisation...
	- add 
	- add 

---
# 31-07-2024
- #python [[Relu]] For dead neurons to happen in ReLUs, the output value of a specific neuron of the linear layer before the ReLU has to be negative for all input images.
- #python To have a more accurate conclusion of model performance, we would have to train the models for multiple seeds and look at the averages.

# 30-07-2024
- #python  Lightning allows better training for less time and less error proneness. 

# 27-07-2024
- #AudioProcessing The Nyquist Constraint for audio files says that we can only get clear frequency signals up to half the sample size. 
- #AudioProcessing When we use spectrograms, it is common to normalise the spectrogram to the max frequency value in decibel (centred at 0) and have all other values be negative to better highlight differences. 

# 23-07-2024
- #ProbTheory [[Simpson's Paradox]]: Sometimes data that is looked at in groups shows a different trend when looked at at the whole dataset level
- #Statistics [[Maximum Likelihood Estimation (MLE)]]: MLE is just using a probability distribution to fit for each sample the most likely parameter
	- IID assumption makes this a product and the log makes it a sum
	- [[Bayes Theorem]] also uses [[Likelihood]] functions and priors to find the posterior. 
	- For most functions it is possible to derive a simple loss function by removing all unnecessary terms. All necessary terms form the necessary statistics to avoid losing any information. 
- #Code [[@takamichi2018]]: Using the loss function from a von-mises-distribution to model the phase from the magnitude alone

---

# 18-07-2024
- #Mathematics Sum of consecutive integers from $a$ to $b$
	- $\text{Sum} = \frac{(b - a + 1) \cdot (a + b)}{2}$
- Sum of Sums of Ranges
	- Sum of the sums of the first $n$ ranges of consecutive integers.
- Formula for Sum of First $k$ Integers $S(k)$:
	- $S(k) = \frac{k(k + 1)}{2}$
- Formula for Sum of Sums:
	- $\sum_{k=1}^{n} S(k) = \frac{n(n + 1)(n + 2)}{6}$


# 16-07-2024
- [ ] #todo [[@nugraha2019]] find out how to do the convolutions for uneven lengths.
- 

---

# 10-07-2024
- #python: if I hit recursion depth, it could be useful to address the issue with a self-managed stack
- #python: Vectorization should be used at all times and under all circumstances

---
# 08-07-2024
- #python: `.sort` for tuples the elements of the tuples are being compared in order
	- `{python}events.sort(key=lambda event: (event[0], event[3]))` lambda functions can be used for custom sorting functions
- #python: to check if all items in a list are the same. 
```python
def all_same(items):
    return all(x == items[0] for x in items)
```
---

# 02-07-2024
- #ProbTheory [[@Thomas2018]]: Full summary of the most important concepts in 101 for univariate and multivariate Probability Theory 
- #ProbTheory [[Covariance]] & [[@Thomas2018]]: Linear transformations have related properties
	- $\mathbb{E}\left[\sum_{i=1}^n \alpha_i X_i+\beta\right]=\sum_{i=1}^n \alpha_i \mathbb{E}\left[X_i\right]+\beta$
	- $\operatorname{Cov}[\mathbf{A x}+\boldsymbol{b}]=\mathbf{A} \operatorname{Cov}[\boldsymbol{x}] \mathbf{A}^{\top}$ 

---
# 31-06-2024
#ProbTheory [[Categorical and Multinomial Distributions]]
- **Issue**: Numerical instability with extreme logits.
- **Solution**: Use log-sum-exp trick.
	- Formula: $\log \sum_{c=1}^C \exp(a_c) = m + \log \sum_{c=1}^C \exp(a_c - m)$
	- $m = \max_c a_c$ for stability.
- **Implementation**: $\operatorname{lse}(\boldsymbol{a}) \triangleq \log \sum_{c=1}^C \exp(a_c)$

---

# 29-06-2024
- #ProbTheory #ComputationalGeometry [[Probability as an Extension of Boolean Logic]]: $P(A \cup B) \triangleq  P(A) + P(B) - P(A \cap B)$ is basically the inclusion-exclusion principle. 
	- #LinAlg this is also the same principle for subspace dimensionality
		- $\operatorname{dim}(U+W)=\operatorname{dim} U+\operatorname{dim} W-\operatorname{dim}(U \cap W)$ 

---
# 28-06-2024
- [ ] #todo _Convert the remaining #LinAlg and #ProbTheory cards to Mochi so that you do not forget all the time._
- #LinAlg [[Matrix-Matrix Multiplication]]: When multiplying matrices, the easiest way to get the correct result imo is to use the scaling solution.
	1. Each values in the first column (top to bottom) of the second matrix scales one column of the first matrix
	2. add them to obtain the first column of the resulting matrix
	3. repeat for each additional column

- #ProbTheory [[Random Vectors]]: A **[[Random Vectors|random vector]]** is standard notation for a vector of random variables
- #ProbTheory [[Covariance]]: Covariances have nice properties
	- From the definition follows that: $\mathbb{E}\left[ \mathbf{x}\mathbf{x}^{\top} \right]= \mathbf{\Sigma} +\mathbf{\mu} \mathbf{\mu}^{\top}$ 
	- The covariance of a linear transformation is: $\operatorname{Cov}[\mathbf{A x}+\boldsymbol{b}]=\mathbf{A} \operatorname{Cov}[\boldsymbol{x}] \mathbf{A}^{\top}$
	- The cross-covariance between $\boldsymbol{x}$ and $\boldsymbol{y}$ is defined as: $\operatorname{Cov}[\boldsymbol{x}, \boldsymbol{y}]=\mathbb{E}\left[(\boldsymbol{x}-\mathbb{E}[\boldsymbol{x}])(\boldsymbol{y}-\mathbb{E}[\boldsymbol{y}])^{\top}\right]$ 


---

# 27-06-2024
- #Uncertainty [[Conformal Predictions]] might be a very useful tool for UQ after SR model for structural biomarker determination
- #InformationTheory [[]]
---
# 26-06-2024
- #InformationTheory [[Information Theory]]: The entropy of a probability distribution can be interpreted as a measure of uncertainty, or lack of predictability, associated with a random variable drawn from a given distribution. 
	- Entropy is also used to quantify information content in a data source
		- Assume: $X_{n} \sim p$ 
			- if entropy is high, it is hard to predict the value of each observation $X_{n}$. 
			- vice versa for low entropy; minimum entropy is a delta function that has all its mass in one state


---
# 19-06-2024
- #ProbTheory [[Bernoulli and Binomial Distribution|binomial]]: the binomial can be written as $p(\text{ data }|\text{true probability}=s)= c\cdot s^\text{\# true}\cdot (1-s^\text{\# false})$
	- for this to work we need to assume independence of events


# 17-06-2024
- #LinAlg [[Matrix Calculus]]: The directional derivative is $\nabla$ multiplied by the a normalised directional vector. 

# 16-06-2024
- #ComputationalGeometry Inclusion-Exclusion is inherent exponential and hence for most problems unquestionably not a good idea [^1]. 
	- Basic CS problem
- #ComputationalGeometry Line Sweep has $O(n \cdot log(n))$ time complexity when implemented with a segment tree algorithm
# 15-06-2024
- #LinAlg The full [[Eigenvalue decomposition|EVD]] pipeline has three steps
	- Power method, Rayleigh Coefficient, Deflation
	- The power method finds the first [[Eigenthings|eigenvectors]] which we can then use in the Rayleigh Coefficient to find the corresponding eigenvalue. Eigenvectors are orthonormal, and the eigenvalues are real, we can project out the first eigenvector and then reapply the power method and RL coefficient. 
		- [ ] _Apply the Power Method, Raylight Coefficient and Deflation on a matrix_
- SVD makes it possible to see that for both $\mathbf{A}^{\top}\mathbf{A}$ and $\mathbf{A}\mathbf{A}^{\top}$ the eigenvectors are in the right or left matrix of the SVD and the eigenvalues are the square of the singular values
	- The [[Eigenthings|eigenvalues]] of $\mathbf{A}^{\top}\mathbf{A}$ are always the squares singular values $\mathbf{S}^{\top} \mathbf{S}$ 
	- The [[Eigenthings|eigenvectors]] are the left or right matrix depending on the order (inner or outer product)
# 14-06-2024
- #LinAlg In the case of a Gaussian distribution, we have $\mathbf{A}=\boldsymbol{\Sigma}^{-1}$, **so small values of $\lambda_i$ correspond to directions where the posterior has low precision and hence high variance**.
	- [ ] <mark class="hltr-orange">TODO</mark> *This requires some more pondering and some mathematical examples*
- $\large R(\mathbf{A}, x) \triangleq \frac{x^{\top} \mathbf{A} x}{x^{\top} \boldsymbol{x}}$ is the **Rayleigh quotient**
	- Necessary for the [[Eigenvalue decomposition#Power method]] 
# 13-06-2024
- #LinAlg common way to rewrite the principle formula for [[Eigenthings]] or [[Eigenvalue decomposition|EVD]] is $\large\operatorname{det}(\lambda \mathbf{I}-\mathbf{A})=0$. This makes intuitive sense because we need to squeeze space for $\mathbf{A}$ to result in just scaling. 

# 12-06-2024
- #LinAlg [[Norms in Linear Algebra#Matrix Norms|norm]]: Matrix Norms are geometrically, the amount by which a linear map stretches any unit-norm input.
	- The most important matrix [[Norms in Linear Algebra|norm]] is the $\|\mathbf{A}\|_2$-norm: $\|\mathbf{A}\|_{2}=\sqrt{\lambda_{\max }\left(\mathbf{A}^{\top} \mathbf{A}\right)}=\max _i \sigma_i$ where $\lambda_{max}$ is the largest eigenvalue and $\sigma_{i}$ is the i-th singular value
		- [ ] <mark class="hltr-orange">TODO</mark> _Calculate $\|\mathbf{A}\|_2$_


- #LinAlg [[Trace]]: $\operatorname{tr}(\mathbf{A})=\operatorname{tr}\left(\mathbf{A} \mathbb{E}\left[v v^{\top}\right]\right)=\mathbb{E}\left[\operatorname{tr}\left(\mathbf{A} v v^{\top}\right)\right]=\mathbb{E}\left[\operatorname{tr}\left(v^{\top} \mathbf{A} v\right)\right]=\mathbb{E}\left[v^{\top} \mathbf{A} v\right]$ is the hutchinson trace estimation. 
	- [ ] <mark class="hltr-orange">TODO</mark> *Check out how this makes calculations easier and under which conditions*


- #LinAlg Postive/Negative Semi-definite matrices are determined by their solution to the quadratic equation $\mathbf{x}^{\top}\mathbf{A}\mathbf{x}$.
	- if all positive $\mathbf{A}$ is positive-definite, if all negative $\mathbf{A}$ is negative-definite, if both $\mathbf{A}$ is indefinite


- #LinAlg $\large\tag{1}\kappa(\mathbf{A}) \triangleq\|\mathbf{A}\| \cdot\left\|\mathbf{A}^{-1}\right\|$ is called the condition number
	- The condition number gives me information on the stability of a matrix this is better than the determinant as the results are scaled to the level of instability
	- larger $\kappa$ indicated numerical instability


- #LinAlg The outer product interpretation of [[Matrix-Matrix Multiplication]] is relevant wrt. [[Eigenvalue decomposition|EVD]]: Scaling works with diagonal matrices.
	- Pre-multiplication scales rows
	- Post-multiplication scales columns

- #python good example of using zip to concat/work on the same string but in upper and lower case at the same time. 
```python
def first_non_repeating_letter(s):
	for char, char_lower in zip(s, s.lower()):
		if s.lower().count(char_lower) == 1:
		return char
return ""
```
# 11-06-2024
- #LinAlg [[Linear Maps]] are changes of in basis vectors of the input [[Vector Spaces]]. We just multiply the original basis with the columns of the matrix. Once we have the transformed basis, every vector can be reconstructed ([1](murphy2022.pdf#page=261&selection=200,2,217,58&color=yellow|murphy2022, p.231))
	- [x] <mark class="hltr-orange">TODO</mark> *I need to verify that this holds $\boldsymbol{y}=\left(\sum_{j=1}^n a_{1 j} x_j, \ldots, \sum_{j=1}^n a_{m j} x_j\right)$* ✅ 2024-06-30
- The Range is alternatively known as the [[Range|column space]]. 

# 10-06-2024
- #LinAlg $\mathbf{x}^\top\mathbf{A}\mathbf{x}$ is called the quadratic form; 
	- explicitly $\boldsymbol{x}^{\top} \mathbf{A} \boldsymbol{x}=\sum_{i=1}^n \sum_{j=1}^n A_{i j} x_i x_j$ 

- #LinAlg columns of a linear map describe how the map transforms the basis vectors of the domain and they span the image of the transformation

- #python  python uses row-major-order when going form vectors to matrices 

# 08-06-2024
- #python `{python}look_up_table = {roman: arabic for roman, arabic in zip("IVXLCDM", [1, 5, 10, 50, 100, 500, 1000])}`
	- This allows me to concat two equal length lists together into one reversible look up table
- #Calculus mathematically we can show that convex functions follow $t \mathbf{x}+(1-t) \mathbf{y} \in \mathcal{X}$
	- handy if we want to optimise anything

# 07-06-2024
- 5 and its multiples allow me to find the number of trailing zeroes in any factorial number. Just divide by $5, 5^2, 5^3, ...$ and sum. 
- `{python}[x for x in x if x.isalpha()]` allows me to filter out numbers from strings

# 06-06-2024
- `{python}np.rot90` allows me to rotate a matrix by 90 degrees
- `{python} array\[::-1,::-1\] reverses rows and columns

# 05-06-2024
- Hex conversion is done very easily with the `hex()` command. 
- `{python}t = {i: hex(i)[2:].upper() for i in range(16)}` creates a table for RGB to HEX conversion

# 27-05-2024
- In [[Eigenvalue decomposition]] it is important to understand that $\mathbf{AU}=\mathbf{U\Lambda}$ is best understood as the outer product/scaling interpretation of [[Matrix-Matrix Multiplication]]. 

- There exists a cluster of important concepts that all connect to symmetric matrices ([[Eigenthings]], [[Trace]] ($\operatorname{tr}(\mathbf{A})=\sum_{i=1}^n \lambda_i$), [[Determinant]] $\operatorname{det}(\mathbf{A})=\prod_{i=1}^n \lambda_i$ are all interconnected)

- Generalised [[Inner Products|Inner products]] are the foundation of all geometric interpretations attached to [[Vector Spaces]]. 
	- Inner products -> Norms, Angles, Distances 
	- There is something fascinating about inner and outer products and the differences that simple changes in positions cause 

# 26-05-2024
- [x] <mark class="hltr-orange">TODO</mark> *[[Eigenthings]] will require some in-depth graphical overview to be understood properly* ✅ 2024-06-26
- [x] <mark class="hltr-orange">TODO</mark> Add obsidian minimal theme indent lines in colour


# 25-05-2024
- [[Inner Products]], [[Metrics]] :Inner products, Norms, Metrics are all functions. I think it is useful to understand math as objects and transformation of these objects


# 24-05-2024
- There is a relationship between Probability Theory.
	- I found this by comparing the formula of the dimensionality of combined subspaces and the formula for the joint probability formula.
	- $\operatorname{dim}(U+W)=\operatorname{dim} U+\operatorname{dim} W-\operatorname{dim}(U \cap W)$ 
# Footnotes

[^1]: https://www.youtube.com/watch?v=SVwItRH2DNU&list=PLE1010BEDB031C039&index=5 
[^2]: 