# database-access skill

`database-access` 是一个面向 Codex 的生物信息学技能包，主要用于访问 NCBI、UniProt、SRA、GEO 等公共数据库，并支持序列下载、远程 BLAST 检索以及相关数据获取工作流。

本仓库将上游 `GPTomics/bioSkills` 中的 `database-access` 内容整理为可直接被 Codex 识别的独立 skill，便于单独安装、复用与版本管理。

## 功能概览

该 skill 适合以下任务场景：

- 检索 NCBI 数据库中的文献、基因、核酸或蛋白记录
- 根据 accession 或 ID 批量获取条目内容
- 下载 SRA 测序数据或查询 GEO 数据集
- 调用远程 BLAST 进行序列相似性搜索
- 访问 UniProt 并进行 ID 映射或批量检索
- 作为后续序列分析、比对、注释流程的数据获取入口

## 主要能力

- `entrez-search`：搜索 NCBI 数据库
- `entrez-fetch`：按 ID 拉取记录
- `entrez-link`：进行数据库间关联查询
- `batch-downloads`：批量下载与历史记录服务
- `sra-data`：下载 SRA 数据
- `geo-data`：检索 GEO 数据集
- `blast-searches`：执行远程 BLAST 搜索
- `local-blast`：本地 BLAST 数据库与检索
- `sequence-similarity`：PSI-BLAST、HMMER 等相似性分析入口
- `uniprot-access`：UniProt 检索与 ID 映射
- `interaction-databases`：STRING、BioGRID、IntAct 等互作数据库访问

## 安装方法

将本仓库内容放入你的 Codex skills 目录中，目标路径通常为：

```text
~/.codex/skills/database-access
```

如果你已经克隆了本仓库，也可以直接复制整个目录到上述位置。

安装完成后，重启 Codex 以加载新 skill。

## 目录结构

```text
database-access-skill/
├─ README.md
├─ SKILL.md
└─ SOURCE.md
```

- `README.md`：仓库说明文档
- `SKILL.md`：Codex 可识别的技能定义文件
- `SOURCE.md`：上游来源说明

## 依赖说明

该 skill 的完整能力通常依赖以下工具或库：

```bash
pip install biopython
conda install -c bioconda sra-tools
conda install -c bioconda blast
conda install -c bioconda hmmer
```

其中：

- `biopython` 用于 Entrez、BLAST 等 Python 接口访问
- `sra-tools` 用于下载 SRA 数据
- `blast` 用于本地 BLAST 检索
- `hmmer` 用于更深入的序列相似性分析

## 上游来源

本仓库内容整理自以下上游目录：

`https://github.com/GPTomics/bioSkills/tree/ebe4f4003ebeef4beda84ae1fb4f52295848c4e1/database-access`

需要说明的是，上游目录提供的是 `README.md`，而不是 Codex 原生可安装格式的 `SKILL.md`。因此本仓库对其进行了适配封装，使其可以作为独立 skill 被直接安装和使用。

## 使用建议

在 Codex 中可围绕以下类型的问题触发本 skill：

- “帮我搜索 NCBI 上与 CRISPR 相关的 2024 年文献”
- “下载人类 TP53 的 RefSeq mRNA 序列”
- “获取 SRA accession 为 `SRR12345678` 的 FASTQ 数据”
- “查询 BRCA1 在 UniProt 中对应的蛋白条目”
- “对这段蛋白序列执行远程 BLAST 搜索”

## 许可与说明

本仓库主要用于将公开资料整理为 Codex 可用的技能结构，便于个人研究、教学与工作流集成使用。实际数据访问能力和可用性仍取决于相关数据库服务状态、网络环境以及本地依赖安装情况。
