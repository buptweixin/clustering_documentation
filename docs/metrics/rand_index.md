# 什么是 rand index
> The Rand index or Rand measure (named after William M. Rand) in statistics, and in particular in data clustering, is a measure of the similarity between two data clusterings. --wikipedia

# rand index 的定义

两种算法分别对数据集 $S$ 聚类， 得到两个聚类结果 $X$ 和 $Y$, $S$ 中取一个 pair 它在 $X$ 和 $Y$ 中聚类结果总共有 4 种可能：

1. a: 满足 $X$ 和 $Y$ 中都被聚到一组内的 pair 数;
2. b: 满足 $X$ 和 $Y$ 中都没有被聚到一组的 pair 数；
3. c: 在 $X$ 中被聚到一组但是在 $Y$ 中没有被聚到一组的 pair 数;
3. d: 在 $Y$ 中被聚到一组但是在 $X$ 中没有被聚到一组的 pair 数;

rand index $R$ 的定义如下：

$$
R=\frac{a+b}{a+b+c+d}=\frac{a+b}{\left(\begin{array}{l}n \\ 2\end{array}\right)}
$$

其中 $\left(\begin{array}{l}n \\ 2\end{array}\right)$ 表示从 $S$ 中任取两个数据组成 pair 的可能种数。

# rand index 的性质

rand index 取值范围为 [0, 1], 0 表示两个聚类结果完全不相似， 1 表示两个聚类结果完全一致。

# Adjusted Rand index

ari 的目的在于使随机聚类分数尽可能低

$$
A R I=\frac{\sum_{i j}\left(\begin{array}{c}n_{i j} \\ 2\end{array}\right)-\left[\sum_{i}\left(\begin{array}{l}a_{i} \\ 2\end{array}\right) \sum_{j}\left(\begin{array}{l}b_{j} \\ 2\end{array}\right)\right] /\left(\begin{array}{l}n \\ 2\end{array}\right)}{\frac{1}{2}\left[\sum_{i}\left(\begin{array}{l}a_{i} \\ 2\end{array}\right)+\sum_{j}\left(\begin{array}{l}b_{j} \\ 2\end{array}\right)\right]-\left[\sum_{i}\left(\begin{array}{l}a_{i} \\ 2\end{array}\right) \sum_{j}\left(\begin{array}{l}b_{j} \\ 2\end{array}\right)\right] /\left(\begin{array}{l}n \\ 2\end{array}\right)}
$$

或

$$
\text {score}=\frac{x-E(x)}{\max (x)-E(x)}
$$

