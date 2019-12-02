# 极大似然估计
## 贝叶斯决策

$$ P(w|x)=\frac{P(x|w)P(w)}{P(x)} $$

$P(w)$：先验概率 Priori probability，代表每种类别分布的概率
$P(x|w)$：类条件概率 ，在某种类别前提下某事的概率
$P(w|x)$：后验概率

**问题引出**

数据：有限数目的样本数据。$P(w),P(x|w)$都未知，需要估计，$P(w)$比较好估计，估计类条件概率非常难。

办法：把估计概率密度$P(x|w)$转化为参数估计，概率密度函数选取非常重要。

前提：1、训练样本分布可代表所有；2、独立通分布；3、有充分的训练样本

## 极大似然

目的：利用已知样本，反推最可能导致这一结果的参数值

样本：$D=\{x_1,x_2,...,x_n\}$

似然函数：
$$l(\theta)=P(D|\theta)=P(x_1,x_2,...x_n|\theta)=\prod_{i=1}^{N}P(x_i|\theta)$$

P()为假设的概率分布函数。

如$\hat \theta$使似然函数最大，则其就是极大似然估计量


## 求解极大似然函数
$$\hat\theta=\underset{\theta}{\operatorname{argmax}\prod_{i=1}^{N}P(x_i|\theta)}$$

对数似然
$$H(\theta)=\ln{l(\theta)}$$
$$\hat\theta=\underset{\theta}{\operatorname{argmax}\sum_{i=1}^{N}\ln{P(x_i|\theta)}}$$

一个$\theta$：
$$\frac{dl(\theta)}{d\theta}=0$$

$\theta$向量：

$$\nabla_\theta H(\theta)=0$$

## 似然与概率

概率：在特定环境下某件事情发生的可能性 $P(x|\theta)$
似然：在确定的结果下推测这个结果可能的环境 $L(\theta|x)$

## 对数化似然函数
因为在MLE中经常对于多个独立时间求：

$$L=\prod_{i=1}^{N} P_i$$

对多项式的乘积求导复杂，而对多项式和的求导简单，且对数函数不改变原函数的单调性和极值位置。