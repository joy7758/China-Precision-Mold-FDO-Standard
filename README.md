# China Precision Mold FDO Standard (CPM-FDO)
# 中国精密模具 FDO 标准 (CPM-FDO)

<!-- SEARCH_VISIBILITY_BEGIN -->
## Discoverability Snapshot / 检索曝光摘要

- Standard ID / 标准编号: `RR-CPM`
- Repository / 仓库名: `China-Precision-Mold-FDO-Standard`

### EN Summary / 英文摘要
Precision manufacturing domain standard for FAIR Digital Objects and DOIP interoperability.

### CN Summary / 中文摘要
面向精密制造场景的FDO与DOIP互操作标准。

### SEO Keywords / 检索关键词
`precision-mold`, `fdo`, `doip`, `industrial-data`, `interoperability`

### Suggested Search Phrases (EN)
- China-Precision-Mold-FDO-Standard RR-CPM open standard
- China-Precision-Mold-FDO-Standard precision-mold fdo github
- RR-CPM precision-mold reference implementation

### 建议检索短语（中文）
- China-Precision-Mold-FDO-Standard RR-CPM 标准 规范
- China-Precision-Mold-FDO-Standard precision-mold fdo 仓库
- RR-CPM 参考实现 红岩 宪章

### Quick Links / 快速入口
- Governance Hub / 总入口: https://github.com/joy7758/RedRock-Constitution
- Standards Registry / 标准注册表: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-cpm
- Repos Index / 仓库索引: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md
- Ecosystem Graph / 生态关系图: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md
- Onepager / 一页纸: https://github.com/joy7758/China-Precision-Mold-FDO-Standard/blob/main/docs/onepager/RR-CPM_ONEPAGER_CN_EN.md
- Citation / 引用元数据: `CITATION.cff`
- Security Policy / 安全策略: `SECURITY.md`
- Machine-readable / 机器可读: `machine-readable/repository.json`
<!-- SEARCH_VISIBILITY_END -->

## Bilingual Governance Notice

## Standard Domain Entry / 标准域入口

- Standard ID / 标准编号：`RR-CPM`
- Registry Row / 注册表定位：https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-cpm
- Hub / 总入口：https://github.com/joy7758/RedRock-Constitution
- Onepager / 一页纸：`docs/onepager/RR-CPM_ONEPAGER_CN_EN.md`

**CN**: 所有标准文档均以中文与英文同步发布，英文为完整翻译版本。  
**EN**: All standards are published in Chinese and English, and the English content must be a full translation.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18497089.svg)](https://doi.org/10.5281/zenodo.18497089)

## 1. Abstract / 摘要

The CPM-FDO project establishes a technical framework for transforming precision industrial molds into FAIR Digital Objects (FDOs). By encapsulating physical mold fatigue indices, residual value algorithms, and lifecycle telemetry into machine-actionable units, this standard enables seamless financial assetization (movable property pledge) and cross-border semantic interoperability under the DOIP 2.0 protocol.

CPM-FDO 项目建立了一个将精密工业模具转化为 FAIR 数字对象 (FDO) 的技术框架。通过将物理模具的疲劳指数、残值算法和生命周期遥测数据封装为机器可操作单元，该标准在 DOIP 2.0 协议下实现了无缝的金融资产化（动产质押）和跨境语义互操作性。

## 2. Architecture & Protocol Stack / 架构与协议栈

This implementation adheres strictly to the FDO Core Model to ensure data is Findable, Accessible, Interoperable, and Reusable by machines.

本实现严格遵守 FDO 核心模型，以确保数据可被机器查找、访问、互操作和重用。

- **Persistent Identifier (PID) / 持久标识符**: Managed via Handle System (Prefix `20.500.XXXX/MOLD` - MPACN 2026 Batch). / 通过 Handle 系统管理（前缀 `20.500.XXXX/MOLD` - MPACN 2026 批次）。
- **Interface Protocol / 接口协议**: Digital Object Interface Protocol (DOIP) v2.0. / 数字对象接口协议 (DOIP) v2.0。
- **Metadata Kernel / 元数据内核**: JSON-LD 1.1 with focus on manufacturing fatigue semantics. / 专注于制造疲劳语义的 JSON-LD 1.1。
- **Security / 安全性**: Attribute-Based Access Control (ABAC) integrated at the DOIP level for sovereign data protection. / 在 DOIP 层集成的基于属性的访问控制 (ABAC)，用于主权数据保护。

## 3. Machine-Actionability Implementation / 机器可操作实现

Unlike traditional databases, CPM-FDO provides "Active Objects":
与传统数据库不同，CPM-FDO 提供“主动对象”：

- **Self-Describing / 自描述**: Each FDO contains a reference to its profile (Type), allowing AI agents to interpret mold wear-and-tear without external documentation.
每个 FDO 包含对其配置文件（类型）的引用，允许 AI 代理无需外部文档即可解释模具磨损情况。
- **Autonomous Operations / 自主操作**: Custom DOIP operations like `Op.CalculateResidualValue` allow financial institutions to query the real-time value of an asset directly from its PID.
自定义 DOIP 操作（如 `Op.CalculateResidualValue`）允许金融机构直接从 PID 查询资产的实时价值。

## 4. Repository Structure / 仓库结构

```plaintext
├── profiles/           # FDO Profiles & Type definitions / FDO 配置文件与类型定义
├── schemas/            # JSON-LD schemas for industrial assets / 工业资产的 JSON-LD 模式
│   └── mold-fatigue-v1.jsonld
├── implementation/     # Cordra/LHS configuration files / Cordra/LHS 配置文件
├── scripts/            # DOIP interaction tools (Python/Node.js) / DOIP 交互工具
└── docs/               # Technical specs and FDO Forum proposals / 技术规范与 FDO 论坛提案
```

## 5. Deployment (Node Initialization) / 部署（节点初始化）

To initialize a local FDO node for precision mold tracking:
要初始化用于精密模具追踪的本地 FDO 节点：

```bash
# Pull the FDO-compliant Cordra instance
# 拉取符合 FDO 标准的 Cordra 实例
docker pull cnri/cordra:latest

# Deploy with CPM-FDO configuration
# 使用 CPM-FDO 配置部署
docker run -d --name cpm-fdo-node \
  -v $(pwd)/config:/data/config \
  -p 8080:8080 -p 2641:2641 \
  cnri/cordra:latest
```

## 6. Strategic Roadmap (2026) / 战略路线图 (2026)

- **Q1**: Activation of Handle Prefix & Genesis FDO Minting. / 激活 Handle 前缀与创世 FDO 铸造。
- **Q2**: DOIP-MCP (Model Context Protocol) Integration for LLM-native asset querying. / DOIP-MCP (模型上下文协议) 集成，用于 LLM 原生资产查询。
- **Q3**: Pilot deployment with Tier-1 Commercial Banks for automated asset-backed financing. / 与一级商业银行进行试点部署，实现自动化资产支持融资。

---

## Belongs to RedRock Constitution / 隶属于红岩宪章体系

This repository is part of the RedRock Constitution architecture framework.

Please start from the central governance hub:

https://github.com/joy7758/RedRock-Constitution

本仓库属于红岩宪章体系，请从总入口开始阅读与理解：

https://github.com/joy7758/RedRock-Constitution

---

## Standard Domain / 标准域

This repository implements Standard Domain `RR-CPM` under the RedRock Constitution framework.

本仓库实现红岩宪章标准域：`RR-CPM`

Central Governance Hub:
https://github.com/joy7758/RedRock-Constitution

## Onepager / 一页纸

- `RR-CPM` Onepager / 一页纸：`docs/onepager/RR-CPM_ONEPAGER_CN_EN.md`
- Hub / 总入口：https://github.com/joy7758/RedRock-Constitution

<!-- ECOSYSTEM_LINKS_BEGIN -->
## Ecosystem Links / 生态关系链接

![quality-baseline](https://github.com/joy7758/China-Precision-Mold-FDO-Standard/actions/workflows/quality-baseline.yml/badge.svg)

### CN
- 总入口（宪章）：[RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)
- 标准注册表：[STANDARDS_REGISTRY](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-cpm)
- 仓库总索引：[REPOS_INDEX_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md)
- 全局生态图：[ECOSYSTEM_GRAPH_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md)
- 机器可读元数据：[`machine-readable/repository.json`](machine-readable/repository.json)

### EN
- Governance hub: [RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)
- Standards registry: [STANDARDS_REGISTRY](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-cpm)
- Repositories index: [REPOS_INDEX_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md)
- Global ecosystem graph: [ECOSYSTEM_GRAPH_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md)
- Machine-readable metadata: [`machine-readable/repository.json`](machine-readable/repository.json)

### Related Repositories / 关联仓库
- [DOIP-Segments-Specification](https://github.com/joy7758/DOIP-Segments-Specification)
- [pFDO-Specification](https://github.com/joy7758/pFDO-Specification)
- [RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)

### Search Keywords / 检索关键词
`precision-mold`, `fdo`, `doip`, `industrial-data`, `interoperability`

### Bilingual Project Abstract / 双语项目摘要
- EN: Precision manufacturing domain standard for FAIR Digital Objects and DOIP interoperability.
- CN: 面向精密制造场景的FDO与DOIP互操作标准。
<!-- ECOSYSTEM_LINKS_END -->
