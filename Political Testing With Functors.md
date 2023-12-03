# Title: The Political Test As A Category [DRAFT I]

###### Reading Time: 5 minutes

### Summary

A political test is a category.  Test scoring is a functor into Vect.  We build 3 scoring functors by sending a test answer profile to a row matrix, a diagonal matrix, and a column matrix, respectively.

### Contents

1. The Political Test as a Category  
    1. Objects  
    2. Morphisms
2. Test Scoring Is A Functor
    1. The Row Matrix Functor
    2. The Diagonal Matrix Functor
    3. The Column Matrix Functor
3. Conclusion: What have we done, morally?

# 1. The Political Test as a Category

Consider a political test with $n$ questions and $k$ possible answers for each question.

The test can be represented as a concrete category $P$ with:

#### 1.1. Objects

$P$ has objects $Q$ and $A$, where:

1. $Q$ is a set of $n$ multiple choice questions

1. $A$ represents the $k$ possible answers

#### 1.2. Morphisms

$P$ has two classes of morphisms:

1. Identity morphisms $1_Q$ and $1_A$
2. Answer morphisms $f: Q \to A$

Answer morphisms $f$ are functions that map each question $q \in Q$ to an answer $a \in A$.


# 2. Test Scoring Is A Functor

The test comes with a scoring function:

$$ S: Hom_P[Q, A] \to  \R^{12} $$

Given an answer session $f$, the scoring function returns a vector $v$ in $\R^{12}$, where $v_i$ is the score for the $i$ th political position.

We can also define $S$ as a Scoring Functor from $P$ to $Vect$, the category of real vector spaces. We will build 3 Scoring Functors, $S_1$, $S_2$, $S_3$ by sending $f$ to a row matrix, a diagonal matrix, and a column matrix, respectively.

### 2.1. The Row Matrix Functor

Let $S_1$ be the functor from $P$ to Vect defined as follows:

$$ S_1(Q) = \R, $$

$$ S_1(A) = \R^{12} $$

$$ S_1(f) = f' $$

where $f'$ is the row matrix of political scores:

$$ [v_1, v_2, \ldots , v_{12}] $$

We can then define the score vector $v$ as follows:

$$ v = f'(1), \text{ for } 1  \in  \R  $$

### 2.2. The Diagonal Matrix Functor

Let $S_2$ be the functor from $P$ to $Vect$ defined as follows:

$$S_2(Q) = \R^{12}$$

$$S_2(A) = \R^{12}$$

$$S_2(f) = f''$$

where $f''$ is the diagonal matrix of political scores:

$$f'' = \begin{bmatrix} v_1 & 0 & \cdots & 0 \\ 0 & v_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & v_{12} \end{bmatrix}$$

We can then define the score vector $v$ as follows:

$$v = \text{diag}(f'')$$

Or as:

$$v_i = f''e_i$$

where $e_i$ is the $i$ th standard basis vector in $\R^{12}$

### 2.3. The Column Matrix Functor

Let $S_3$ be the functor from $P$ to Vect defined as follows:

$$S_3(Q) = \R^{12}$$

$$S_3(A) = \R$$

$$S_3(f) = f'''$$

where $f'''$ is the column matrix of political scores:

$$f''' = \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_{12} \end{bmatrix}$$

We can then define the score vector $v$ as follows:

$$v_i = (e_i)^T f'''$$

# 3. Conclusion and Open Questions

We have shown that a political test is a category, and that test scoring is a functor into Vect.  We have built 3 scoring functors by sending a test answer profile to a row matrix, a diagonal matrix, and a column matrix, respectively.

We have some open questions:


1. What is the relationship between the 3 scoring functors? 
    1. Are they isomorphic?
    2. If so, how?


2. What is the right way to model how much information is lost in scoring? Does our categorical setup help us answer this question?
