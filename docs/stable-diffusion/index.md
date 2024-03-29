---
sidebar_position: 1
---

# Stable Diffusion

## 我从哪来，我在哪

人工智能绘画在 2021 年临近“奇点”，即在这个时间之前，可认为处于玩具状态，但在 2021 年后它变得可用。

人工智能绘画原理：采用深度学习生成式神经网络，从人类作品中学习绘画规律，从而实现绘画。

[Stable Diffusion](https://stability.ai/)（SD）是一种人工智能绘画技术，使用开源模型，于 2022 年 8 月面世。

发展史关键词：

- GAN 2014
- CNN 2015
- CLIP 2021
- Imagen 2022.5
- Parti 2022.6
- ControlNet 2023.2

## 对标的商业产品

- Midjourney v5 2023.3
- OpenAI DALL·E 2：2022.4
- Adobe Firefly 2023.5

均是扩散模型，源自热力学分支——非平衡热力学。墨水在水中扩散形成大斑点。墨水在扩散前，初始状态难以采样（形成数据），而在扩散后变得简单均匀，容易采样（形成数据）。非平衡热力学可以描述墨水扩散过程的概率分布，扩展过程每一步都可逆，只要步长足够小，我们可以从最终分布中推导出最初的复杂分布。即一种有损图像压缩编解码器。

# 特点

- 自动
- 迅速
- 可重复
- 可探索
- 依赖数据
- 需要多轮调整指导
- 不含有表达指向
- 图生图
- 可控性 ControlNet
- 开放性（未审查、有暴力、内容敏感和版权问题）

## 如何使用

WebUI 是最简单方式，AI绘画师通过给出“提示词”，SD 将文本编码为数字化图像特征，调用 Unet神经网络和调度算法创建图像信息，解码器 VAE 绘制最终图像。

所以，SD 之后的由模型控制，对 AI 绘画师来说，提示词是关键。

1. 有计算机基础：按步骤安装官方包
2. 爱好者：安装整合包

安装后，可以在浏览器中使用。

### 安装模型

模型：指主模型

平台：

- https://civitai.com
- https://huggingface.co
- https://www.liblib.art/ 国内

### 安装插件

- LoRA 模型：微调模型
- LyCORIS 模型：升级版 LoRA
- ControlNet：控制扩展模型
- Textual Inversion：Embedding 模型
- Hypernetwork：附件网络，个性化模型
- VAE 模型：Variational Autoencoder，滤镜+微调，用于美化

### WebUI 功能

- 文生图：通过提示词生成图片
- 图生图：通过图片和提示词生成图片
- 后期处理：放大分辨率
- PNG图像信息：通过图片读取出提示词
- 模型合并：对模型进行融合
- 训练：训练自己的模型
- Additional Networks：LoRA 微调模型插件
- 模型转化：格式转化
- 图片浏览器
- WD 1.4 标签器：从图片推导提示词
- 设置
- 扩展：安装插件和更新

### 采样器

- Euler a: 默认
- DPM++2M Karras：常用于卡通，速度快
- DPM++2S a Karras：用于写实
- DPM++SDE Karras：用于写实

### 步数

- 默认 20，不建议超过 30。

### 分辨率

- 大多模型用 512 * 512 渲染，少数 768 * 768。
- 如果设置为 1024 * 1024，会合并内容嵌入，产生多人、多角度等问题。

### 提示词引导系数 CFG Scale

- CFG：7。即模型创造力对提示词的遵从度，建议7~10。

### 随机种子 Seed

-1

## 文生图经验

1. 类似绘画，从重点开始描述
2. 英文比中文准确
3. 提示词多不一定好
4. 增加反向词过滤，提高出片率
5. 学习提示词语法：从画质、艺术类型、美术风格、国家特征、大师风格、软件风格、游戏风格
6. 学习提示词：人物、环境、构图、拍摄视角、镜头焦距、色彩、光影、设备、景别
7. \<LoRA:模型名:权重>、\<hypernetwork:模型名:权重>
8. 注意提示词顺序
9. (关键词:权重)
10. a AND b、a | b
11. 反向词，有相对固定的套路，直接借用。NSFW

## 图生图

- 常用于人像生成卡通、草图生成具体图

## LoRA

- 多 LoRA 权重融合，可以得到令人惊讶的作品。

## ControlNet

- 控制材质，控制人物姿态。


