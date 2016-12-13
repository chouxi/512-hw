9.6

Assume that the $ T_s $ is the minimun steiner tree, So we can just handle the tree like the approximation algorithm for the TSP,the meaning is that use each edge for twice so we can just have a loop. Now we can just start from one of the point of this loop and when the next vertex is not belong to V', we can just ignore them. So the final loop is a loop which only contains the vertices that belong to V'. 

In this way, we can use triangle inequality rules that we have $ d_{ik} < d_{ij} + d{jk} $ . If the $ T_s $ as the minimun striner tree have cost C.Then as follow the path above we can obtain a path which have cost 2C. So that means the cost of MST which only contain V' can still not bigger than the twice of the cost of minimun striner tree. 

9.9
a)
We first show that any solution S that the algorithm outputs must have the property that $ w(S) >= 1/2 * \sum_{c \in E} w(e) $. Because that the maximum size of the maximun cut can be  $ w(S) >= \sum_{c \in E} w(e) $ , this means that an approximation ratio is 2

So, To prove that the  $ w(S) >= 1/2 * \sum_{c \in E} w(e) $ we just need to find the contridiction of  $ w(S) < 1/2 * \sum_{c \in E} w(e) $, For each vertex belong to V, we can simply define that c(v) is the total weight of edges connected to V which is cross the cut and W(v) is the sum of weights of all edge linked to v. So we can have
\begin{equation}
 \sum_{v \in V} c(v) = 2 * w(S) < \sum_{c \in E} w(e) = 1/2 * \sum_{v \in V} w(v)
\end{equation}
Because that we use the algorithm that which count each edge twice(from each point of the same edge).Thus,there must be at least one vertex v such that $ c(v) < 1/2 * w(v) $. If v belongs to S, so we can just simply define $ S' \ as \ S \cup (V) $, hence we can just get

\begin{equation}
w(S') >= w(S) - c(v) + (w(v) - c(v)) = w(S) + w(v) - 2 * c(v) > w(S)
\end{equation}

which can simply make the algorthm not stop at S, which will make a contradiction to the assumeption.


