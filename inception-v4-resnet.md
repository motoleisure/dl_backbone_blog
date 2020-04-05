- [bilibili-子豪兄](https://www.bilibili.com/video/BV1r7411X7LC?p=7)
- ![CSDN-incpetion-v4-architecture](https://images2017.cnblogs.com/blog/853467/201712/853467-20171227215021394-1251296998.png)
- [Medium-Review: Inception-v4, Evolved From GoogLeNet, Merged with ResNet Idea (Image Classification)](https://towardsdatascience.com/review-inception-v4-evolved-from-googlenet-merged-with-resnet-idea-image-classification-5e8c339d18bc)

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

### Inception V4
#### Main idea
- 2015,何凯明等人提出了震惊业界的ResNet模型，在网络中引入了shortcut用以解决深层网络的无法收敛(梯度消失/梯度爆炸)或者收敛慢的问题。
- 本文提出质疑的同时也尝试inception+resnet
- 提出了Inception-V4, Inception-ResNet-V1, Inception-ResNetV2三个模型
  - Inception-V4没有使用残差模块，它是在Inception-V3的基础上进一步改进了Inception模块，提升了模型性能和计算效率。
  - Inception_ResNet将Inception模块和深度残差网络ResNet结合，提出了三种包含残差连接的Inception模块，残差连接显著加快了训练收敛速度
  - Inception-ResNet-V2和Inception-V4的早期stem网络结构相同。
  - Inception-ResNet-V1和Inception-V3准确率相近，Inception-ResNet-V2和Inception-V4准确率相近。
  - 经过模型集成和图像多尺度裁剪处理后，模型top-5错误率降低至3。1%
  - 针对卷积核个数大于1000时残差模型早期训练不稳定的问题，提出了对残差分支幅度缩小的解决方案。
  
