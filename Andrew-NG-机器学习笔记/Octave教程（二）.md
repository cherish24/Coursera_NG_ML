###### 如何求矩阵、向量的维数  

```
octave:1> A = [1 2; 3 4; 5 6]
A =

   1   2
   3   4
   5   6

octave:2> size(A)
ans =

   3   2

octave:3> size(A, 1)
ans =  3
octave:4> size(A, 2)
ans =  2
octave:5> V = [1 2 3 4]
V =

   1   2   3   4

octave:6> length(V)
ans =  4
octave:7> length(A)
ans =  3
octave:8> W = [1; 2; 3]
W =

   1
   2
   3

octave:9> length(W)
ans =  3
```     

其中，length()表示求出矩阵或向量的最大维数。    

###### 如何导入数据   

```
octave:12> load ex1data1.txt       % 或者 load('ex1data1.txt')
```    

在导入数据之前，需要用cd命令“前往”数据文件所在的文件目录。当然，我们可以使用pwd命令查看当前所在的文件目录路径，确保在导入数据之前，“前往”数据文件所在的文件目录。      

###### 如何显示Octave中当前的所有变量   

```
octave:13> who
Variables in the current scope:

A         V         W         ans       ex1data1

octave:14> whos
Variables in the current scope:

   Attr Name          Size                     Bytes  Class
   ==== ====          ====                     =====  =====
        A             3x2                         48  double
        V             1x4                         32  double
        W             3x1                         24  double
        ans           1x15                        15  char
        ex1data1     97x2                       1552  double

Total is 222 elements using 1671 bytes
```      

既然Octave能存储当前的所有变量，那我们就可以清除Octave中当前存储的变量：     

```
octave:15> clear V
octave:16> whos
Variables in the current scope:

   Attr Name          Size                     Bytes  Class
   ==== ====          ====                     =====  =====
        A             3x2                         48  double
        W             3x1                         24  double
        ans           1x15                        15  char
        ex1data1     97x2                       1552  double

Total is 218 elements using 1639 bytes
```      

其中，我们若只键入clear，则表示清除Octave中当前所有的变量。    

###### 如何存储数据   

```
octave:17> V = ex1data1(1:10)           % 将ex1data1中10个数据保存至V
V =

 Columns 1 through 8:

   6.1101   5.5277   8.5186   7.0032   5.8598   8.3829   7.4764   8.5781

 Columns 9 and 10:

   6.4862   5.0546

octave:18> whos
Variables in the current scope:

   Attr Name          Size                     Bytes  Class
   ==== ====          ====                     =====  =====
        A             3x2                         48  double
        V             1x10                        80  double
        W             3x1                         24  double
        ans           1x15                        15  char
        ex1data1     97x2                       1552  double

Total is 228 elements using 1719 bytes

octave:19> save test.mat V;                % 将V中的数据保存至test.mat
octave:20> save test.txt V -ascii          % 将V中的数据以ascii吗保存至test.txt
```      

###### 如何操作数据    

```
octave:21> A
A =

   1   2
   3   4
   5   6

octave:22> A(3, 2)            % 取出位于A中第三行第二列的元素
ans =  6
octave:23> A(2, :)            % 取出位于A中第二行的所有元素
ans =

   3   4

octave:24> A(:, 2)            % 取出位于A中第二列的所有元素
ans =

   2
   4
   6

octave:25> A([1 3], :)        % 取出位于A中第一行或第三行的所有元素
ans =

   1   2
   5   6

octave:26> A(:, 2) = [10; 11; 12]         % 对位于A中第二列的所有元素重新赋值
A =

    1   10
    3   11
    5   12

octave:27> A = [A, [100; 110; 120]]         % 对于矩阵A新增一列
A =

     1    10   100
     3    11   110
     5    12   120

octave:28> A(:)           % 输出A中所有的元素，即将A中的元素放入一个向量中
ans =

     1
     3
     5
    10
    11
    12
   100
   110
   120

octave:29> B = [11 12; 13 14; 15 16]
B =

   11   12
   13   14
   15   16

octave:30> C = [A B]              % 将A和B组成一个新矩阵
C =

     1    10   100    11    12
     3    11   110    13    14
     5    12   120    15    16

octave:31> B = [11 12 13; 14 15 16; 17 18 19]
B =

   11   12   13
   14   15   16
   17   18   19

octave:32> C = [A; B]
C =

     1    10   100
     3    11   110
     5    12   120
    11    12    13
    14    15    16
    17    18    19
```          

其中，“:”表示第i行或第j列的所有元素。
