### Shuffle dateset 打乱数据集

新建0-149的乱序list，在排序的同时，打乱X和Y，保证X和Y始终对应

### Distance Matrix 求得距离矩阵

使用欧式距离

### Normalize 构造归一化函数

对距离归一化

### Gaussian Kernal --> Similarity Matrix  由高斯核求得相似度矩阵

根据相似度画图，相似度>0.9时，两点之间连线

### Adjacency Matrix and with weight 求出邻接矩阵和带权邻接矩阵

相似度>0.9，邻接矩阵置为1，带权邻接矩阵置为两点的相似度，其余置0

### Degree Matrix 求度矩阵

根据相似度>0.9，大于的时候主对角线上对应元素+1

### Laplacian Matrices 求拉普拉斯矩阵

`L = degree_matrix - weight_adjacency_matrix`

并求得特征值`eigenValue`和特征向量`eigenVector`

将每个特征值对应的150个特征向量排序，取最小的50个组成新的特征向量`new_eigenVector`

### Clustering with K-means 利用K均值聚类

首先生成初始质心，在根据距离矩阵分类，反复重置质心，直到稳定

聚成3类

得到每个样本对应的结果`clustAssing`

### Arrange and Draw 整理数据并画图

根据`clustAssing`将结果放入3个list，根据list中的元素画图

最后求得正确率`acc`



### Conclusion

正确率最高一次为96.7%，不稳定

首先是所对应的标签需要多次尝试，因为0，1，2没有固定标准

主要是K-means受初始点的影响较大，初始点选取的合适，正确率就会很高