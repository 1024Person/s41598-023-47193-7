# Enhancing the direct charging performance of an open quantum battery by adjusting its velocity  

## 模型

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403170951055.png)

体系由四部分组成，充电器A，电池B，外界耦合的腔$R_A,R_B$。然后，还有两种相互作用，也就是充电器和电池的相互作用，还有就是充电器和电池与外界环境之间的相互作用。然后，电池和充电器在腔内能够沿着$z$轴进行移动（中间右侧的坐标系表明了$z$轴的方向），还有就是电池和充电器的本质是一个二能级系统（量子比特），外界的腔就是一个谐振子模型，电池和充电器的移动，表现在哈密顿量上就是电池和充电器和外界的耦合强度不同。就是在不同的位置，耦合强度不同。

体系哈密顿量
$$
H_{0} = H_A+H_B+H_{R_A}+H_{R_B}=\sum_{j=A,B}\left(\frac{\omega_0}{2}\sigma_z^j+\sum_{k}\omega_k^ja_{k}^{j\dagger}a^j_k\right)\\
H_{int}=H_{A-B}+H_{A-R_A}+H_{B-R_B}=D\left(\sigma_+^A\sigma_-^B+\sigma_-^A\sigma_+^B\right)+\sum_{j=A,B}\sum_kf_k^j\left(z\right)\left(\bold g_k^j\sigma^j_+a_k^j+H.c.\right)
$$
其中的$f$就是和$z=vt$有关的一项，然后这个函数就是对耦合强度的调制，因为不同的位置，耦合强度不同，代表着对耦合强度的调制。

在相互作用绘景下

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403170947942.png)

其中，$f_k^j(z=vt) = \sin\left[\omega_k^j\left(\beta t-\Gamma\right)\right]$，$\Gamma = L/c$,$L$是光腔的尺寸。而$\beta=v/c$，$f_k^j(z)$显含时间

总体期望值算符

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403170949524.png)

这个总体期望值算符，由四部分组成，产生湮灭算符就是外界环境$R_A,R_B$这两个腔的算符，$\sigma_z$就是电池和充电器的哈密顿量。同时这个算符和哈密顿量时对易的

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403170950893.png)

整个希尔伯特空间可以进行分解成量子比特希尔伯特空间和腔希尔伯特空间
$$
\mathcal{H}=\mathcal{H}_q\otimes\mathcal{H}_R
$$
空间的基矢就是
$$
\left\{|i_A,j_B\rangle\otimes|n_1,n_2,\dots,n_k,\dots\rangle_{R_A}|^\infty_{n_1,n_2,\dots=0}\otimes|m_1,m_2,\dots,m_k,\dots\rangle_{R_B}|_{m_1,m_2,\dots=0}^\infty\right\}\left(i,j=e,g\right)
$$
第一个代表着电池和充电器空间，然后后面的$n_k$中，$k$代表腔的模式，$n$代表能级，后面的$|_{n_1,n_2,\dots=0}^\infty$代表着$n_1,n_2,\dots$的取值可以从0到$\infty$。

同样的，我们也可以将希尔伯特空间，按照体系的能级进行分解，也就是
$$
\mathcal{H}=\oplus_{n=0}^\infty \mathcal{H}_n
$$
其中，下标$n$代表着第几个激发态，下面全在第一激发态中的讨论，第一激发态中的态矢量如下所示

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171015746.png)

注意这里面就只有一个激发态（e或者1），其中k代表着模式，这个$|_{k=0}^\infty$代表着$k$的取值，$k$可以从0取到$\infty$，并不是求和。

## $\mathcal{H}_1$空间

初态取
$$
|\Psi\left(0\right)\rangle = \left[c_1\left(0\right)|e_A,g_B\rangle+c_2\left(0\right)|g_A,e_B\rangle\right]\otimes|0\rangle_{R_A}|0\rangle_{R_B}
$$
在第一个希尔伯特空间中$\mathcal{H}_1$进行演化，那么每个时刻的态就可以用希尔伯特空间的基矢进行展开

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171021905.png)

其中的展开系数$c_1\left(t\right),c_2\left(t\right),d_k\left(t\right),d_k'\left(t\right)$满足归一化

​	![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171022123.png)

每个子系统约化密度矩阵（这个除了自己，要约化掉三个空间）

![image-20240317102333430](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171023467.png)

我们把体系的态带入到薛定谔方程中$H_{IP}|\Psi\left(t\right)\rangle=i\frac{d}{dt}|\Psi\left(t\right)\rangle$，然后就能得到$c_1(t),c_2(t),d_k(t),d_k'(t)$的微分方程[^1]（注意下面的第一个和第二个指数因子上少了一个$t$）

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171142804.png)

注意我们选取的初态中$d_k(0)=0,d_k'(0)=0$，因此，我们可以先将下面两个微分方程先求解出来，观察方程可以发现，其实$d_k(t),d_k'(t)$分别可以用$c_1(t),c_2(t)$进行表示。

最终，$c_1(t),c_2(t)$的微分方程如下所示（**感觉下面的积分和卷积很像啊**）
$$
\begin{aligned}
\dot{c}_1(t)&=-iDc_2(t)-\int^t_0F_A(t-t')c_1(t')dt'\\
\dot{c}_2(t)&=-iDc_1(t)-\int_0^tF_B(t-t')c_2(t')dt'
\end{aligned}
$$
其中，$F_A,F_B$的表达式如下所示[^1]

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171523557.png)

> 论文里说这两个F是，外界环境A和外界环境B的相关函数，但是搞不懂，相关函数到底是什么？有什么物理意义？或者说有什么作用？原文如下：
>
> ![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171526256.png)
>
> 搞不懂，这里的memory correlation function 是什么意思

为了简单起见，我们取$F_A(t-t')=F_B(t-t')=F(t-t')$，同时取极限情况下，即认为$\omega_k$是连续的，也就是$\omega$，那么，$F(t-t')$的表达式如下所示

![](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171530416.png)

其中，$J(\omega)$**是腔场的密度谱**（这里非常的不理解！！！）$J(\omega)$的表达式如下所示

![image-20240317153540805](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171535979.png)

其中，$\lambda$定义了耦合的谱宽度（不理解），这个和“memory time”$\tau_E$相联系，也就是$\tau_E=\lambda^{-1}$，然后$\gamma$是量子比特与环境的耦合强度这个和"relaxation time "$\tau_R$相联系，$\tau_r\approx \gamma^{-1}$，$\Delta$代表频率$\omega_0$和腔场的中心的失谐（这个失谐是在qubit和腔场之间的频率的失谐，因为qubit的振动频率是$\omega_0$）。还有就是，如果我们取$\frac{\gamma}{\lambda}<< 1$，也就是弱耦合情况下，体系的演化就是一个Markovian（马尔可夫过程），在这种过程中，系统的信息或者能量将会以指数的速度衰减到0。当在强耦合情况下$\frac{\gamma}{\lambda}>>1$时，体系的演化就是一个non-Markovian（非马尔可夫过程），这时候，能量或者信息将会从环境中回流到系统中。

---

下面是看不懂，也算不出来的部分，这一部分别算了，实在是算不出来

将上面的$J(w)$回代到$F(t-t')$中，并做一些计算之后，在连续极限的情况下$\Gamma\to\infty$的情况下，$F(t-t')$也就能够化简成下面的这种样子，但是其中有一点需要注意，就是在这个极限下，$\omega$没了！！！！这个很重要！！！因为这样的话就不知道腔的振荡频率了！！

![image-20240317161221832](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171612266.png)

将（17a），（17b）这两个微分方程（也就是$c_1(t),c_2(t)$满足的微分方程）的等号两边同时做拉普拉斯变化，利用拉普拉斯变换的卷积性质

![image-20240317161957762](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171619835.png)

以及微分性质[^2]

![image-20240317162058178](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171620223.png)

就能得到

![image-20240317162148120](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171621272.png)

其中$F(s)$的推导，如下所示[^3]

![image-20240317164213781](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171642088.png)

其中的$\lambda_1$就是$\bar{\lambda}$，论文中的表达式是下面这样

![image-20240317164344187](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171643290.png)

所以我们就有了$c_1(s),c_2(s)$的表达式，如下所示（这个没有什么技术含量，就是移项整理而已，就不再写了）

![image-20240317164955279](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171649348.png)

进一步利用部分分解的方法（就是将上面的公式进行裂项整理），可得

![image-20240317165151644](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171651698.png)

再利用拉普拉斯逆变换可得，

![image-20240317170253003](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171702089.png)

但是这个里面的$\mathcal{M}_{\pm}$实在是太难计算了，电脑程序都算不出来

![image-20240317170342654](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171703816.png)

上面的那个三次根能计算出来吗？应该可以吧。

思路就是将这个$\mathcal{M}_{\pm}$回代到上面的$c_1(t),c_2(t)$中，就能得到电池中展开系数的表达式了，进而就能知道电池的能量了

![image-20240317170637163](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403171706224.png)

然后就是计算电池的可提取功
$$
\mathcal{W}=\Tr\left\{\rho_BH_B\right\}-\min_U\Tr\left\{U\rho_BU^\dagger H_B \right\}
$$
进一步化简就是
$$
\mathcal{W}=\sum_{ij}r_j\epsilon_i\left(\left|\langle r_j|\epsilon_i\rangle\right|^2-\delta_{ij}\right)
$$

> 注意上面的公式，直接看有点看不懂，但是，带入一个具体的例子就能明白了，用二能级来举例就明白了
> $$
> \begin{aligned}
> \mathcal{W}&=\sum_{i,j=0}^{1}r_j\epsilon_i\left(\left|\langle r_j|\epsilon_i\rangle\right|^2-\delta_{ij}\right)\\
> &=r_0\epsilon_0\left(|\langle r_0|\epsilon_0\rangle|^2-1\right)+r_0\epsilon_1|\langle r_0|\epsilon_1\rangle|^2+r_1\epsilon_0|\langle r_1|\epsilon_0\rangle|^2+r_1\epsilon_1\left(|\langle r_1|\epsilon_1\rangle|^2-1\right)\\
> &=\left(r_0\epsilon_1+r_1\epsilon_0\right)-\left(r_0\epsilon_0+r_1\epsilon_1\right)
> \end{aligned}
> $$
> 注意$|r_j\rangle,|\epsilon_i\rangle$这里两个态的主要意思将这个态与$r_j\ge r_{j+1},\epsilon_i\le \epsilon_{i+1}$相联系，就是说$|r_j\rangle$这个态是降序的态，而$|\epsilon_i\rangle$这个态是升序的态，以二能级为例，$|0\rangle$代表基态，$|1\rangle$代表激发态
> $$
> \begin{cases}
> |r_0\rangle\to|1\rangle,|r_1\rangle\to|0\rangle\\
> |\epsilon_0\rangle\to|0\rangle,|\epsilon_1\rangle\to|1\rangle
> \end{cases}
> $$
> 这两个态是可以理解了，但是就算是这两个态理解了，给的态$\rho_B$也应该是一个任意的态呀，咋它的本征值咋还按照顺序排列上了？

把
$$
\begin{aligned}
\rho_B(t)&=\left|c_2(t)\right|^2|e_B\rangle\langle e_B|+\left(1-|c_2(t)|^2\right)|g_B\rangle\langle g_B|\\
&=
\left[\begin{matrix}|c_2(t)|^2&0\\
0&1-|c_2(t)|^2
\end{matrix}\right]
\end{aligned}
$$
带入到上面中可得[^1]
$$
\mathcal{W}=\omega_0\left(2|c_2(t)|^2-1\right)\Theta\left(|c_2(t)|^2-\frac{1}{2}\right)
$$
这个解析解式已经推导出来的，确实是正确的。

## 复现代码

将这篇论文中的fig都给复现出来了[^4]，但是最后的fig6的那个退相干的，有点不合适

![image-20240318110410664](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181104210.png)

![image-20240318110441061](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181104182.png)

![image-20240318110521036](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181105142.png)

![image-20240318110551361](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181105485.png)

![image-20240318110627560](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181106715.png)

![image-20240318110703308](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181107446.png)

![image-20240318110722049](https://raw.githubusercontent.com/1024Person/pic-raw/main/img/202403181107152.png)

上面的几幅图，说明了：量子比特具有更高的运动速度，对于能量，最大可提取功，效率都有提升作用，同时对于退相干具有抑制效果。

## 扩展

这篇论文能不能和非互易的那篇文献结合一下？感觉应该有点希望！！！但是实在是太难了！！！

## 参考

[^1]:[推导过程](./推导过程.md)
[^2]:[公式墙(1)——Laplace Transform(拉普拉斯变换) - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/152647974)

[^3]:[推导.ipynb](./推导.ipynb)
[^4]:[复现代码.nb](./复现代码.nb)



