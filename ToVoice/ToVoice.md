
  <h1>ChatLearning——ToVoice</h1>

> ## 实时语音克隆 - 中文/普通话
>

![mockingbird](https://user-images.githubusercontent.com/12797292/131216767-6eb251d6-14fc-4951-8324-2722f0cd4c63.jpg)

------



### **ChatLearning**的语音转换模块使用了[Mocking Bird](https://github.com/babysor/MockingBird)

考虑到使用**Mocking Bird**时环境配置麻烦，且深度学习过于占用资源，所以决定将语音转换模块部署至**ChatLearning服务器**中

------



### 使用步骤

1. 选择你需要克隆的音源（大概3-15秒的人声，最好纯净无杂音，小于10MB）
2. 将音源转换至**wav**格式，命名为**source.wav**放到**ChatLearning**目录下
3. 使用<code>uploadwav</code>指令将你的音源上传至**ChatLearning服务器**
4. 使用<code>setvoicept <训练集名称></code>指令来选择/切换训练模型（训练集）  训练集名称会在下方说明

#### **有两种情况会触发ChatLearning文字转语音功能**

1. 在开启**reply**的群中，<code>@bot</code>并发送<code>快说 <文字></code>
2. 使用<code>voicereply</code>指令**开启/关闭**在**发送答案**时，将文字的答案转为语音发送。并通过<code>voicereply <回复概率></code>来设置转为语音的概率（推荐20%）

#### **说明**

因服务器资源有限，在使用**@bot**方法触发功能时，最大字数**不得超过80**，并且有**10s**的冷却时间

后续会观察服务器负载情况来调整阈值

------



### 训练模型

以下模型均来自社区，且不定期更新

如果您通过**MockingBird**自己训练了模型，想应用到**ChatLearning**中并同意分享

请发送至threeax@foxmail.com，我会在确认可用后上传至ChatLearing服务器

| 服务器中的名称 |                         作者                         |                            源地址                            |                       说明                       |
| :------------: | :--------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------: |
|   pretrained   |      [**@babysor**](https://github.com/babysor)      | [地址](https://github.com/babysor/MockingBird/blob/main/README-CN.md) |        75k steps 用3个开源数据集混合训练         |
|   ferret70k    |   [**@ferretgeek**](https://github.com/ferretgeek)   |  [地址](https://github.com/babysor/MockingBird/issues/245)   | aidatatang_200zh以及aishell3两个数据集，混合训练 |
|   azusa200k    |  [**@Marg1t**](https://space.bilibili.com/23436398)  |     [地址](https://www.bilibili.com/video/BV1RF411z7C5)      |                 阿梓音源训练模型                 |
|    pipimeng    | [**@imi-123**](https://mirai.mamoe.net/user/imi-123) |  [地址](https://github.com/babysor/MockingBird/issues/460)   |           皮皮梦音源训练模型，步长160k           |

