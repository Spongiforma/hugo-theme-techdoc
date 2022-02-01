+++
title = "Linear optimisation"
draft = false
+++

## Definitions {#definitions}

Standard form:

minimise \\(\bm{c^T x}\\),
subject to \\(A\bm{x} = \bm{b}\\)
\\(\bm{x} \geq \bm{0}\\)

A problems can be converted to another problem by applying the following operations:

-   Elimination of free variables:

Given an unrestricted variable \\(x\_j\\) we replace it with \\(x\_j^+ - x\_j^-\\) which are both non-negative.

-   Elimination of inequality constraints:

Given \\(\sum\_{j=1}^n a\_{ij}x\_j \leq b\_i\\),

we introduce a new **slack** variable \\(s\_i \geq 0\\):

\\[
\sum\_{j=1}^n a\_{ij}x\_j + s\_i = b\_i
\\]

the opposite is treated with a **surplus** variable \\(s\_i \geq 0\\) but replace '+ s\_i' with '- s\_i'


### Piecewise linear convex objective problems {#piecewise-linear-convex-objective-problems}

A function \\(f : \mathcal{R}^n \mapsto \mathcal{R}\\), is called convex if for every \\(\bm{x},\bm{y} \in \mathcal{R}^n\\), and every \\(\lambda \in [0,1]\\), we have:

\\[
f(\lambda\bm{x} + (1-\lambda)\bm{y}) \leq \lambda f(\bm{x}) + (1-\lambda)f(\bm{y})
\\]

A concave function is defined similarly but inverse.

`Note relation between local and global minima/maxima due to this property.`

**Theorem**

Let \\(f\_1,\cdots,f\_m : \mathcal{R}^n \mapsto \mathcal{R}\\) be convex functions. Then the function \\(f\\) defined by
\\(f(\bm{x}) = \max\_{i=1,\ldots,m}f\_i(\bm{x})\\) is also convex.

**Transformation**

"minimize \\(\max\_i (\bm{c}\_i^T \bm{x} + d\_i)\\), subject to \\(Ax \geq b\\)"

can become:

"minimize z, subject to \\(z\geq \bm{c}\_i^T \bm{x} + d\_i\\) for all i, Ax >= b"

When modulus appears:

minimize \\(\sum\_{i=1}^n c\_i |x\_i|\\)

subject to \\(Ax\geq b\\)
where the coefficients are nonnegative such that the function is convex.

becomes:

minimize \\(\sum\_{i=1}^n c\_iz\_i\\)

subject to \\(Ax \geq b, x\_i \leq z\_i, -x\_i\leq z\_i\\)

**or**

minimize \\(\sum\_{i=1}^n c\_i(x^+\_i + x^-\_i)\\)

subject to \\(Ax^+ - Ax^- \geq b, x^+,x^- \geq 0\\).

Notice that \\(x^+\_i = 0\\) or \\(x^-\_i = 0\\).


### Dynamical systems {#dynamical-systems}

\\[
\bm{x}(t+1) = \bm{Ax}(t) + \bm{Bu}(t)
\\]

where we are free to choose u(t) subject to Du(t) <= d.

\\[
y(t) = \bm{c}^T\bm{x}(t)
\\]

**possible form**

minimize z
subject to -z <= y(t) <=  z
x(t+1) = Ax(t) + Bu(t)
y(t) = c'x(t)
Du(t) <= d
x(T) = 0,
x(0) = given,


### Possible outcomes {#possible-outcomes}

-   There exists a unique optimal solution
-   There exist multiple optimal solutions; in this case, the set of optimal solutions can be either bounded or unbounded
-   The optimal cost -infty, and no feasible solution is optimal
-   The feasible set is empty
-   there is also "minimize 1/x subject to x>0" but it does not arise in linear programming


## Geometry {#geometry}


### Polyhedron {#polyhedron}

**Definition**
A polyhedron is a set that can be described in the form \\(\\{\bm{x} \in \mathcal{R}^n \vert \bm{Ax}\geq \bm{b}\\}\\), where A is an m x n matrix and b is a vector in \\(\mathcal{R}^m\\)

**Definition**

Let \\(\bm{a}\\) be a nonzero vector in \\(\mathcal{R}^n\\), and let b be a scalar.

1.  The set \\(\\{\bm{x} \in \mathcal{R}^n \vert \bm{a}'\bm{x} = \bm{b}\\}\\) is called a hyperplane
2.  The set \\(\\{\bm{x} \in \mathcal{R}^n \vert \bm{a}'\bm{x} \geq \bm{b}\\}\\) is called a halfspace.

Note that a hyperplane is the boundary of a corresponding halfspace. The vector \\(\bm{a}\\), is perpendicular to the hyperplane. (note that a is the normal of the hyperplane. In a way, b is the distance of the hyperplane from the origin)

**Definition**

A set \\(S \subset \mathcal{R}^n\\) is convex if for any \\(\bm{x},\bm{y} \in S\\), and any \\(\lambda \in [0,1]\\), we have \\(\lambda \bm{x} + (1-\lambda)\bm{y} \in S\\). Notice that the expression is a weighted average of x,y.

**Definition**

Let \\(x^1,\ldots,x^k\\) be vectors in \\(\mathcal{R}^n\\) and let \\(\lambda\_1,\ldots,\lambda\_k\\) be nonnegative scalars whose sum is unity.

The vector \\(\sum\_{i=1}^k \lambda\_i\bm{x}^i\\), is said to be a **convex combination** of the vectors \\(x^1,\ldots,x^k\\)

The **convex hull**, of the vectors \\(x^1,\ldots,x^k\\) is the set of all convex combinations of these vectors.

**Theorem**

1.  The intersection of convex sets is convex.
2.  Every polyhedron is a convex set
3.  A convex combinations of a finite number of elements of a convex set also belongs to that set.
4.  The convex hull of a finite number of vectors is a convex set.


### Corners {#corners}

**Definition**

Let P be a polyhedron. A vector \\(x \in P\\) is an **extreme-point** of P if we cannot find two vectors y,z in P both different from x and a scalar \\(\lambda \in [0,1]\\) such that \\(x = \lambda y + (1-\lambda)z\\).

**Definition**

Let P be a polyhedron. A vector \\(x \in P\\) is a **vertex** of P if there exists some \\(c\\) such that \\(c'x < c'y\\) for all \\(y \in P\\), \\(y \neq x\\).
