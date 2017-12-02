###### 控制语句    

```
V =

   0
   0
   0
   0
   0
   0
   0
   0
   0
   0

>> for i=1:10,                 % for循环
>     V(i) = 2 ^ i;
> end;
>> V
V =

      2
      4
      8
     16
     32
     64
    128
    256
    512
   1024

>> indices = 1:10;
>> for i=indices,          % for循环遍历输出
>     disp(i);
> end;
 1
 2
 3
 4
 5
 6
 7
 8
 9
 10

>> i = 1;
>> while i <= 5,              % while循环
>     V(i) = 100;
>     i = i + 1;
> end;
>> V
V =

    100
    100
    100
    100
    100
     64
    128
    256
    512
   1024

>>  i = 1;
>> while true,
>     V(i) = 999;
>     i = i + 1;
>     if i == 6,
>         break;              % break与continue的使用
>     end;
> end;
>> V
V =

    999
    999
    999
    999
    999
     64
    128
    256
    512
   1024

>> V(1) = 2;
>> if V(1) == 1,                             % if-else语句
>     disp('The value is one');
> elseif V(1) == 2,
>     disp('The value is two');
> else
>     disp('The value is not one or two');
> end;
The value is two
```           

###### 函数     

我们先创建costFunctionJ.m文件，并在其添加如下代码：      

```
function J = costFunctionJ(X, y, theta)

% X is the "design matrix" contanining our tranining examples.
% y is the class labels.

m = size(X, 1);                   % number of tranining examples
predictions = X*theta;            % predictions of hypothesis on all m examples
sqrErrors = (predictions-y).^2;   % squared sqrErrors

J = 1/(2*m) * sum(sqrErrors);
```       

然后，我们在Octave的CLI中键入如下命令：       

```
% 先利用cd命令前往costFunctionJ.m文件目录路径

>> X = [1 1; 1 2; 1 3]
X =

   1   1
   1   2
   1   3

>> y = [1; 2; 3]
y =

   1
   2
   3

>> theta = [0;1];
>> j = costFunctionJ(X, y, theta)
j = 0
```       

注：文件名需与函数名一致。
