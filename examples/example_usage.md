# 使用示例

本文档展示学术文献验证技能的使用示例。

## 示例1：会议论文

### 输入

```
请帮我核实这篇论文：
Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis
```

### 输出

**步骤1：识别文献类型**

会议录 [C]（CVPR 2024会议论文）

**步骤2：著录项目核实表**

| 字段 | 类型要求 | 论文信息 | 是否必备 |
|------|----------|----------|----------|
| 主要责任者 | 有则必备 | Yu Yang, Pan Erting, Wang Xinya, 等 | 是 |
| 题名 | 必备 | Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis | 是 |
| 文献类型标识 | 必备 | [C/OL] | 是 |
| 会议名称 | 有则必备 | CVPR | 是 |
| 会议年份 | 有则必备 | 2024 | 是 |
| 引文页码 | 有则必备 | 4 | 是 |
| 获取和访问路径 | 电子资源必备 | https://openaccess.thecvf.com/... | 是 |

**步骤3：引用格式**

顺序编码制：
```
[1] Yu Yang, Pan Erting, Wang Xinya, et al. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis[C/OL]//CVPR, 2024: 4. https://openaccess.thecvf.com/content/CVPR2024/html/Yu_Unmixing_Before_Fusion_A_Generalized_Paradigm_for_Multi-Source-based_Hyperspectral_Image_CVPR_2024_paper.html.
```

---

## 示例2：期刊论文

### 输入

```
请帮我核实：Attention is all you need
```

### 输出

**文献类型：** 期刊论文 [J]

**核实信息：**
- 作者：Vaswani A, Shazeer N, Parmar N, 等
- 期刊：Advances in Neural Information Processing Systems (NIPS)
- 年份：2017
- 页码：5998-6008

**引用格式：**
```
[1] Vaswani A, Shazeer N, Parmar N, et al. Attention is all you need[C/OL]//NIPS 2017, 2017: 5998-6008. https://doi.org/10.48550/arXiv.1706.03762.
```

---

## 示例3：批量处理

### 输入

```
请帮我核实以下参考文献：
1. Deep learning
2. ImageNet Classification with Deep Convolutional Neural Networks
3. Very Deep Convolutional Networks for Large-Scale Image Recognition
```

### 输出

**总览表格：**

| 序号 | 题名 | 文献类型 | 状态 |
|------|------|----------|------|
| 1 | Deep learning | 期刊[J] | 已核实 |
| 2 | ImageNet Classification... | 会议录[C] | 已核实 |
| 3 | Very Deep Convolutional... | 会议录[C] | 已核实 |

**引用格式汇总：**
```
[1] LeCun Y, Bengio Y, Hinton G. Deep learning[J]. Nature, 2015, 521(7553): 436-444.
[2] Krizhevsky A, Sutskever I, Hinton G E. ImageNet classification with deep convolutional neural networks[C]//NIPS 2012, 2012: 1097-1105.
[3] Simonyan K, Zisserman A. Very deep convolutional networks for large-scale image recognition[C/OL]//ICLR 2015, 2015. https://arxiv.org/abs/1409.1556.
```

---

## 常见错误对比

### 错误1：中国人名缩写

❌ 错误：
```
Yu Y, Pan E, Wang X
```

✅ 正确：
```
Yu Yang, Pan Erting, Wang Xinya
```

### 错误2：年份重复

❌ 错误：
```
//CVPR 2024, 2024
```

✅ 正确：
```
//CVPR, 2024
```

### 错误3：会议录添加出版地

❌ 错误：
```
[C]//CVPR. Seattle: IEEE, 2024
```

✅ 正确：
```
[C]//CVPR, 2024
```
