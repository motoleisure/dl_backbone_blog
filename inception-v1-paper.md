- [bilibili-子豪兄](https://www.bilibili.com/video/BV1r7411X7LC?p=4)
- [Inception-v1 network architecture](https://static.oschina.net/uploads/space/2018/0317/141544_FfKB_876354.jpg)
- [Inception-v1-to-v4-progress](https://www.itread01.com/content/1544969366.html)
### Inception技术演进
- Googlenet-V1
- BN-Inception
- V2~V3
- V4, Inception-ResNet
- Xception, 深度可分离卷积

### Refer to the Network in Network
- core idea 1, using 1x1 kernel filter
	- 降维或者升维
	- 跨通道信息融合
	- 减少参数量
	- 增加模型深度，提高非线性表示能力
	
- core idea 2, global average pooling
	- 用gap替代全连接层，fully connected layers
	- 便于迁移学习
	- class activation mapping
	
### Refer to Arora paper
- 理论研究，Provavle Bounds for leraning some deep representations, 
用稀疏，分散的网络取代以前庞大密集臃肿的网络
	
### Inception v1

#### main idea
- 在增加网络深度和宽度的同时减少参数量和计算量
- 基于2个理论
	- Hebbian principle，赫布理论，神经元突触 用进废退， fire togehter, wire together
	- multi-scale，多尺度信息处理
	
#### Motivation
- (现状)提高模型性能的传统方法
	- 1 增加深度(层数)
	- 2 增加宽度(filters)
- (痛点)传统方法的两个缺点
	- 1 更深和更宽的模型，适用于大规模标注好的数据集，某些细粒度的数据集标注成本非常高
	- 2 更深和更宽的模型， 参数量非常大，导致模型容易过拟合
- 所以我们不能一味追求模型精度而不顾计算效率和计算量，我们的目标是在提升模型精度的同时，也要兼顾计算效率，能耗，内存占用，部署在移动设备和嵌入式设备中。
- (提出解决方法)
	- 用稀疏连接结构取代密集连接
	- 但现有硬件是在密集结构的数据上加速的
	- (提出假设)能否在仍旧利用现有硬件进行密集矩阵运算的条件下，改进模型结构，哪怕只在卷积层水平改进，从而能够利用额外的稀疏性呢？
	- 将稀疏矩阵分解为密集的子矩阵，能加速矩阵的乘法
	
#### Architecural details
- Inception其实是用一系列密集的子模块组成一个大的稀疏模型
- 局部信息由1x1卷积提取，浅层网络提取
- 大范围的空间信息由大卷积核提取，深层网络提取

- 9 inceptions (3a, 3b, 4a-4e, 5a, 5b)
- 2 个辅助分类器
- 22 layers
- 比alexnet少12倍参数，但更加准确
