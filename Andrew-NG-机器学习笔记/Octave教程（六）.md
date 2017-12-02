###### 向量化   

![](http://upload-images.jianshu.io/upload_images/5983416-1f45ffd93f362c55.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

对于上图的假设函数h，我们在非向量化的情况下可写出如下代码：     

```
prediction = 0.0;

for j = 1:n+1,
    prediction = prediction + theta(j) * X(j);
end;
```   

注：j从1~n+1是因为在Octave中下标是从1开始，虽然我们手工标注是从0开始的。   

但若我们在向量化的情况下可写出如下代码：      

```
prediction = theta' * X
```   

从上述对比中，我们可以看出在向量化的情况下，我们只需一行代码即可完成假设函数h的计算，效率比非向量化的情况下的代码运行效率高。    

现在，让我们看看使用C++语言，在非向量化的情况下的代码：         

```
double prediction = 0.0;

for (int j = 0; j <= n; j++)
    prediction += theta[j] * X[j];
```          

然后，我们再看看在向量化的情况下的代码：       

```
double prediction = theta.tanspose() * X
```      

通过上述代码，我们推荐在计算矩阵或向量时进行向量化操作（和使用相应的库函数），使我们代码变得简洁高效。          

对于线性回归的梯度下降算法，在非向量化的情况下，我们要分别计算出θ~0~，θ~1~，θ~2~， ······    

![](http://upload-images.jianshu.io/upload_images/5983416-3442957ebe9616af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在向量化的情况下，我们可以按照图中所示的操作写出相关代码：       

![](http://upload-images.jianshu.io/upload_images/5983416-449616674a3df03a.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
