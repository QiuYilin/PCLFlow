# PCLFlow
一个基于点云库PCL的三维视觉数据流编程框架

# 预期依赖

boost全家桶

# 预期目标

1.得益于PCL算法的结构化设计，将每个算法作为数据流一个执行单元

2.核心思想是图拓扑排序+数据流传递+线程池,类似于有数据流机制的PCL特化的taskflow/CGraph

3.提供开发过程中的可视化辅助，可能使用imgui，类似于Halcon的HDEVELOP，帮助三维视觉开发者快速生成dll

# 预期用法

```
pf::Graph A;
pf::Executor;
pf::VoxGridNode a; 
a.property[0] = 0;
pf::ResistrationNode b;
b.property[1] = 1;
A.add(a);
A.add(b);
if(A.connect(a,1,b,2)){
    Executor.run(A);
}
```
