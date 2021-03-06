
DES加密过程
======
* 64位密钥经子密钥产生算法产生出16个子密钥：K<sub>1</sub>，K<sub>2</sub>，···，K<sub>16</sub>，分别供第一次，第二次，······，第十六次加密迭代使用。<br>
* 64位明文首先经过初始置换IP(Initial Permutation)，将数据打乱重新排列并分成左右两半。左边32位构成L<sub>0</sub>，右边32位构成R<sub>0</sub><br>
* 由加密函数*f*实现子密钥K<sub>1</sub>对R<sub>0</sub>的加密，结果为32位的数据组*f*(R<sub>0</sub>,K<sub>1</sub>)。*f*(R<sub>0</sub>,K<sub>1</sub>)再与L<sub>0</sub>模2相加，又得到一个32位的数据组，将其作为第二次加密迭代的R<sub>1</sub><br>，以R<sub>0</sub>作为第二次加密迭代的L<sub>1</sub>。至此，第一次加密迭代结束。<br>
* 第二次加密迭代至第十六次加密迭代分别用子密钥K<sub>2</sub>，······，K<sub>16</sub>进行，其过程与第一次加密迭代相同。<br>
* 第十六次加密迭代结束后，产生一个64位的数据组。以其左边32位作为R<sub>16</sub>，以其右边32位作为L<sub>16</sub>，两者合并再经过逆初始置换IP<sup>-1</sup>，将数据重新排列，便得到64位密文。至此加密过程全部结束。<br>

DES的整体结构
-----
![](http://pic002.cnblogs.com/images/2012/42533/2012062320501672.jpg)
