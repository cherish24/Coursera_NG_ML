###### 矩阵运算  

```
octave:33> A = [1 2; 3 4; 5 6]
A =

   1   2
   3   4
   5   6

octave:34> B = [11 12; 13 14; 15 16]
B =

   11   12
   13   14
   15   16

octave:35> C = [1 1; 2 2]
C =

   1   1
   2   2

octave:36> A * C
ans =

    5    5
   11   11
   17   17

octave:37> A .* B       % A中每一个元素与B中对应的元素相乘
ans =

   11   24
   39   56
   75   96

octave:38> A .^ 2      % 对A中每一个元素进行平方运算
ans =

    1    4
    9   16
   25   36

octave:39> V =[1; 2; 3]
V =

   1
   2
   3

octave:40> 1 ./ V       % 对V中的每个元素求其倒数
ans =

   1.00000
   0.50000
   0.33333

octave:41> log(V)       % 对V进行对数运算
ans =

   0.00000
   0.69315
   1.09861

octave:42> exp(V)        % 对V进行e的幂次方运算
ans =

    2.7183
    7.3891
   20.0855

octave:44> -V
ans =

  -1
  -2
  -3

octave:45> abs(-V)        % 对-V进行求绝对值运算
ans =

   1
   2
   3

octave:46> V + ones(length(V), 1)
ans =

   2
   3
   4

octave:53> a
a =

    1.00000   15.00000    2.00000    0.50000

octave:54> a < 3
ans =

  1  0  1  1          % a中的元素< 3为真，返回1；反之，返回0    
```   

其中，“.”表示元素位运算。            

###### 如何求转置矩阵  

```
octave:47> A
A =

   1   2
   3   4
   5   6

octave:48> A'
ans =

   1   3   5
   2   4   6
```            

###### 一些有用的函数    

```
octave:49> a = [1 15 2 0.5]         % a为向量
a =

    1.00000   15.00000    2.00000    0.50000

octave:50> [val, ind] = max (a)
val =  15                 % a中的最大值
ind =  2                  % a中的最大值所在的位置索引

octave:52> max(A)              % A每一列的最大值
ans =

   5   6

octave:55> find(a<3)
ans =

   1   3   4      % 返回a中< 3的元素的位置索引

octave:57> A = magic(3)
A =

   8   1   6
   3   5   7
   4   9   2

octave:58> [r, c] = find(A >= 7)
r =                  % 返回A中>= 7的元素所在的行数

   1
   3
   2

c =                  % 返回A中>= 7的元素所在的列数

   1
   2
   3

octave:59> sum(a)      % 将a中所有的元素加起来求和
ans =  18.500

octave:60> prod(a)     % 将a中所有元素相乘
ans =  15

octave:61> floor(a)       % 将a中所有元素向下取整
ans =

    1   15    2    0

octave:63> ceil(a)        % 将a中所有元素向上取整
ans =

    1   15    2    1

octave:64> A
A =

   8   1   6
   3   5   7
   4   9   2

octave:65> max(A, [], 1)          % A中每一列的最大值
ans =

   8   9   7

octave:66> max(A, [], 2)          % A中每一行的最大值
ans =

   8
   7
   9

octave:67> max(A)
ans =

   8   9   7

octave:68> max(max(A))            % A中最大值，也可以采用max(A(:))
ans =  9

octave:69> A = [1 2 3; 4 5 6]
A =

   1   2   3
   4   5   6

octave:70> sum(A, 1)         % 对A中每一列求和
ans =

   5   7   9

octave:71> sum(A, 2)         % 对A中的每一行求和
ans =

    6
   15

octave:72> A = magic(3)
A =

   8   1   6
   3   5   7
   4   9   2

octave:73> sum(A, 1)
ans =

   15   15   15

octave:74> sum(A, 2)
ans =

   15
   15
   15

octave:76> A .* eye(3)
ans =

   8   0   0
   0   5   0
   0   0   2

octave:77> sum(sum(A .* eye(3)))
ans =  15

octave:78> flipud(eye(3))
ans =

Permutation Matrix

   0   0   1
   0   1   0
   1   0   0

octave:79> sum(sum(A .* flipud(eye(3))))
ans =  15

octave:81> A
A =

   8   1   6
   3   5   7
   4   9   2

octave:82> pinv(A)         % 求出A的伪逆矩阵
ans =

   0.147222  -0.144444   0.063889
  -0.061111   0.022222   0.105556
  -0.019444   0.188889  -0.102778
```    

其中，flipud()实现矩阵的上下翻转。
