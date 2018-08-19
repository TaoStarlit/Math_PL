|what|you|better|attention|
|--|--|--|--|

## eigenVector and eigenvalue:
|what|you|better|attention|
|--|--|--|--|
|eigenvactor, transformation|the vector that ..; transform XX;only has xx change|an ~ of a ~ is a non-zero vector that changes by only a scalar factor when that ~ is applied on in|changes by only xx|



definition: In liear Algebra, an eigenvector of a linear transformation is non-zero vector that changes by only a scalar factor when that transformation is applied to it. (for a linear transform A, the vector that only has scalar change is the eigenvector of this transform, the eignensalar is the changed sacalar.)

## the 4 special matrix
#### 1. unit matrix: $\left(\begin{array}{cc}1&0\\ 0&1 \end{array}\right)$ 

all the the vector are eigenvector

$det(A-\lambda I)=det\left(\begin{array}{cc}1-\lambda&0\\ 0&1-\lambda \end{array}\right)=(\lambda-1)^2$, then $\lambda=1$ , they are multiple roots

eigenvector:
$\left(\begin{array}{cc}1-\lambda&0\\ 0&1-\lambda \end{array}\right)x=0$, when $\lambda=1$, $0 x = 0$, when  x can be any vector

#### 2. exchange matrix: $\left(\begin{array}{cc}0&1\\ 1&0 \end{array}\right)$  (anti-diagonal matrix)

exchange the x1 x2, the  anti-diagnoal vector is unchanged, so the eigen vector is $(\sqrt 2, \sqrt 2)^T$

Q: are the eigenvalues are multiple root?  only the anti-diagnoal vector?


$det(A-\lambda I)=det\left(\begin{array}{cc}0-\lambda&1\\ 1&0-\lambda \end{array}\right)=\lambda^2-1$, then $\lambda=1$  and $\lambda=-1$

eigenvector:
$\left(\begin{array}{cc}0-\lambda&1\\ 1&0-\lambda \end{array}\right)x=0$, when $\lambda=1$ $x_1=x_2$, when $\lambda=-1$, $x_1=-x_2$, so $v_{\lambda=1}=(\sqrt2,\sqrt2)^T$, $v_{\lambda=2}=(\sqrt2,-\sqrt2)^T$

A:not multiple root; No, as the diagonal is also eigenvecotor

#### 3. typical Stretch matrix: $\left(\begin{array}{cc}2&1\\ 1&2 \end{array}\right)$

Q: do I have to denote the vector as $(\sqrt2, \sqrt2)^T$, but it can not be $(1, 1)^T$

$det(A-\lambda I)=det\left(\begin{array}{cc}2-\lambda&1\\ 1&2-\lambda \end{array}\right)=(2-\lambda)^2-1=\lambda^2-4\lambda+3$, then $\lambda=3$  and $\lambda=1$

eigenvector:
$\left(\begin{array}{cc}2-\lambda&1\\ 1&2-\lambda \end{array}\right)x=0$, when $\lambda=3$ $x_1=x_2$, when $\lambda=1$, $x_1=-x_2$, so $v_{\lambda=3}=(1,1)^T$, $v_{\lambda=2}=(1,-1)^T$

A: don't have to, because $(\sqrt2, \sqrt2)^T$ and $(1,1)^T$ are in the same direction


![alt text][2112]

#### 3. *typical Stretch matrix: $\left(\begin{array}{cc}1&2\\ 2&1 \end{array}\right)$

Q: what is the different between 3

$det(A-\lambda I)=det\left(\begin{array}{cc}1-\lambda&2\\ 2&1-\lambda \end{array}\right)=(1-\lambda)^2-4=\lambda^2-2\lambda-3=(\lambda-3)(\lambda+1)$, then $\lambda=3$  and $\lambda=-1$

eigenvector:
$\left(\begin{array}{cc}1-\lambda&2\\ 2&1-\lambda \end{array}\right)x=0$, when $\lambda=3$ $x_1=x_2$, when $\lambda=-1$, $x_1=-x_2$, so $v_{\lambda=3}=(1,1)^T$, $v_{\lambda=-1}=(1,-1)^T$

A: the diagonal vector is in opposite direction.


#### 4. shear mapping matrix: $\left(\begin{array}{cc}1&m\\ 0&1 \end{array}\right)$ $m=0.5$

Q: 与乔丹典型式有几毛钱的关系？

$det(A-\lambda I)=det\left(\begin{array}{cc}1-\lambda&0.5\\ 0&1-\lambda \end{array}\right)=(1-\lambda)^2$, then $\lambda=1$ multiple roots

eigenvector:
$\left(\begin{array}{cc}1-\lambda&0.5\\ 0&1-\lambda \end{array}\right)x=0$, when $\lambda=1$, $0.5 x_2=0$, so $x=(c,0)^T$, the vector is all the horizontal line.

A: 什么三角阵，对角阵。 确实是 重根，确实A是三角阵，（下面一片都是0）

![alt text][shearmapping]

[2112]:img\Eigenvectorsof2112.png "2112"
[shearmapping]:img\shearmapping.png "shearmapping"





#### 先不管旋转 0 1 -1 0， 先搞定错切和乔丹典型式 Jordan标准型

https://www.zhihu.com/question/30668401
从相对抽象落实到具体(向量空间→线性相关/无关→基与维度→极大线性无关→线性变换及其矩阵表示→同构、秩零定理→行列式→方程组理论→特征值、特征向量→内积空间理论→乔丹标准型…

http://find.lib.uts.edu.au/search.do?Ntt=David+C.+Lay&N=0

##### 1 重根 与 基础解系
https://baike.baidu.com/item/%E7%9F%A9%E9%98%B5%E7%89%B9%E5%BE%81%E5%80%BC

得同解方程组x1-x2+x3=0，解为x1=x2-x3(x2,x3为自由未知量)。分别令自由未知量 (x2,x3)=(0,1) (x2,x3)=(1,0),得到了基础解系（满足那个方程组的） ξ1=(1,0,1) ξ2=(-1,1,0) 

所以A的对应于特征值λ1=λ2=-2的全部特征向量为x=k1ξ1+k2ξ2(k1,k2不全为零)，可见，特征值λ=-2的特征向量空间是二维的。注意，特征值在重根时，特征向量**空间的维数**是特征根的重数。 **这里是二重根，所以需要k1 k2**
令自由未知量x3=2得基础解系ξ3  ，所以A的对于特征值λ3=4得全部特征向量为x= k3ξ3。 **单根，所以一个k3 就够了**

##### 1 用基础解系，来表示上面的向量空间
对于 exchange matrix $ξ1=(1,1)^T$ and  $ξ2=(1,-1)^T$, x=k1ξ1, x=k2ξ2
对于 unit matrix： 0x1+0x2=0 $ξ1=(1,0)^T$ and  $ξ2=(0,1)^T$, x=k1ξ1+k2ξ2(k1,k2不全为零)
对于 shear mapping 0.5x2=0, ??

遗留问题： 特征空间维度就是重根的重数