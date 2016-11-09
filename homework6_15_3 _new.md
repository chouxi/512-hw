<script type="text/javascript"
   src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
### CLRS 15.3
- First, sorting the input points by x-coordinate.
- Then, we defined subproblem min_dist(i, j).
$$
i->...->1->...->j
$$
    This min_dist is the same with min_dist(j, i). Only different in direction. But from 1->i and j->1 same as 1->j, i->1.

- So, there are different transition fucntions:
    
    - When i == 1 and j == 2, min_dist(i,j) = cost_(i, j) = cost(1,2).
        
        In this case, back and forth has the same path.1->2 and 2->1, we cannot touch 3 because the property of bitonic problem.

    - When i < j - 1, min_dist(i, j) = min_dist(i, j - 1) + cost(j-1,j)
        
        In this case, when k = j - 1 has the min cost(k,j). So, we can put j - 1 to the 1->j path directly.

    - When i = j - 1
        $$
            min_{1<=k<i}(l(k,i) + dist(k,j))
        $$
        In this case, we have to get from i to 1, but didn't know how to back. Then for every 1<=k<i, we check wheter the l(k,i)(which is computed before) + dist(k,j) is smaller.

- Complexity:
    - sort the array is $O(nlogn)$.
    - For every i we need to calculate every j one time. which is $O(n^2)$
    - For i == j-1, need $O(n)$ time to check every k, so plus $O(n)$, which is dominated by $O(n^2)$.
    - So, the total complexity is $O(n)$.
    - spcace complexity is $O(n^2)$