<script type="text/javascript"
   src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
Homework 5-B

Section 2

Yanhao Wang 175002614

Mohan Xiao 174005865

Zheng Qi 174003950
#### 5.19 
- (a)

We can see that to prove encoding with Huffman will have a length of \\( \sum m{p_i}log{\frac1 p_i}\\) is equivalent to proving that the code length for \\( p_i \\) element is \\( log{\frac1 p_i }\\)

Huffman encoding has the followign scheme:

>If some character occurs with frequency more than 2/5, then there is quaranteed to be a codeword of length 1.

>If all character occur with frequency less than 1/3, then there is guanranteed to be no codeword of length 1.

From the above property, we know that element with \\( p_i = 1/2 \\) must be in the first layer. 

Then we consider the rest of the tree. The same property applies for the subtree and it is obvious that element with \\( p_i = 1/4 \\) that is in the first layer of the subtree, since \\(1/4 \div 1/2 = 1/2\\).  Thus it is in the \\( 2_{nd}\\) layer of the original tree.  

Continue this approach and we can see that the element with \\( p_i = \frac1 {2^k} \\) is in the \\(k_{th}\\) layer of the Huffman tree.

- (b)

When \\( p_i = \frac1 n\\), the entropy is the largest.

When \\( p_i = 0 \\) or \\(1\\), the entropy is the smallest.
#### 5.31
As for this question, if the time which number i customer spend is \\(t_i\\), We ﬁrst observe that no matter what order we choose to serve the customers in, the total time taken does not 

change. The total time (lets call it X) required to serve all of the customers is always the sum of their service times. Thus the total time which all the customers will spend 

is \\(w = (n-1)t_1 + (n-2)t_2 + \ldots + t_i\\)

Thus, we wish to minimize the number of customers that are still waiting at any given time. This means we want to serve the customers that require less time ﬁrst, 

Then we can see that if we want the w to become minimus, we can just sort the \\(t_i\\) as ascending order, the time comolixity of this problem is \\(O(nlogn)\\)
#### 5.33

According to the question, \\(n=2^k\\). In the base set \\(S_1\\), there are n elements from 1 to \\(k^2\\).

Consider set \\(S_2\\) and \\(S_3\\) which is the optimal solution, odd numbers in \\(S_2\\) and even numbers in \\(S_3\\)

For greedy sets \\(S_{4_{i}}\\), elements in each sets has elements from \\(2^{i}\\) to \\(2^{i+1}\\). Assume they are all connected to each other in the graph.
Obviously, combine all the sets \\(S_{4_{i}}\\) is equal to \\(S_1\\).

Above all, \\(S_2\\) and \\(S_3\\) has no common elements are optimal. \\(S_{4_{i}}\\) has at least one common element with \\(S_{4_{i+1}}\\) 