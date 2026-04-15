# Academic Paper Verifier

GB/T 7714-2025 学术文献验证与引用格式生成工具

## 简介

本工具用于验证学术文献的准确性，包括确认论文是否存在、核实关键信息（作者、标题、发表源、年份等），并依据 GB/T 7714-2025《信息与文献 参考文献著录规则》生成规范的参考文献著录格式。

### 核心特性

- **文献类型全面支持**：覆盖13类文献类型（期刊、会议、图书、学位论文、报告、标准、专利、预印本、数据集、档案、地图、网站/网页、报纸）
- **精确匹配验证**：至少3个独立信息项完全匹配才认定文献相同
- **GB/T 7714-2025 标准合规**：完整实现2025版国标要求
- **格式逐条核验**：对照常见错误警示表逐项检查，确保著录格式正确
- **智能类型识别**：自动识别 arXiv、bioRxiv 等预印本平台文献

### 适用场景

1. 验证某篇论文是否存在及其信息准确性
2. 获取论文的完整出版信息（作者、标题、期刊/会议、年份、页码等）
3. 生成符合国标的参考文献著录格式
4. 批量验证多条参考文献
5. 验证引用格式是否正确

## 支持的文献类型

| 类型标识 | 文献类型 | 示例 |
|----------|----------|------|
| [J] | 期刊论文 | Nature、Cell 等期刊发表的论文 |
| [C] | 会议录 | CVPR、ICML、AAAI 等会议论文 |
| [M] | 图书（专著） | 教材、专著、手册等 |
| [D] | 学位论文 | 硕士、博士学位论文 |
| [R] | 报告 | 科技报告、调研报告、白皮书 |
| [S] | 标准 | 国家标准、行业标准、国际标准 |
| [P] | 专利 | 发明专利、实用新型专利、外观设计专利 |
| [PP] | 预印本 | arXiv、bioRxiv、medRxiv 等预印本 |
| [DS] | 数据集 | 科学数据集、统计数据库 |
| [A] | 档案 | 历史档案、公文档案 |
| [CM] | 地图 | 地理地图、工程图纸 |
| [EB/OL] | 网站/网页 | 在线网站、网页资源 |
| [N] | 报纸 | 报纸文章 |

## 核心功能

### 1. 文献匹配性校验
- 标题、作者、年份、期刊/会议名、DOI 等多信息交叉验证
- 至少3个独立信息项完全匹配才认定文献相同
- 模糊信息警示（标题不完整、拼写错误、信息缺失等）
- 搜索结果优先级筛选（权威数据库优先）

### 2. 作者姓名著录
- **西文著录**：姓全部著录，首字母大写，名可缩写（如 `Vaswani A`）
- **汉语拼音著录**：姓全部著录，首字母大写，名用全称（如 `Li Jiangning`）
- 同姓不同名时著录名的首字母或全名以区分

### 3. 预印本特殊处理
- arXiv、bioRxiv、medRxiv 等平台文献自动识别为 `[PP/OL]`
- 格式要求：`主要责任者. 题名[PP/OL]. 版本. 出版平台(创建或修改日期)[引用日期]. 获取和访问路径.`
- 示例：`Kingma D P, Ba J L. Adam: A method for stochastic optimization[PP/OL]. arXiv(2014-12-22)[2024-09-30]. https://arxiv.org/abs/1412.6980.`

### 4. 格式逐条核验
- 对照常见错误警示表逐项检查
- 作者著录检查
- 文献类型和标识符检查
- 著录用符号检查（.`:``,`;`//`[]`()`）
- 必备性检查（必备/有则必备/可选）

## 输出格式

### 最终引用格式
```
[1] Vaswani A, et al. Attention is all you need[J]. NIPS, 2017, 30: 5998-6008.
[2] Yu Y, et al. Unmixing before fusion[C/OL]//CVPR, 2024: 4. https://...
[3] Kingma D P, Ba J L. Adam: A method for stochastic optimization[PP/OL]. arXiv(2014-12-22)[2024-09-30]. https://arxiv.org/abs/1412.6980.
```

### 查证链接表
| 文献题名 | 查证链接 | 链接类型 | 匹配度 |
|----------|----------|----------|--------|
| 题名 | [链接](URL) | 会议官方 | 高 |
| 题名 | [链接](URL) | 预印本 | 中 |

## 使用示例

### 示例1：会议录文献
**输入**：Yu Yang et al. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis, CVPR 2024

**输出**：
```
[1] Yu Yang, Pan Erting, Wang Xinya, et al. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis[C/OL]//CVPR, 2024: 4. https://openaccess.thecvf.com/content/CVPR2024/html/Yu_Unmixing_Before_Fusion_A_Generalized_Paradigm_for_Multi-Source-based_Hyperspectral_Image_CVPR_2024_paper.html.
```

### 示例2：预印本文献（arXiv）
**输入**：Kingma & Ba, Adam: A Method for Stochastic Optimization, arXiv 2014

**输出**：
```
[1] Kingma D P, Ba J L. Adam: A method for stochastic optimization[PP/OL]. arXiv(2014-12-22)[2024-09-30]. https://arxiv.org/abs/1412.6980.
```

## 文档结构

```
academic-paper-verifier/
├── SKILL.md                                  # 入口与指南
├── README.md                                 # 项目说明
├── CHANGELOG.md                              # 版本变更记录
├── LICENSE                                   # MIT 许可证
├── CONTRIBUTING.md                           # 贡献指南
└── references/
    ├── gbt7714-2025-citation-rules.md        # GB/T 7714-2025 完整规则
    └── citation-formats.md                   # 各类型文献著录格式详解
```

## 参考标准

- GB/T 7714-2025《信息与文献 参考文献著录规则》
- 实施日期：2026-07-01
- 替代标准：GB/T 7714-2015

## 版本历史

详见 [CHANGELOG.md](CHANGELOG.md)

## 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 贡献

欢迎提交 Issue 和 Pull Request，详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## 联系方式

- 项目维护者：Academic Paper Verifier Contributors
- 问题反馈：请通过 Issue 提交

## 致谢

感谢所有贡献者对本项目的支持和贡献。
