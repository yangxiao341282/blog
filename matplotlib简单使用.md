```python
###############################################################################
#########                  xiaoy
#########                  2020.11.14
###############################################################################
```



# python matplotlib 的安装与基础使用

## 一 、matlplotlib的安装 

### 1. pip 安装

<center><pre>pip3 install matplotlib -i https://pypi.tuna.tsinghua.edu.cn/simple</pre></center>
​    可以还需要安装一部分辅助的包

### 2. linux 包管理器安装

#### ubuntu 安装命令

<center><pre>sudo apt-get install python-matplotlib</pre></center>   
#### Redhat 安装命令

<center><pre>sudo yum install python-matplotlib</pre></center>  
## 二、matplotlib的基础使用

```python
###导入python包
import matplotlib.pyplot as plt
import numpy as plt

##############################创建一块画布  并指定大小和分辨率 两种方式  ########################
plt.figure(figsize=(7, 3.5)， dpi = 100)
fig = plt.figure(figsize=(7, 3.5), dpi = 100)

###通过rc参数设定图像细节
plt.rcParams['xtick.direction'] = 'in' #刻度线向内
plt.rcParams['ytick.direction'] = 'in'

################################  添加子图的两种方法  ##################################

###添加子画布  22 1指建立一个2*2的图，最后一个1是 选定第一个区域
ax1 = plt.subplot(221)
ax2 = plt.subplot(222)

###另一种添加子画布方法
ax1 = fig.add_subplot(221)
ax2 = fig.add_subplot(222)

###
ax1.plot(x,y)  #画折线图
ax1.sactter(x,y) #画散点图
ax1.bar(x,y)  #条形图
ax.hist(x,y) #直方图

#################################  对于图的设定 ################################

###设定x和y轴的区间范围
ax1.set_xlim((0,1))
ax1.set_ylim((0,1))  

###设定x和y轴上尺度点的位置
ax1.set_xticks([0, 0.2, 0.4, 0.6, 0.8, 1.0])
ax1.set_yticks([0.4, 0.6, 0.8, 1.0])        

###设定x和y轴的标注
ax1.set_xlabel('recall')
ax1.set_ylabel('precision') 

###设定对应label位置
ax.legend(loc='low righr')

###设定title
ax.set_title('CIFAR-10',fontname='Times New Roman')

###设定是否有上和右边的边界
ax.spines['top'].set_visible(True)
ax.spines['right'].set_visible(True)

###设置格栅栏
ax.grid(true)
ax.grid(color='r', linestyle='--', linewidth=1,alpha=0.3)
#ax1.xaxis.grid(color='r', linestyle='--', linewidth=1,alpha=0.3)
#ax2.yaxis.grid(color='r', linestyle='--', linewidth=1,alpha=0.3)

```

```python
###保存图片
plt.subplots_adjust(wspace=0.3) #调整子图间距离
import tikzplotlib
tikzplotlib.save('choose_n.tex') #保存成tex文件
plt.savefig("x.pdf")
plt.show()
```
