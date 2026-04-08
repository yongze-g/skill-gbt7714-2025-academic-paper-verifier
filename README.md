# Academic Paper Verifier

学术文献验证工具 - 基于 GB/T 7714-2025 标准的参考文献著录格式生成器

## 简介

本技能用于验证学术文献的准确性，包括确认论文是否存在、核实关键信息（作者、标题、发表源、年份等），并依据 **GB/T 7714-2025《信息与文献 参考文献著录规则》** 生成规范的参考文献著录格式。

**核心原则：专事专办，按文献类型匹配对应要求，不堆砌信息。**

## 功能特性

- ✅ 验证学术文献是否存在及其信息准确性
- ✅ 获取论文的完整出版信息（作者、标题、期刊/会议、年份、页码等）
- ✅ 生成符合 GB/T 7714-2025 国标的参考文献著录格式
- ✅ 支持批量验证多条参考文献
- ✅ 支持两种引用体系：顺序编码制、著者-出版年制
- ✅ 支持13种文献类型：期刊、会议录、图书、学位论文、报告、标准、专利、预印本等

## 支持的文献类型

| 标识 | 文献类型 | 说明 |
|------|----------|------|
| [J] | 期刊论文 | Journal articles |
| [C] | 会议录 | Conference proceedings |
| [M] | 图书（专著）| Monographs |
| [D] | 学位论文 | Dissertations |
| [R] | 报告 | Reports |
| [S] | 标准 | Standards |
| [P] | 专利 | Patents |
| [N] | 报纸 | Newspapers |
| [PP] | 预印本 | Preprints (2025版新增) |
| [EB/OL] | 电子公告/网页 | Electronic bulletins/webpages |
| [DB/OL] | 在线数据库 | Online databases |

## 使用方法

### 基本用法

直接向助手提供论文信息，例如：

```
请帮我核实这篇论文并生成引用格式：
Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis
```

### 批量处理

一次性提供多条文献：

```
请帮我核实以下参考文献：
1. Attention is all you need
2. Deep learning
3. ImageNet Classification with Deep Convolutional Neural Networks
```

## 输出格式

### 顺序编码制示例

```
[1] Yu Yang, Pan Erting, Wang Xinya, et al. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis[C/OL]//CVPR, 2024: 4. https://openaccess.thecvf.com/...
```

### 著者-出版年制示例

```
Yu Yang, Pan Erting, Wang Xinya, et al. 2024. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis[C/OL]//CVPR, 2024: 4. https://openaccess.thecvf.com/...
```

## 核心规则

### 作者姓名著录

| 人名类型 | 姓 | 名 | 示例 |
|----------|-----|-----|------|
| 中国人名（汉语拼音） | 全部著录，首字母大写 | **宜用全称** | `Yu Yang`, `Wang Xinya` |
| 欧美人名（西文） | 全部著录，首字母大写 | 可缩写为首字母 | `Vaswani A`, `Einstein A` |

### 常见错误警示

| 错误类型 | 错误示例 | 正确做法 |
|----------|----------|----------|
| 作者大小写（西文） | VASWANI A（全大写） | Vaswani A（姓首字母大写，名缩写） |
| 中国人名缩写 | Yu Y（名缩写） | Yu Yang（**名用全称**） |
| 年份重复 | `//CVPR 2024, 2024` | `//CVPR, 2024`（会议名已含年份时不重复） |
| 会议录信息冗余 | 添加出版地、出版者 | 会议录只需会议名、年份、页码 |

## 文件结构

```
academic-paper-verifier/
├── SKILL.md              # 技能定义文件（核心）
├── README.md             # 本文件
├── LICENSE               # 开源协议
├── references/
│   └── gbt7714-2025-citation-rules.md  # GB/T 7714-2025 完整著录规则
└── examples/             # 示例文件（可选）
```

## 技术说明

- **标准依据**：GB/T 7714-2025《信息与文献 参考文献著录规则》（2026年7月1日实施）
- **网络搜索**：使用网络搜索获取文献的完整出版信息
- **信息核实**：通过多源交叉验证确保信息准确性

## 开源协议

MIT License - 详见 [LICENSE](LICENSE) 文件

## 贡献指南

欢迎提交 Issue 和 Pull Request 来改进本技能。

## 更新日志

### v1.0.0 (2026-04-08)
- 初始版本发布
- 支持13种文献类型的著录格式生成
- 完整实现 GB/T 7714-2025 标准规则
- 添加丰富的国标示例

## 致谢

- GB/T 7714-2025 标准起草单位
- 参考文献著录规则学习文档贡献者
