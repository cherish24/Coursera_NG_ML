####### 绘制图表   

绘制sin函数图：     

```
octave:1>  t = [0:0.01:0.98];
octave:2> y1 = sin(2 * pi * 4 * t);
octave:3> plot(t, y1)
```   

结果如图所示：   


![y1](http://upload-images.jianshu.io/upload_images/5983416-ffedb0d23077e90d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

绘制cos函数图：    

```
octave:4> y2 = cos(2 * pi * 4 * t);
octave:5> plot(t, y2)
```       

结果如图所示：

![y2](http://upload-images.jianshu.io/upload_images/5983416-e9d277a104eb7ea5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

将两个函数图放置于一个界面：      

```
octave:6> plot(t, y1)
octave:7> hold on;                   % 保持sin函数图，新函数图将在此界面中继续绘制
octave:8> plot(t, y2, 'r')           % r表示函数图的线条采用红色
```    

结果为：         

![](http://upload-images.jianshu.io/upload_images/5983416-67af422f94ee6e79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在此基础上，我们为函数图添加相关信息：      

```
octave:9> xlabel('time')                % x轴信息
octave:10> ylabel('value')              % y轴信息
octave:11> legend('sin', 'cos')         % 函数标明
octave:12> title('My Plot')             % 函数图标题
```         

结果为：        

![](http://upload-images.jianshu.io/upload_images/5983416-8d430e68adfaa416.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

将函数图保存至本地：     

```
octave:13> cd 'D:\Codes\Coursera\ML'; print -dpng 'myPlot.png'
```    

关闭函数图窗口只需输入close即可。             

给函数图窗口编号：      

```
octave:15> figure(1); plot(t, y1);
octave:16> figure(2); plot(t, y2);
```     

另一种将两个函数图绘制于同一界面的方法：        

```
octave:18> subplot(1, 2, 1);            % 将界面分为1*2，即分为两个格子，最后一个参数代表使用哪一个格子
octave:19> plot(t, y1)
octave:20> subplot(1, 2, 2);
octave:21> plot(t, y2)
```     

结果为：      

![](http://upload-images.jianshu.io/upload_images/5983416-79bc71ecf7bee6bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

修改坐标轴尺度：      

```
octave:22> axis([0.5 1 -1 1])     % 前两个参数表示x轴为0.5~1，后两个参数表示y轴为-1~1
```      

结果为：

![](http://upload-images.jianshu.io/upload_images/5983416-4c6a8760683bf382.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

使用clf可将上述函数图的界面清空。    

可视化矩阵：        

```
octave:23> A = magic(4);
octave:24> A
A =

   16    2    3   13
    5   11   10    8
    9    7    6   12
    4   14   15    1

octave:26> imagesc(A)
```      

结果为：      

![](http://upload-images.jianshu.io/upload_images/5983416-58189b9a226c1cbf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

通过使用不同的颜色来代表矩阵A中的每一个元素。       

我们也可以将其改为灰度图：     

```
octave:27> imagesc(A), colorbar, colormap gray;
```   

结果为：    

![](http://upload-images.jianshu.io/upload_images/5983416-6cc22d8eb45e5274.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
