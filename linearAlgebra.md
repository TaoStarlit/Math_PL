|what|you|better|attention|
|--|--|--|--|

向量空间→线性相关/无关→基与维度→极大线性无关→线性变换及其矩阵表示→同构、秩零定理→行列式→方程组理论→特征值、特征向量→内积空间理论→乔丹标准型

（同构没找到什么解释，但是相似的却有）



## 20180820
|相似变换矩阵|正交矩阵|酉矩阵|待续|
|--|--|--|--|
|$B=P^{-1}AP$|$M=W\Sigma V^T$|$M=U\Sigma V^*$||
|相似变换|正交变换|降维|待续|
|$B=P^{-1}AP$|$B=WM$|$Y=W_L^T$X||
|如果B是**对角矩阵**，则A是**可对角化矩阵**，P是**对角化矩阵**|对M在实数域进行奇异分解，变到另外的坐标，不改变长度，如置换|对X在复数域进行奇异值分解，共轭转置在实数域，就是转置||
相似矩阵，矩阵同构，对角化- 与 特征矩阵（无直接关系，当长得和-长得和PCA很像。。逆和转置联系在一起，又和正交矩阵orthogonal matrix联系了）|
|求B|求$W$|求$W_L$|。|
|怎么|W左奇异矩阵就是$XX^T$的特征矩阵|左奇异矩阵取前面根据奇异值大小取前面的L个列向量||

##### 相似矩阵 + 矩阵对角化 与 特征向量：
https://zh.wikipedia.org/wiki/%E7%9B%B8%E4%BC%BC%E7%9F%A9%E9%99%A3

相似关系是一种等价关系。 A和B之间相似的 当且仅当 存在 可逆矩阵P，使得 $P^{-1}AP=B$, ($A=PBP^{-1}$)

P 称为A和B之间的相似变换矩阵。
如果P还是正交矩阵的话（逆也是装置那么就是奇异值分解了）

两者的秩相等。
两者的行列式值相等。
两者的迹数相等。
两者拥有同样的特征值，尽管相应的特征向量一般不同。
两者拥有同样的特征多项式characteristic polynomial: $p_A(t):=det(A-tI) \in k[t]$。
两者拥有同样的初等因子。


##### 矩阵对角化 与 特征向量
https://ccjou.wordpress.com/2010/05/13/%E5%8F%AF%E5%B0%8D%E8%A7%92%E5%8C%96%E7%9F%A9%E9%99%A3%E8%88%87%E7%BC%BA%E9%99%B7%E7%9F%A9%E9%99%A3%E7%9A%84%E5%88%A4%E5%AE%9A/

A矩阵，存在可逆S矩阵，使得$D=S^{-1}AS$是对角矩阵,则称A是diagonalizable matrix可对角化矩阵

若A是nxn阶，有n个线性独立的特征向量，《=》 S是可逆，A可分解为$A=S\Sigma S{-1}$

即：若不具备n个独立的特征向量，则S是不可逆的，A无法对角化

Q: shear mapping 可逆吗？ （它没有n个线性独立的特征向量）
A:可逆充分条件，满秩，行列式不等于0，则shear mapping是可逆。 但是不代表，一定能找到个S可逆的。 可对角化比可逆的条件要苛刻

特征值两两相异，则这个是可以对角化（有相互独立的特征向量）

特征值有重根，有时可对角化有时不能（n个特征向量，小于n个独立的特征向量）
如 unit matrix VS shear matrix 多个0.5而已

如$\left(\begin{array}{ccc}2&1&1\\ 0&1&-1\\ 0&0&2 \end{array}\right)$ VS $\left(\begin{array}{ccc}2&1&1\\ 0&1&1\\ 0&0&2 \end{array}\right)$ -1变1而已

如果矩阵的某个特征值的几何重数（特征值的特征空间eigen space的维度$dimN(A-\lambda I)$，小于代数重数（特征值重根的重数），则这个矩阵为缺陷矩阵(不可对角化矩阵).

$A-\lambda I$ 的零空间必定包含非零向量,说明是个不可逆矩阵 -- 检查 $det(A-\lambda I)=0$, 确实不可逆。

N(A),矩阵A的零空间nullspace, 是线性方程组Ax=0的解空间，也就是核空间。所以 $A-\lambda I$ 的零空间就是 特征值为$\lambda$时，特征向量（A-\lambda I=0的解）张成的空间，又叫特征空间(eigenspace)

解空间如何判断: 线性空间的任一组基底都称为这个齐次线性方程组的基础解系。求齐次线下方程组的解可归结为求它的基础解系，通常可对其系数矩阵用初等行变换求出。 -- 就是求一组基础解系了。

秩零定理：齐次线性方程组的解空间的维数 = n - r(A). 单位矩阵的，确实r(I-I)=0, 则n=2;  shear mapping的，r(A-I)=1,则n=1。所以shear mapping的重根的几何重数(geometric multiplicity)只有1，代数重数(algebraic multiplicity)却是2，这是缺陷矩阵(defective matrix)。


碰到了秩rank，那么把痕track也搞定吧！ 就是对角线上的值的相加，所以单位矩阵和shear mapping的迹tr是相等的。
性质，相似矩阵的$tr(A)=tr(P^{-1}BP)=tr(B)$

#### 正交矩阵： 
每个元素均为实数，每个列向量都为单位向量，使得矩阵的转置就是矩阵的逆。 
1. $det(Q)^2=det(Q)det(Q^T)=det(QQ^T)=det(QQ^{-1})=det(I)=1$ 所以det(Q)必定为1 和 -1
2. 例子: 恒等变化（单位矩阵）； 置换坐标（exchange matrix置换矩阵)； 旋转
$\left(\begin{array}{cc}\cos\theta&-\sin\theta\\ \sin\theta&\cos\theta \end{array}\right)$, （theta=0就是单位矩阵）； 
反射
$\left(\begin{array}{cc}\cos\theta&\sin\theta\\ \sin\theta&-\cos\theta \end{array}\right)$, （当theta=90度时-旋转90度之后再镜面一下，反射矩阵就是置换矩阵）（反射是它自己的逆，这蕴涵了反射矩阵是对称的（等于它的转置矩阵）也是正交的。）； 


##### 主成分分析
PCA的数学定义是：一个正交化线性变换，把数据变换到一个新的坐标系统中，使得这一数据的任何投影的第一大方差在第一个坐标（称为第一主成分）上，第二大方差在第二个坐标（第二主成分）上，依次类推。

##### 奇异值分解：
X mxn: m行数是属性个数；列数是样本个数。$X^T$ 是去取平均值的数据。 $XX^T$的本征矢量矩阵W mxm； $\Sigma$是mxn非负矩形对角阵mxn；$X^TX$的本征矢量矩阵V nxn； $X=W\Sigma V^T$ 

降维 $Y=W_L^TX$ lxm  mxn --> lxn   W里面每个列向量就是基里面的向量，只取前面l个大的。 mxl，然后装置一下，变成lxm

###### 奇异值和特征值的联系：
V的列向量（右奇异向量）是 $M^*M$ 的特征向量。
U的列向量（左奇异向量）是 $MM^*$ 的特征向量。
$\Sigma$ 的非零对角元（非零奇异值）是$M^{*}M$ $M^{*}M$ 或者 $MM^{*}$ 的非零特征值的**平方根**。


##### 奇异值分解在某些方面与 对称矩阵 或 厄米矩阵基于特征向量的对角化 类似。
假设M是一个mxn阶矩阵，其中的元素全部属于域K，也就是实数域或者复数域。 存在一个分解使得:

$M=U\Sigma V^*$

其中U是mxm阶酉矩阵（正交矩阵向实数域推广），Sigma是 mxn阶 非负 实数对角矩阵； 而$V^*$，即V的共轭转置，是nxn阶酉矩阵(如果是正交矩阵，转置也就是逆矩阵，如，置换矩阵的平方，就是单位矩阵。在PCA里面就是转置:

$X=W\Sigma V^T$, 没必要共轭)，Sigma对角线上的元素$\Sigma_i$也就是M的奇异值。



##### 奇异向量，分为左奇异向量m，右奇异向量n, 因为X或者M和$\Sigma$是mxn矩阵，

### jordan 标准型， jordan块，以shear mapping 与 unit matrix做对比

- 缺陷矩阵 和 秩 无关，因为 shear mapping 和 unit matrix 一样是满秩的。



## 20180819
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
隔天回答20180820：当矩阵不是缺陷的时候，才成立，如shear mapping matrix是缺陷的，所以二重根，特征向量空间的维度确实1； 而unit matrix是满足条件的，所以特征向量空间就是2了