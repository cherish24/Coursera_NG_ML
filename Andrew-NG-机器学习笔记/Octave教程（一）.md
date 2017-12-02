###### 基本操作  

加减乘除和幂次方操作   

```
octave:1> 2 + 3
ans =  5
octave:2> 4 - 2
ans =  2
octave:3> 3 * 7
ans =  21
octave:4> 15 / 3
ans =  5
octave:5> 4 ^ 2
ans =  16
```    

布尔运算  

```
octave:7> 1 == 2       % false
ans = 0
octave:8> 1 ~= 2       % true, like !=
ans = 1
octave:9> 1 && 1       % AND
ans = 1
octave:10> 1 || 0      % OR
ans = 1
octave:11> xor(1, 0)   % OR
```

在Octave的命令行界面，即CLI中，在一条语句的后面添加一个分号，不会立即输出该语句的值，例如：  

```
octave:12>  a = 3
a =  3
octave:13> a = 3;
octave:14> a
a =  3
```     

浮点数的精确值    

```
octave:16> a = pi;
octave:17> a
a =  3.1416
octave:18> disp(a)
 3.1416
octave:19> disp(sprintf('2 decimals: %0.2f', a))
2 decimals: 3.14
octave:20> format long
octave:21> a
a =  3.14159265358979
octave:22> format short
octave:23> a
a =  3.1416
```   

矩阵和向量的创建    

```
octave:24> A = [1 2; 3 4; 5 6]
A =

   1   2
   3   4
   5   6

octave:25> B = [1, 2; 3, 4; 5, 6]
B =

   1   2
   3   4
   5   6

octave:26> C = [1 2;
> 3 4;
> 5 6]
C =

   1   2
   3   4
   5   6

octave:27> V = [1 2 3]
V =

   1   2   3

octave:28> V = [1; 2; 3]
V =

   1
   2
   3
```   

创建一个由1~2的1*11的向量，其中每列元素按0.1递增：  

```
octave:29> V = 1:0.1:2
V =

 Columns 1 through 7:

    1.0000    1.1000    1.2000    1.3000    1.4000    1.5000    1.6000

 Columns 8 through 11:

    1.7000    1.8000    1.9000    2.0000
```    

按照上述代码可推断出如下代码：     

```
octave:30> V = 1:6
V =

   1   2   3   4   5   6
```    

其中，此处代码中的步长默认为1。       

创建元素都为0或1的矩阵：     

```
octave:31> ones(2, 3)
ans =

   1   1   1
   1   1   1

octave:32> A = 2 * ones(3, 4)
A =

   2   2   2   2
   2   2   2   2
   2   2   2   2

octave:33> W = zeros(3, 4)
W =

   0   0   0   0
   0   0   0   0
   0   0   0   0
```      

利用随机数创建矩阵：        

```
octave:34> rand(3, 3)
ans =

   0.756239   0.689382   0.798139
   0.520566   0.078869   0.136158
   0.277309   0.547070   0.746694

octave:35> randn(3, 3)  % Gauss random variables
ans =

  -1.109632   0.918097  -1.759147
   0.370428   2.668096  -0.648677
  -0.674782  -0.094224  -0.316925
```     

利用Octave绘制直方图：     

```
octave:36> w = -6 + sqrt(10)*(randn(1, 100000));
octave:37> hist(w)
octave:38> hist(w ,50)      % 绘制条数为50的直方图
```   

![hist(w)](http://upload-images.jianshu.io/upload_images/5983416-f05207bc473d1198.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![hist(w ,50)](http://upload-images.jianshu.io/upload_images/5983416-f11ec690769622cc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

创建单位矩阵：      

```
octave:41> eye(4)
ans =

Diagonal Matrix

   1   0   0   0
   0   1   0   0
   0   0   1   0
   0   0   0   1
```           

查询帮助文档，即"help <function>"，如：     

```
help eye
```
