# File: promql/quantile.go

在Prometheus项目中，promql/quantile.go文件的作用是实现PromQL语言中的quantile函数，用于计算数据的分位数。

excludedLabels是一个用于过滤标签的字符串列表。它指定了在计算分位数时需要忽略的标签名称。

bucket是一个表示数据桶的结构体，包含了bucket的上限值以及落入该桶的样本数量。

buckets是bucket的切片，用于存储所有的bucket。

metricWithBuckets是一个表示带有bucket的指标的结构体，包含了一个指标以及其对应的bucket切片。

Len、Swap和Less是bucket切片在排序时使用的方法。

bucketQuantile用于计算quantile函数的结果，给定一个指标及其对应的bucket，根据分位数计算出对应的值。

histogramQuantile用于计算直方图类型数据的分位数。

histogramFraction用于计算获取直方图中各个桶的样本累积百分比。

coalesceBuckets用于合并相邻的相同样本数量的桶。

ensureMonotonic用于确保数据的单调性，即检查并修正桶的数量和值使其单调递增。

quantile是最终提供给PromQL解释器调用的函数，它会根据用户给定的分位数和指标数据返回相应的结果。

