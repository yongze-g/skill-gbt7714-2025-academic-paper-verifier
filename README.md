# Academic Paper Verifier

【AI生成警示】该项目由AI生成，核实和重排的参考文献可能依然不准确。

GB/T 7714-2025 学术文献验证与引用格式生成工具

## 简介

本工具用于验证学术文献的准确性，包括确认论文是否存在、核实关键信息（作者、标题、发表源、年份等），并依据 **GB/T 7714-2025《信息与文献 参考文献著录规则》** 生成规范的参考文献著录格式。

### 核心特性

- **文献类型全面支持**：覆盖17类文献类型（期刊、会议、图书、学位论文、报告、标准、专利、预印本、数据集、档案、地图、网站/网页、报纸、数据库、汇编、计算机程序、其他）
- **精确匹配验证**：多信息项交叉验证，确保文献准确性
- **GB/T 7714-2025 标准合规**：完整实现2025版国标要求
- **格式逐条核验**：对照常见错误警示表逐项检查，确保著录格式正确
- **智能类型识别**：自动识别文献类型和载体标识

### 适用场景

1. 验证某篇论文是否存在及其信息准确性
2. 获取论文的完整出版信息（作者、标题、期刊/会议、年份、页码等）
3. 生成符合国标的参考文献著录格式
4. 批量验证多条参考文献
5. 验证引用格式是否正确

## 支持的文献类型

### 文献类型标识

| 标识 | 文献类型 | 示例 |
|------|----------|------|
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
| [EB] | 网站/网页 | 在线网站、网页资源 |
| [N] | 报纸 | 报纸文章 |
| [DB] | 数据库 | 在线数据库 |
| [G] | 汇编 | 汇编文献 |
| [CP] | 计算机程序 | 软件程序 |
| [Z] | 其他 | 其他未分类文献 |

### 载体标识（需与文献类型标识组合使用）

| 标识 | 载体类型 |
|------|----------|
| /OL | 在线资源 |
| /CD | 光盘 |
| /DK | 磁盘 |
| /MT | 磁带 |
| /MM | 缩微资料 |

### 组合示例

- 在线期刊论文：`[J/OL]`
- 在线会议录：`[C/OL]`
- 在线网页：`[EB/OL]`
- 在线数据库：`[DB/OL]`

## 工作流程

```
步骤1：分析指令 → 步骤2：提取关键字 → 步骤3：信息收集 → 步骤4：信息匹配验证
    ↓
步骤5：识别文献类型 → 步骤6：获取格式模板 → 步骤7：准备必备项 → 步骤8：常见问题排查
    ↓
步骤9：生成引用格式 → 步骤10：汇总输出
```

## 核心功能

### 1. 文献匹配性校验
- 标题、作者、年份、期刊/会议名、DOI 等多信息交叉验证
- 精确匹配与模糊搜索结合
- 搜索结果优先级筛选（权威数据库优先）

### 2. 作者姓名著录规则
- **西文著录**：姓全部著录，首字母大写，名可缩写（如 `Vaswani A`）
- **汉语拼音著录**：姓全部著录，首字母大写，名用全称（如 `Yu Yang`）
- 同姓不同名时著录名的首字母或全名以区分
- 作者数量规则：≤3人全部列出，>3人列出前3人后加",等"或", et al."

### 3. 格式逐条核验
- 对照常见错误警示表逐项检查
- 作者著录格式检查
- 文献类型和标识符检查
- 著录用符号检查（`.`, `:`, `,`, `;`, `//`, `[]`, `()`）
- 必备性检查（必备/有则必备/可选）

### 4. 降级处理规则
- 会议录文献若无官方链接，自动降级为预印本类型 `[PP/OL]`
- 在查证链接表中标注警告信息

## 输出格式

### 最终引用格式
```
[1] Vaswani A, Shazeer N, Parmar N, et al. Attention is all you need[C/OL]//NIPS 2017, 2017: 5998-6008. https://doi.org/10.48550/arXiv.1706.03762.
[2] Yu Yang, Pan Erting, Wang Xinya, et al. Unmixing before fusion: a generalized paradigm for multi-source based hyperspectral image synthesis[C/OL]//CVPR, 2024: 4. https://openaccess.thecvf.com/content/CVPR2024/html/Yu_Unmixing_Before_Fusion_A_Generalized_Paradigm_for_Multi-Source-based_Hyperspectral_Image_CVPR_2024_paper.html.
[3] Kingma D P, Ba J L. Adam: A method for stochastic optimization[PP/OL]. arXiv(2014-12-22)[2024-09-30]. https://arxiv.org/abs/1412.6980.
```

### 查证链接表
| 序号 | 文献题名 | 查证链接 | 链接类型 | 备注 |
|:----:|----------|----------|----------|------|
| 1 | 题名 | [链接](URL) | 会议官方 | 正常 |
| 2 | 题名 | [链接](URL) | 预印本 | ⚠️无会议链接 |

## 使用示例

### 示例1：会议录文献（电子资源）
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

### 示例3：期刊论文（电子资源）
**输入**：Veen P Hvd et al. Longitudinal changes in brain volumes, J Neurol Sci 2014

**输出**：
```
[1] Veen P Hvd, Muller M, Vincken K L, et al. Longitudinal changes in brain volumes and cerebrovascular lesions on MRI in patients with manifest arterial disease: the SMART-MR study[J/OL]. J Neurol Sci, 2014, 337(1/2): 112-118. https://pubmed.ncbi.nlm.nih.gov/24314719/. DOI:10.1016/j.jns.2013.11.029.
```

## 文档结构

```
academic-paper-verifier/
├── SKILL.md                                  # 技能主入口与工作流程
├── README.md                                 # 项目说明
├── CHANGELOG.md                              # 版本变更记录
├── LICENSE                                   # MIT 许可证
├── CONTRIBUTING.md                           # 贡献指南
└── references/
    ├── gbt7714-2025-core-rules.md            # GB/T 7714-2025标准核心规则
    ├── citation-formats.md                   # 各类型文献著录格式详解
    └── troubleshooting.md                    # 错误排查与辅助规则
```

### 文件职责分工

| 文件 | 职责 | 内容特点 |
|------|------|----------|
| `SKILL.md` | 技能主入口，工作流程 | 面向技能使用者，精简实用 |
| `references/gbt7714-2025-core-rules.md` | 标准核心规则 | 完整权威，作为规则依据 |
| `references/citation-formats.md` | 格式详细指南 | 实用导向，便于查阅套用 |
| `references/troubleshooting.md` | 错误排查指南 | 问题导向，帮助排查解决 |

## 参考标准

- **标准编号**：GB/T 7714-2025《信息与文献 参考文献著录规则》
- **实施日期**：2026-07-01
- **替代标准**：GB/T 7714-2015

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