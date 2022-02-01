+++
title = "Linear Algebra"
draft = false
+++

## Vector space {#vector-space}

Requirements for a set of entities to form a vector space

1.  Closure under commutative and associative addition
2.  Closure under multiplication of a scalar
3.  The existance of a null vector
4.  Multiplication by unity leaves any vector unchanged
5.  Each vector has a corresponding negative vector


## Linear equations {#linear-equations}


### Row-echelon form {#row-echelon-form}

1.  All zero rows are at the bottom of the matrix
2.  If two sucessive rows are non-zero, the second row starts with strictly more zeros than the first


### Reduced row-echelon form {#reduced-row-echelon-form}

1.  It's in row-echelon form
2.  The leading left most non-zero entry in each non-zero row is 1
3.  All other elements of the column in which the leading entry 1 occurs are zeros


### Row operations {#row-operations}

1.  Interchanging rows
2.  Multiplying row by non-zero scalar
3.  Adding a multiple of one row to another row

Preserves row-equivalence


### Gauss-Jordan algorithm / Gaussian elimination {#gauss-jordan-algorithm-gaussian-elimination}

You should know this


### Homogenous equations {#homogenous-equations}

"Implicit equations with no non-zero constants"

`A homogenous system of m linear equations in n unknowns always has a non-trivial solution if m < n`


## Matrices {#matrices}


### Inner product {#inner-product}

Hilbert space is basically inner product space for finite dimensions

Orthornormal: \\(\braket{\hat{e}\_i}{\hat{e}\_j} = \delta\_{ij}\\) (i.e. orthogonal and normalised)

\begin{aligned}
\braket{a}{b} & = \braket{b}{a}^\ast \\\\
& = \sum\_i a\_i^\ast b\_i \text{ (On orthonormal basis)} \\\\
& = \sum\_{ij} a\_i^\ast b\_j \braket{\hat{e}\_i}{\hat{e}\_j} \\\\
\end{aligned}


### Inequalities and equalities {#inequalities-and-equalities}


#### Cauchy-Schwarz's inequality {#cauchy-schwarz-s-inequality}

\\[
\vert\braket{a}{b}\vert \leq \Vert a\Vert \Vert b\Vert
\\]

In 2d, abcosx <= aba

equality when a is a scalar multiple of b


#### Triangle Inequality {#triangle-inequality}

\\[
\Vert a+b \Vert \leq \Vert a \Vert + \Vert b \Vert
\\]


#### Bessel's inequality {#bessel-s-inequality}

\\[
\Vert a \Vert^2 \geq \sum\_i \vert \braket{\hat{e}\_i}{a} \vert^2
\\]
or

\\[
\braket{a}{a} \geq \sum\_i \vert a\_i \vert^2
\\]

where \\(\hat{e}\_i\\) is an orthonormal basis

where the equality holds if the sum includes all N basis vectors or if remaining basis vectors have
a\_i = 0


#### Parallelogram equality {#parallelogram-equality}

\\[
\Vert a + b \Vert^2 + \Vert a - b \Vert^2 = 2(\Vert a \Vert^2 + \Vert b \Vert^2)
\\]


### Functions of matrices {#functions-of-matrices}

\\[
\exp A = \sum\_{n=0}^\infty \frac{A^n}{n!}
\\]

Derivatives exist.


### Operations {#operations}


#### Transpose {#transpose}

\\[
(AB\ldots G)^T = G^T \ldots C^T B^T A^T
\\]


#### Hermitian Conjugate (Complex Transpose) {#hermitian-conjugate--complex-transpose}

\\[
A^\dagger = (A^\ast)^T = (A^T)^\ast
\\]


#### Trace {#trace}

\\[
\Tr A = \sum\_i A\_{ii}
\\]

\\[
\Tr ABC = \Tr BCA = \Tr CAB
\\]

(Invariant under cyclic permutations)

\\[
\Tr \Omega = \Tr U^\dagger \Omega U
\\]


#### Determinant {#determinant}

Minor:

\\(M\_{ij}\\) = determinant of matrix obtained by removing row i and column j

Cofactor:

\\(C\_{ij} = (-1)^{i+j} M\_{ij}\\)

Thus a determinant is the sum of the products of the elements along any row or column and their corresponding cofactors

e.g.

\\[
\sum\_i A\_{1i}C\_{1i}
\\]

<!--list-separator-->

-  Properties

	1.  \\(\vert A^T \vert = \vert A \vert\\)

	2.  If rows of A are interchanged, its determinant changes sign but is unaltered in magnitude

	3.  if all the elements of a row or column of A have a common factor, it can be factored out. Also, \\(\vert \lambda A \vert = \lambda^N \vert A \vert\\)

	4.  If any two rows are identical or multiples of one another, det is 0

	5.  Determinant is unchanged by adding to the elements of one row any fixed multiple of the elements of another row

	6.  Determinant of the product of multiple matrices is invariant under permutations of the matrices

	 \\[
	 \vert A \vert = a \cdot (b \times c)
	 \\]

	 \\(\vert A^{-1} \vert = \vert A \vert^{-1}\\)

	 \\[
	 \det \Omega = \det U^\dagger \Omega U
	 \\]


#### Inverse {#inverse}

Exists when determinant is not zero, i.e. the matrix is non-singular

\\[
(A^{-1})\_{ik} = \frac{C\_{ki}}{\vert A \vert}
\\]

\\[
(ABC)^{-1} = C^{-1}B^{-1}A^{-1}
\\]

A diagonally dominant matrices are invertible/non-singular


#### Rank {#rank}

R(A) = R(A^T) = number of linearly independent vectors row-wise or column-wise

or

Size of the largest square submatrix of A whose determinant is non-zero


### Special forms {#special-forms}


#### Diagonal matrix {#diagonal-matrix}

Having non-zero elements only on the leading diagonal

Also denoted by e.g. A = diag(1,2,-3)

\\[
\vert A \vert = \prod\_i A\_{ii}
\\]

\\[
A^{-1} = \text{diag} (\frac{1}{A\_{11}},\frac{1}{A\_{22}}, \ldots)
\\]

if A and B are diagonal, their product is commutative


#### Lower or upper triangular matrices {#lower-or-upper-triangular-matrices}

\\[
\vert A \vert = \prod\_i A\_{ii}
\\]


#### Symmetric and antisymmetric matrices {#symmetric-and-antisymmetric-matrices}

Symmetric:

\\[
A = A^T
\\]

Anti/Skew-symmetric:

\\[
A = -A^T
\\]

Any matrix can be written as a sum of a symmetric and an antisymmetric matrix

\\[
A = \frac12 (A + A^T) + \frac12 (A - A^T)
\\]

Note that if A is an NxN antisymmetric matrix, |A| = 0 if N is odd


#### Orthogonal matrix {#orthogonal-matrix}

\\[
A^T = A^{-1}
\\]

\\[
\vert A \vert = \pm 1
\\]


#### Hermitian matrices (Complex Symmetric) {#hermitian-matrices--complex-symmetric}

Hermitian

\\[
A = A^\dagger
\\]

Anti-Hermitian

\\[
A = -A^\dagger
\\]

\\[
A = \frac12 (A+A^\dagger) + \frac12(A-A^\dagger)
\\]


#### Unitary matrix (complex orthogonal) {#unitary-matrix--complex-orthogonal}

\\[
A^\dagger = A^{-1}
\\]

The determinant and eigenvalues of a unitary matrix have unit modulus

It also represents a linear operator which leaves the norms (inner products) of complex vectors unchanged (i.e. orthonormal-ness)

An operator is unitary iff each of its matrix representations are unitary

The rows may be interpreted as components of n orthonormal vectors similar to how columns are components of n vectors.


#### Normal matrices {#normal-matrices}

\\[
AA^\dagger = A^\dagger A
\\]

Hermitian matrices and unitary matrices are normal

A Normal matrix is hermitian iff it has real eigenvalues


## Vectors and spaces {#vectors-and-spaces}


### Completeness relation for orthonormal vectors {#completeness-relation-for-orthonormal-vectors}

\\[
\sum\_i \ket{i}\bra{i} = I
\\]

where |i> is any orthonormal basis for the vector space V

Which allows us to represent any operator in the outer product notation.
Given A : V \\(\rightarrow\\) W, and |v\_i> and |w\_j> are orthornormal bases for V and W

\begin{aligned}
A & = I\_W A I\_V \\\\
& = \sum\_{ij} \bra{w\_j}A\ket{v\_i} \ket{w\_j} \bra{v\_i}
\end{aligned}


#### Outer product representation of Unitary U {#outer-product-representation-of-unitary-u}

Define:

\\[
\ket{w\_i} \equiv U\ket{v\_i}
\\]

Note that that implies:

\\[
U = \sum\_i \ket{w\_i} \bra{v\_i}
\\]

And that if |v\_i> and |w\_i> are any orthonormal bases, then U defined above is also unitary


### Projectors {#projectors}

A class of Hermitian operators. Let W be a k-dimensional vector subspace of the d-dimensional vector space V. Using Gram-Schmidt procedure it is possible to construct an orthonormal basisc for V (|1>,...,|d>)such that |1>,...,|k> is an orthonormal basis for W. The projector by defintion:

\\[
P \equiv \sum\_{i=k}^k \ket{i} \bra{i}
\\]

\\[
(P\_i)\_{kl} = \delta\_{kl}\delta\_{li}
\\]

The orthogonal complement of P is Q = I - P, which is a projector onto the vector space spanned by |k+1>...|d>

\\[
P\_i P\_j = \delta\_{ij} P\_j
\\]

Note that P^2 = P


## Operators {#operators}


### Commutator {#commutator}

Definition:

\\[
\Omega \Lambda - \Lambda\Omega \equiv [\Omega,\Lambda]
\\]

Identities:

\\[
[\Omega,\Lambda] = \Lambda[\Omega,\theta] + [\Omega,\Lambda]\theta
\\]

\\[
[\Lambda\Omega,\theta] = \Lambda[\Omega,\theta] + [\Lambda,\theta]\Omega
\\]


### Diagonalisable {#diagonalisable}

A diagonal representation for an operator A on vector space V is a representation:

\\[
A = \sum\_i \lambda\_i \ket{i}\bra{i}
\\]
with corresponding eigenvalues \\(\lambda\_i\\)

An operator is diagonalisable is it has a diagonal representation.

Any normal operator M on a vector space V is diagonal wrt some orthonormal basis for V. Also any diagonalisable operator is normal


### Active and passive transformations {#active-and-passive-transformations}

If all vectors in a space are subject to a unitary transform (**Active Transformation**)

\\[
\ket{V} \to U\ket{V}
\\]
Then the same change would be effected if subjected operators to the change (**Passive Transformation**)
\\[
\Omega \to U^\dagger\Omega U
\\]


## Eigenvectors and eigenvalues {#eigenvectors-and-eigenvalues}

\\[
Ax = \lambda x
\\]

\\[
A^{-1}x^i = \frac{1}{\lambda\_i}x\_i
\\]

The eigenspace corresponding to a eigenvalue v is the set of vectors with eigenvalue v


### Normal matrices: {#normal-matrices}

\\[
A^\dagger x^i = \lambda\_i^\ast x^i
\\]

If \\(\lambda\_i \neq \lambda\_j\\), the eigenvectors \\(x^i\\) and \\(x^j\\) must be orthogonal

An eigenvalue corresponding to two or more different eigenvectors (i.e. they are not multiples) are **degenerate**. or in other words the **eigenspace** has more than 1 dimensions

Suppose \\(\lambda\_1\\) is k-fold degenerate (for x^1 to x^k), then any linear combination of those x^1 also has an eigenvalue of \\(\lambda\_1\\)


### Gram-Schmidt orthogonalisation {#gram-schmidt-orthogonalisation}

\begin{aligned}
z^1 & = x^1, \\\\
z^2 & = x^2 - \braket{\hat{z}^1}{x^2} \hat{z}^1, \\\\
z^3 & = x^3 - \braket{\hat{z}^2}{x^3} \hat{z}^2 - \braket{\hat{z}^1}{x^3} \hat{z}^1, \\\\
& \ldots \\\\
z^k & = x^k - \sum\_{i=1}^{k-1} \braket{\hat{z}^i}{x^k}\hat{z}^k \\\\
\end{aligned}

Where \\(\hat{z}^i =  \frac{z^i}{\Vert z^i \Vert}\\)


### Eigen-everything of Hermitian and anti-hermitian matrices {#eigen-everything-of-hermitian-and-anti-hermitian-matrices}

Eigenvalues of hermitian matrices are real

Eigenvalues of anti-hermitian matrices are pure imaginary (-\\(\lambda\\))

To every hermitian operator, there exists at least a basis consisting of its orthonormal eigenvectors. It is diagonal in this eigenbasis and has its eigenvalues as its diagonal entries.


### Eigen-everything of unitary matrix {#eigen-everything-of-unitary-matrix}

Eigenvalues of a unitary matrix have unit modulus and are complex.

Assuming no degeneracy, the eigenvectors of a unitary operator are mutually orthogonal


### Eigen-everything of a general square matrix {#eigen-everything-of-a-general-square-matrix}

Any N x N matrix with distinct eigenvalues has N linearly independent eigenvectors.

If it has a degenerate eigenvalues, however, then it may or may not have N linearly independent eigenvectors.

Not having linearly independent eigenvectors makes it **defective**


### Simultaneous eigenvectors {#simultaneous-eigenvectors}

Two different normal matrices have a common set of eigenvectors that diagonalises them both if and only if they commute

If an eigenvalue of A is degenerate then not all of its possible sets of eigenvectors will also constitute a set of eigenvectors of B. i.e. If B is nondegenerate but A is degenerate, then all eigenvectors of B are eigenvectors of A.


### Determination {#determination}

Chracteristic function:
c(lambda) = det | A - lambda I |
Characteristic equation:

\\[
\vert A - \lambda I \vert = 0
\\]

LHS is the characteristic/secular determinant of A

When the determinant is written as a polynomial equation in \\(\lambda\\), the coefficient of \\(-\lambda^{N-1}\\) will be Tr A, i.e. the sum of the roots (recall p+q = -b/a, pq = c/a)


## Change in basis {#change-in-basis}

Given S where:

\\[
x\_i = \sum\_{j=1}^N S\_{ij}x'\_j
\\]

\\[
x = Sx'
\\]

where S is the transformation matrix associated with the change in basis

and

\\[
x' = S^{-1} x
\\]

The components of x transform **inversely** to how the basis vectors transform, as the vector x itself much remain unchanged

This applies to linear operators of x:

\\[
y = Ax, y' = A'x'
\\]

=>

\\[
y' = S^{-1}ASx'
\\]

or in other words:

\\[
A' = S^{-1}AS
\\]

which is an example of a similarity transformation

So any property of A which represents some basis independent property of its linear operator will be shared by A'

1.  If A = I, A' = I
2.  |A| = |A'|
3.  Eigenvalues are the same
4.  Trace is unchanged


### Unitary S {#unitary-s}

1.  If the original basis is orthonormal and S is unitary then the new basis is also orthonormal
2.  If A is (anti) hermitian then A' is (anti) hermitian
3.  If A is unitary then A' is also unitary


## Diagonalisation of matrices {#diagonalisation-of-matrices}

Define a basis \\(x^j\\) given by:
\\[
x^j = \sum\_{i=1}^N S\_{ij}{\bf e\_i},
\\]

where \\(x^j\\) are chosen to be the eigenvectors of the linear operator \\(\mathcal{A}\\).
i.e.

\\[
\mathcal{A} x^j = \lambda\_j x^j
\\].

In our new basis, \\(\mathcal{A}\\) is represented by the matrix \\(A' = S^{-1}AS\\). The columns of S are the eigenvectors of the matrix A, i.e. \\(S\_{ij} = (x^j)\_i\\). Therefore, A' is diagonal with the eigenvalues of \\(\mathcal{A}\\) as the diagonal elements.

Since we require S to be non-singular, the N eigenvectors of A must be linearly independent and form a basis for the N-dimensional vector space. Any matrix with distinct eigenvalues can be diagonalised by this procedure. If it doesn't have N linearly independent eigenvectors, then it cannot be diagaonlised.

For normal matrices, the N eigenvectors are indeed linearly independent. For them, S is unitary.

Note:

\\[
\det \exp A = \exp(\Tr A)
\\]


## Infinite dimensions {#infinite-dimensions}

Define a function

Inner product in (countable) infinite dimensions:

\\[
\braket{f}{g} = \int\_0^L f(x)g(x) \dd{x}
\\]


### Dirac delta {#dirac-delta}

In infinite dimensions,

\\[
\braket{x}{x'} = \delta(x-x')
\\]

if two basis vectors are the same.
\\[
\delta '(x-x') = \delta(x-x')\dv{x}
\\]

Dirac delta with fourier transform

\\[
\delta(x-x') = \frac{1}{2\pi}\int\_{-\infty}^\infty e^{ik(x-x')}\dd{k}
\\]

\\[
\delta(f(x)) = \sum\_i \frac{\delta(x\_i-x)}{|\dv{f}{x\_i}|}
\\]
where x\_i are the zeros of f(x)


### Operators {#operators}


#### Differential operator {#differential-operator}

\\[
D\ket{f} = \ket{\dv{f}{x}}
\\]

implies

In the |x> basis,
\\[
\bra{x}D\ket{x'} = D\_{x,x'}=\delta'(x-x')=\delta(x-x')\dv{x'}
\\]

where it is integrated over the second index (x') and pulls out the derivative of f at the first index (x).

We can turn it hermitian by turning it into the form:

\\[
K = -iD
\\]

but in infinite dimensions, K^t = K is not sufficient to be hermitian. It is only hermitian in the space of functions that obey:

\\[
-ig^\*(x)f(x) | \given\_a^b = 0
\\]

so that <g|K|f> = <f|K|g>\*.

<!--list-separator-->

-  eigeneverything

	 X-basis

	 \\[
	 K\ket{k} = k\ket{k}
	 \\]

	 \\[
	 -i\dv{x}\psi\_k(x) = k\psi\_k(x)
	 \\]

	 where \\(\psi\_k(x) = \braket{x}{k}\\).

	 the solution is:

	 \\[
	 \psi\_k(x) = Ae^{ikx}
	 \\]

	 where we choose \\(A = (1/2\pi)^{-1/2}\\)

	 and <k|k>


#### X basis {#x-basis}

X|x> = x|x>

\\[
\bra{x'}X\ket{x} = x\delta(x'-x)
\\]

Action on functions:

X|f> = |F>

F(x) = xf(x)

\\[
\bra{k}X\ket{k'} = i\delta'(k-k')
\\]

[X,K] = iI
