<script type="text/javascript"
   src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
### CLRS 15.3
- 15.3-1

    Running Recursive-Matrix-Chain is more efficient way to solve this problem than enumerate all the ways of parenthesizing.

    The running time of enumerate all the ways of parenthesizing is $\Omega(4^n/n^{3/2})$. The running time of recursive one is $\Omega(2^n)$

    Let's see the upper bound of recursive-matrix-chain.

    We can derive the upper bound from the lower bound showed in the textbook.
    $$T(n)\leq\left\{
    \begin{array}{ll}
        c &\mbox{if n = 1;}\\
        c + \sum_{k=1}^{n-1}(T(k)+T(n-k)+c) &\mbox{else}
    \end{array}
    \right.$$

    So from the textbook, we can solve the above equations into:
    $$T(n)\leq2\sum_{i=1}^{n-1}T(i)+cn$$
    Using substitution to calculate the upper bound. shall show that $T(n)\leq\ cn3^{n-1}$ for all $n\geq1$. The base case is $T(1)\leq\ c=c*1*3^{1-1}$
    $$\begin{array}{ll}
        T(n)&\leq2\sum_{i=1}^{n-1}T(i)+cn\\
        &\leq2\sum_{i=1}^{n-1}ci3^{i-1}+cn\\
        &\leq\ c*(2\sum_{i=1}^{n-1}i3^{i-1}+n)\\
        &=c*(2*(\frac{n3^{n-1}}{3-1}+\frac{1-3^n}{4})+n)\\
        &=cn3^{n-1}+c(\frac{1-3^n}{2}+n)\\
        &=cn3^{n-1} + \frac{c}{2}(\frac{1-3^n}{2}+n)\\
        &\leq\ cn3^{n-1}\mbox{for all c > 0,} n \geq 1\\
        &=O(n3^{n-1})
    \end{array}$$
    So the recursive-matrix-chain is more efficient than enumeration solution.

- 15.3-2

    Given an array [16,3,4,7,8,10,9,6,2,1,5,13,11,12,15,14]
    ![merge_sort](https://github.com/chouxi/512-hw/raw/master/HW6_ms_pic.png)

    Because there is no overlapping subproblems in the mergesort. So the memorized DP cannot speed up this kind of problem.


- 15.3-3
    
    Yes, this problem has the optimal substructure too.

    For a given matrix $A_k$ at which we split the product, we have two subproblems—parenthesizing $A_i A_{i+1}...A_{k}$ and parenthesizing $A_k A_{k+1}...A_{j}$ —and we must solve both of them maximum. If we don't solve these parts maximum, the final maximum solution must has a different way to parenthesizing the subproblem. So this problem has the optimal substructure.

- 15.3-4
    
    $$
    \begin{array}{ll}
        A_1&=6X8\\
        A_2&=8X5\\
        A_3&=5X3
    \end{array}
    $$
    The sequence p is <6,8,5,3>.

    If we use greedy approach, we will multiply it in $((A_1 A_2)A_3)$, which is $6*8*5+6*5*3=330$, because $p_0*p_2*p_3$ is smaller than $p_0*p_1*p_3$.

    But the optimal solution is  $(A_1(A_2 A_3))$, which is $8*5*3+6*8*3=264$

    So, the approach yields a suboptimal solution.

- 15.3-5

    We can see that if we have limits on  the number of cut, the optimal result substructure of problem cannot used to calculate the substructure which contains it, because of the difference in limits.

    The limitations add the dependent to the subproblem with each other. For example length i has a limit 1, but length k which is smaller than i has a limit 10. The optimal solution of k uses 5 cuts, this substructure k cannot be used to calculate substructure i.

- 15.3-6

    If $c_k = 0$, we only need to find the sequence that makes product of r values are maximum.

    If $c_k$ is arbitrary values, the result of change will not be the $result_i * r_{ij}$. It becomes $result_i * r_{ij} + c_k$. But the problem is the $c_k$ has no relation with i or j, it depends on the time of changes. So, this problem likes the 15.3-5 which has limit on number. The substructures has denpendency with each other in $c_k$. That means the optimal solution cannot necessarily produced by the substructure, because the optimal result of substructure may not optimal when used in the optimal solution of the problem because of the $c_k$.
