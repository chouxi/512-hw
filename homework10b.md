### 9.7
(1)
When k = 2, this problem is can be soleved with min-cut using the max-flow method, which can be solved in polynomial time.
(2)
When k = 3, first find a min-cut between $S_1$ and $S_2$. Then remove the min-cuts, leaving  $S_1$ and $S_2$ unconnected. At this time, $S_3$ can only be connected with on of the other two vertices, we apply the same method to find the min-cut between these two vertices and again remove the min-cuts. Then $S_1$, $S_2$, $S_3$ will be unconnected. This can be solved in polynomial time as well. 
(3)
We can use a greedy algorithm for multiway cut. 
Find the minimum cut that splits $G$ into two components by running minimum flow from each $s_i \in V$ to each $s_{-i} \in V$. Denote the two resulting components by $G^\prime_1, G^\prime_2$. 
Find the minimum cut dividing $G^\prime_1$ or $G^\prime_2$, yielding $G^\prime_3$ (and a modified $G^\prime_1$ or $G^\prime_2$). 
Continue this process until all $k$ terminal nodes are in their own component.  