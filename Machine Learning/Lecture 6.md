# Cluster Analysis

What it is?
Finding a group of objects that are similar to each other and indifferent of another objects of another group.

Types of clustering?
- Partitional Clustering
- Hierarchical Clustering

Types of clusters?
- Well-separated clusters
- Center-based clusters
- Contiguous clusters
- Density-based clusters
- Shared Property or Conceptual clusters
- Described by an Objective Function clusters

Clustering algorithms?
- k-means and its variants
- Hierarchical clustering
- Density-based clustering

Evaluating k-means clusters with Sum of Squared Error (SSE)

$$
SSE=\sum_{i=1}^{k} \sum_{x=C}^{}dist^2(m_i,x)
$$

Limitations of k-means?
- Differing size
- Differing Density
- Non-globular shapes

Solution is to use many clusters.

The hierarchical clustering produces a set of nested clusters organized as a hierarchical tree.

Two main types of hierarchical clustering:
- Agglomerative
- Divisive

