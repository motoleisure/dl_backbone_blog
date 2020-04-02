- [bilibili-子豪兄](https://www.bilibili.com/video/BV1r7411X7LC?p=4)
- [Inception-v3 network architecture](https://miro.medium.com/max/1400/1*gqKM5V-uo2sMFFPDS84yJw.png)
- [Inception-v1-to-v4-progress](https://www.itread01.com/content/1544969366.html)
- [Medium-Review: Inception-v3 — 1st Runner Up (Image Classification) in ILSVRC 2015](https://medium.com/@sh.tsang/review-inception-v3-1st-runner-up-image-classification-in-ilsvrc-2015-17915421f77c)
- [zhihu-Inception V1,V2,V3,V4 模型总结](https://zhuanlan.zhihu.com/p/52802896)

### Inception技术演进
- Googlenet-V1
- BN-Inception
- V2~V3
- V4, Inception-ResNet
- Xception, 深度可分离卷积

### 计算机视觉的基础任务
- 分类
- 检测
- 分割

### Inception Vhttps://zhuanlan.zhihu.com/p/528028963
#### Main idea
- 重新思考Inception结构，减少param，提高模型的表达能力，提高模型运行效率
- 重新思考辅助分类器的作用
- 卷积分解
- 正则化，辅助分类器和label smoothing

#### op对比
- AlexNet : 60 million parameters
- VGGNet : 3× more parameters than AlexNet, 16/19 layers
- GoogLeNet / Inception-v1 : 7 million parameters, 22 layers
- Inception V3 : 25 million parameters, 42 layers

#### 提出通用网络设计原则
- (1) 慎用bottleneck特征，特别在浅层网络，不要过度压缩网络
- (2) 高维度特征在网络内部更容易处理。特征越多，收敛越快。
- (3) 在3×3和5×5大卷积之前可用1×1小卷积先将维，信息不会损失。因为邻近特征的强相关性，使得用1×1卷积将维时，信息损失比较少。
