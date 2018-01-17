# Notes of two papars
## Interpretable Decision Sets
[_Interpretable Decision Sets: A Joint Framework for Description and Prediction_](https://dl.acm.org/citation.cfm?id=2939874)

### Objective: To be precise and concise
* The 'Coverability' of Decision set _R_
* Less overlap of rules in _R_
* High Precision
* Small size of _R_, short length of _R_

**PS**: I found the bases of this thought are similar to _C4.5_ algorithm, in which the decision tree which tries to maximize the accuracy of division (Information Gain: like information entropy) and control the size of the tree (Intrinsic Value: donotes the number of attributes).

### Optimization
Aim to find an R to maximize a non-monotonous and submodular function.

1. First use frequent itemset mining to extract itemsets _S_
2. Then use Smooth Local Search (SLS) to find a sub-optimal _R_ (which is gauanteed to derive 2/5 optimal solution).

**PS**: Like the greedy algorithm: take the element _x_ when it can enlarge the loss function; get rid of _x_ when shrink the loss function. But SLS introduces the threshold. Only if _x_ pass that threshold we absorb/eliminate the _x_.

### Evaluation
* Accuracy： AUC and F1
* Interpretability: function of Overlap, Cover, Length, Number of Rules, Classes(?)
* Ablation Studies. (which should be taken into consideration in following experiments!!)

### Lovable Parts:
* This area is brand new to me. At first sight I thought this work is trivial; but when I dug into this work, I found the differences between Decision Sets and Decision Tree in the same representation. (Simply use conjuctions V and disjuctions ^ to aviod if/else)
* The similarity of thoughts between this paper and well-known _C4.5_.
* The new optimization method: optimization in discret cases! Usually there is a differentiable function which can be solved by SGD and such.
* The systematic evaluations, which should be put stress on in future experiments.

## Network Embedding
[_Structural Deep Network Embedding_](https://dl.acm.org/citation.cfm?id=2939753)

**QUESTION**: At first I was so confused about **supervised** and **unsupervised**, and I found that Restricted Boltzmann Machine (RBM) and Deep Belief Network (DBN) turns out to be unsupervised. Luckily I got some explanation on the Internet and kinda understand why they are so. Still need exploration. 

 (I find I need to add **LaTeX** in markdown document)

### Objective: 
* Network Embedding, which means projection of a network/graph to a low-dimension vector, and hold the relationships in the graph.
* preserve structure of the network: including the 1st-order proximity (direct relationship, existing E_{i,j} links v_i and v_j) and 2nd-order proximity (indirect relationship, which assume that vertexs enjoying the similar neighborhood tend to be similar)

**PS**: seems like clustering of points; the salient difference is the hardship to represent the ordinal relationship of vertexs in the languages or something. So we need to change the format of representation from (0, 0, 0, ..., 1, ..., 0, 0) to like (1.2, 0.3, 5.5, ...).

### Proposal:
1. Autoencoder & decoder, which preserve 2nd proximity (unsupervised)
* input : row of adjacency matrix of _G_.
* output: approach input.
* loss: square error (here non-zeros are more important since the network is sparse).

2. 1st proximity (supervised), loss: square error, applied to middle layer _K_ of encoder & decoder.
(from Laplacian Eigenmaps, which prevent similar vertexs being mapped far away)

3. Regulation: l2-norm of parameters.

Optimization: use BP method to update the parameters. (CAUTION: How to get the derivatives? Worth learning! Especially the transformation in Eq.(9), from sigma(...) to tr(Y^T (D-S) Y)

### Properties 
* Incremental learning? easy to adjust when new vertexs being add to the network.
* O(n) complexity.

### Evaluation
* precision@k and MAP: **VERY IMPORTANT INDICATORS**
* micro-F1 and macro-F1

**QUESTION**: seem not to show the power of the 2nd order.. Need reading again.

### lovable parts
* A sip of NLP or beyond NLP. And a lot of well-known algorithms and great thoughts in this field. A new area!
* (Realize the importance of Discret Mathematics...)







