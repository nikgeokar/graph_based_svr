# Graph-Based SVR
This repository contains a machine learning project that predicts node values in a graph using graph-based kernels and support vector machine (SVM) regression. The project includes experiments with two datasets and utilizes the Propagation algorithm and a multi-output SVM regressor.

This project presents a methodology using graph-based kernels and the support vector machine (SVM) technique to predict node values in a graph. We utilize the Propagation algorithm for kernel computation and a multi-output SVM regressor to generate node labels. We conduct experiments with two datasets: Thessaloniki's controlled parking system violation data to predict parking violation rates of sectors, and the chickenpox dataset to predict disease outbreaks. We also conduct additional experiments using common SVR kernel methods and the K-Nearest Neighbor algorithm for both datasets.

We use the graph kernels. They are based on the idea of propagating label information between nodes of the graph, based on the graph structure. A graph is considered to have attributes on nodes, where in the case of labels they correspond to One-Hot-Vectors of the full dictionary of labels. In general, the algorithm applies kernel computation between all input graph com- binations, thus it accepts as input a list of graphs information and outputs and an adjacency matrix with shape (𝑁𝑔𝑟𝑎𝑝h𝑠,𝑁𝑔𝑟𝑎𝑝h𝑠). We apply the above technique by using the PropagationAttr al- gorithm from Grakel library 1, while we change the final kernel computation function. In Fig. 1 we describe at a high level the application of PropagationAttr process between 2 graphs.

<div align="center">
  <img src="https://github.com/nikgeokar/graph_based_svr/files/11302050/conv_kernel.pdf" alt="1" width="500"/>
</div>


At this point we would like to focus on the kernel computation function 𝑓 (𝑥,𝑦). We replace the default function by applying a convolution-based approach. Where x, and y are the vectors produced from LSH for each graph. We treated the vectors as signals and calculated the convolution between them. Then we calculated the convolution product, which is only given for points where the signals overlap completely.

To access further details and information, please refer to the report file located within this repository (report.pdf).
