9

a)A subproblem is a new instance of the Rudrata Path on a subgraph the origin graph,the starting point is one of the vertex v belongs V. This subproblem can help use to solve problem from each verteices. 

b)choose can be implement by picking the subproblem defined on the smaller graph. This is reasonable as smaller graphs will be evaluated faster. Moreover, this will reduce space complexity of the algorithm
as a single active path must be kept in the tree of possible Rudrata paths.

c)To expend a subproblem , we just difined as Rudrate Path starting at a subgraph of origiin graph and the divide it into subproblem $ P_1 $to $ P_n $, and the $ i_th $ iteration is the subgraph of origin graph