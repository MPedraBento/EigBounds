## EigBounds

This short program exemplifies a much faster algorithm for bounding eigenvalues of a set of matrices. It does so by computing principal minors instead of diagolizing the matrices.
We demonstrate the algorithm with an example of $5 \times 5$ symmetric matrices. This project follows the paper [JHEP 08 (2022) 273](https://link.springer.com/article/10.1007/JHEP08(2022)273).

## Theory

Let $A$ by an $N \times N$ symmetric matrix. Then by Sylvester's criterion, $A$ is positive definite ($A > 0$) if the leading principal minors are positive, $D_k(A) > 0$. Conversely, if we wish to assert that the eigenvalues of $A$ given by $\lambda_i$ are bounded such that $|\lambda_i| < c$ with $i = 1, \ldots, N$, then we need to prove that $A < c$ and $A > -c$ as defined above.

Then, if $D_k(A + cI) > 0$ and $D_k(cI - A) > 0$, it follows that $|\lambda_i| < c$. This criterion is more numerical robust, it is always analytical and it is faster to compute. 

A corollary of this statement is that |\mathrm{diag}(A)| < c is a necessary condition for $|\lambda_i| < c$. This allows to greatly reduce the amount of matrices generated prior to the computation of the leading principal minors.
