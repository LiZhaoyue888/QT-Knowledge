### 为什么写这篇文章？
由于工作在做频谱仪软件界面，所以选定用QCustomPlot做技术内核。经常出现提问AI有关QCustomPlot的部分回答的很不满意，幻觉严重。因此，决定写下这篇文章，作为对QCustomPlot的一个分析。
## 这篇文章讲了什么？  
所有关于QCustomPlot你应该关注的  
- QCustomPlot的性能到底怎么样？为什么性能这么好？
- 为什么QCharts的性能很差劲，尤其是在实时高速绘图这方面。
- QCustomPlot有哪些惊喜的特性
- 如何定制你自己的QCustomPlot用于频谱仪的显示界面

## 关于QCustomPlot你应该知道的
- 官方链接：https://www.qcustomplot.com/
- Github官方源码带Demo：https://github.com/dbzhang800/QCustomPlot/blob/master/examples/plots/mainwindow.cpp
#### 自适应采样率
- QCustomPlot的Adaptive sampling自适应采样率是默认打开的，在源码第21038行
```C++
void QCPGraph::setAdaptiveSampling(bool enabled)
{
  mAdaptiveSampling = enabled; //line:21038
}
```
#### 如何启用官方源码
1. 用Qt Creator打开 QCustomPlot\examples\plots\plot-examples.pro
2. 修改.pro的QCustomPlot的路径，把QCustomPlot.h和.cpp多拷贝几份到../../路径和.pro路径
3. 修改mainwindow里面的  setupDemo(20);，启用官方示例的20个Demo
