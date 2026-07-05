# Blog CMC VRR Article Index

Blog CMC VRR Article Index 是一个面向技术研究人员、内容策展人与知识工作者的结构化文章索引项目。该项目对 `blog.cmcvrr.cn` 平台上的公开技术文章进行系统化梳理，按文章 ID 建立索引目录，并提供统一的资源导航入口，帮助用户在海量内容中快速定位、检索与引用目标文章。

本项目适用于需要批量查阅或定期跟踪 `blog.cmcvrr.cn` 更新动态的用户，尤其适合作为个人知识库的外部资源挂载点，或作为自动化采集流程的种子列表。项目本身不存储任何文章内容，仅提供公开 URL 的整理与分类服务。

## 功能概览

**批量 URL 索引**：提供超过 250 条 `blog.cmcvrr.cn` 文章链接的完整清单，按文章 ID 升序排列，方便检索。

**多维度分类导航**：根据文章 ID 段、主题关键词与内容类型，对资源进行逻辑分组，满足不同场景下的筛选需求。

**自动化采集友好**：所有 URL 保持原始格式，无重定向、无跟踪参数，可直接用于爬虫、脚本或书签导入。

**轻量化快速部署**：项目本身为纯静态 Markdown 文档，无需数据库或后端服务，克隆即可使用。

**定期维护机制**：随源站文章更新，项目维护者定期校验链接可用性，标记失效或变更的条目。

**开放贡献通道**：接受用户提交的新链接推荐、分类建议与错误修正，形成社区驱动的索引质量保障。

## 应用场景

**技术文献回溯**：研究人员可通过本索引快速查找特定 ID 段的历史技术文章，用于文献综述或技术演进分析。

**自动化内容监控**：运维人员可编写定时脚本读取本索引，与源站进行对比，自动发现新增或下线的文章，实现内容变更告警。

**个人知识库挂载**：知识管理工具（如 Obsidian、Notion）的用户可将本索引作为外部数据源，批量导入文章链接并配合内容抓取插件进行离线阅读。

**团队协作共享**：技术团队可将本索引作为内部技术周报的素材池，成员按分类认领文章进行精读与分享，降低信息发现成本。

## 快速开始

以下命令演示了如何将本项目克隆到本地并完成初始环境配置。

```bash
# 克隆项目仓库
git clone https://github.com/your-org/blog-cmcvrr-index.git

# 进入项目目录
cd blog-cmcvrr-index

# 安装依赖（若需要本地预览工具，如 markdownlint、link-checker 等）
npm install -g markdown-link-check
npm install -g markdownlint-cli

# 执行链接有效性检查（可选）
markdown-link-check README.md
```

完成上述步骤后，用户可直接打开 `README.md` 或 `INDEX.md` 文件，浏览全部索引条目。若需将索引导入其他应用程序，可编写简单的解析脚本读取 Markdown 列表中的 URL。

## 安装要求

本项目作为静态文档集合，本身无运行时代码依赖。但若用户希望参与贡献或执行本地校验，建议安装以下工具链。

| 依赖组件 | 必需性 | 说明 |
|---|---|---|
| Git | 必需 | 用于克隆仓库与提交变更 |
| Markdown 阅读器 | 必需 | 任何支持 Markdown 渲染的编辑器或浏览器均可 |
| markdown-link-check | 可选 | 用于批量检测索引中的 URL 是否可访问 |
| markdownlint-cli | 可选 | 用于检查 Markdown 文档格式规范性 |
| Python 3.x + requests | 可选 | 运行社区提供的辅助脚本，进行批量状态码检查 |
| curl / wget | 可选 | 单条链接快速测试工具 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 项目概览 | README.md | 项目的定位、目标用户与核心功能是什么？ |
| 资源索引 | INDEX.md | 全部文章链接列表，按 ID 排序，包含哪些条目？ |
| 分类映射 | CATEGORIES.md | 文章按主题分为哪些类别，每个类别下包含哪些 ID 段？ |
| 变更日志 | CHANGELOG.md | 每次索引更新新增或移除了哪些链接，维护记录如何？ |
| 贡献指南 | CONTRIBUTING.md | 如何提交新链接、报告失效链接或建议分类调整？ |

## 资源列表

### 核心文章索引（按 ID 升序排列）

http://www.blog.cmcvrr.cn/Article/details/00859.sHtML
http://www.blog.cmcvrr.cn/Article/details/00884.sHtML
http://www.blog.cmcvrr.cn/Article/details/0118.sHtML
http://www.blog.cmcvrr.cn/Article/details/01318.sHtML
http://www.blog.cmcvrr.cn/Article/details/0180.sHtML
http://www.blog.cmcvrr.cn/Article/details/01811.sHtML
http://www.blog.cmcvrr.cn/Article/details/0321597.sHtML
http://www.blog.cmcvrr.cn/Article/details/03242.sHtML
http://www.blog.cmcvrr.cn/Article/details/0350411.sHtML
http://www.blog.cmcvrr.cn/Article/details/036096.sHtML
http://www.blog.cmcvrr.cn/Article/details/0383.sHtML
http://www.blog.cmcvrr.cn/Article/details/0421986.sHtML
http://www.blog.cmcvrr.cn/Article/details/0519.sHtML
http://www.blog.cmcvrr.cn/Article/details/059807.sHtML
http://www.blog.cmcvrr.cn/Article/details/0647121.sHtML
http://www.blog.cmcvrr.cn/Article/details/0656034.sHtML
http://www.blog.cmcvrr.cn/Article/details/0659616.sHtML
http://www.blog.cmcvrr.cn/Article/details/069408.sHtML
http://www.blog.cmcvrr.cn/Article/details/069704.sHtML
http://www.blog.cmcvrr.cn/Article/details/0830.sHtML
http://www.blog.cmcvrr.cn/Article/details/1033364.sHtML
http://www.blog.cmcvrr.cn/Article/details/10703.sHtML
http://www.blog.cmcvrr.cn/Article/details/1103.sHtML
http://www.blog.cmcvrr.cn/Article/details/1110.sHtML
http://www.blog.cmcvrr.cn/Article/details/1111.sHtML
http://www.blog.cmcvrr.cn/Article/details/1116250.sHtML
http://www.blog.cmcvrr.cn/Article/details/1156.sHtML
http://www.blog.cmcvrr.cn/Article/details/12015.sHtML
http://www.blog.cmcvrr.cn/Article/details/127005.sHtML
http://www.blog.cmcvrr.cn/Article/details/1297991.sHtML
http://www.blog.cmcvrr.cn/Article/details/1307403.sHtML
http://www.blog.cmcvrr.cn/Article/details/1328.sHtML
http://www.blog.cmcvrr.cn/Article/details/133154.sHtML
http://www.blog.cmcvrr.cn/Article/details/1374.sHtML
http://www.blog.cmcvrr.cn/Article/details/140408.sHtML
http://www.blog.cmcvrr.cn/Article/details/14117.sHtML
http://www.blog.cmcvrr.cn/Article/details/14401.sHtML
http://www.blog.cmcvrr.cn/Article/details/1454191.sHtML
http://www.blog.cmcvrr.cn/Article/details/1507121.sHtML
http://www.blog.cmcvrr.cn/Article/details/1575.sHtML
http://www.blog.cmcvrr.cn/Article/details/15856.sHtML
http://www.blog.cmcvrr.cn/Article/details/1590195.sHtML
http://www.blog.cmcvrr.cn/Article/details/1658.sHtML
http://www.blog.cmcvrr.cn/Article/details/1710.sHtML
http://www.blog.cmcvrr.cn/Article/details/1717744.sHtML
http://www.blog.cmcvrr.cn/Article/details/17286.sHtML
http://www.blog.cmcvrr.cn/Article/details/178774.sHtML
http://www.blog.cmcvrr.cn/Article/details/181040.sHtML
http://www.blog.cmcvrr.cn/Article/details/1812.sHtML
http://www.blog.cmcvrr.cn/Article/details/1869813.sHtML
http://www.blog.cmcvrr.cn/Article/details/1870.sHtML
http://www.blog.cmcvrr.cn/Article/details/1872.sHtML
http://www.blog.cmcvrr.cn/Article/details/1888507.sHtML
http://www.blog.cmcvrr.cn/Article/details/1942.sHtML
http://www.blog.cmcvrr.cn/Article/details/198345.sHtML
http://www.blog.cmcvrr.cn/Article/details/20165.sHtML
http://www.blog.cmcvrr.cn/Article/details/20174.sHtML
http://www.blog.cmcvrr.cn/Article/details/20375.sHtML
http://www.blog.cmcvrr.cn/Article/details/207573.sHtML
http://www.blog.cmcvrr.cn/Article/details/2118139.sHtML
http://www.blog.cmcvrr.cn/Article/details/2127872.sHtML
http://www.blog.cmcvrr.cn/Article/details/2131598.sHtML
http://www.blog.cmcvrr.cn/Article/details/213501.sHtML
http://www.blog.cmcvrr.cn/Article/details/2186482.sHtML
http://www.blog.cmcvrr.cn/Article/details/227712.sHtML
http://www.blog.cmcvrr.cn/Article/details/2297778.sHtML
http://www.blog.cmcvrr.cn/Article/details/2319843.sHtML
http://www.blog.cmcvrr.cn/Article/details/25257.sHtML
http://www.blog.cmcvrr.cn/Article/details/2541.sHtML
http://www.blog.cmcvrr.cn/Article/details/2572.sHtML
http://www.blog.cmcvrr.cn/Article/details/2602248.sHtML
http://www.blog.cmcvrr.cn/Article/details/2794012.sHtML
http://www.blog.cmcvrr.cn/Article/details/2819158.sHtML
http://www.blog.cmcvrr.cn/Article/details/28305.sHtML
http://www.blog.cmcvrr.cn/Article/details/284134.sHtML
http://www.blog.cmcvrr.cn/Article/details/29017.sHtML
http://www.blog.cmcvrr.cn/Article/details/293688.sHtML
http://www.blog.cmcvrr.cn/Article/details/3059.sHtML
http://www.blog.cmcvrr.cn/Article/details/31450.sHtML
http://www.blog.cmcvrr.cn/Article/details/3165651.sHtML
http://www.blog.cmcvrr.cn/Article/details/3175.sHtML
http://www.blog.cmcvrr.cn/Article/details/321815.sHtML
http://www.blog.cmcvrr.cn/Article/details/3308.sHtML
http://www.blog.cmcvrr.cn/Article/details/33094.sHtML
http://www.blog.cmcvrr.cn/Article/details/3325.sHtML
http://www.blog.cmcvrr.cn/Article/details/336439.sHtML
http://www.blog.cmcvrr.cn/Article/details/3478.sHtML
http://www.blog.cmcvrr.cn/Article/details/355571.sHtML
http://www.blog.cmcvrr.cn/Article/details/35642.sHtML
http://www.blog.cmcvrr.cn/Article/details/358442.sHtML
http://www.blog.cmcvrr.cn/Article/details/362952.sHtML
http://www.blog.cmcvrr.cn/Article/details/363857.sHtML
http://www.blog.cmcvrr.cn/Article/details/370551.sHtML
http://www.blog.cmcvrr.cn/Article/details/3772283.sHtML
http://www.blog.cmcvrr.cn/Article/details/3813580.sHtML
http://www.blog.cmcvrr.cn/Article/details/38975.sHtML
http://www.blog.cmcvrr.cn/Article/details/3985976.sHtML
http://www.blog.cmcvrr.cn/Article/details/4029.sHtML
http://www.blog.cmcvrr.cn/Article/details/4113359.sHtML
http://www.blog.cmcvrr.cn/Article/details/415161.sHtML
http://www.blog.cmcvrr.cn/Article/details/441297.sHtML
http://www.blog.cmcvrr.cn/Article/details/444168.sHtML
http://www.blog.cmcvrr.cn/Article/details/444650.sHtML
http://www.blog.cmcvrr.cn/Article/details/445365.sHtML
http://www.blog.cmcvrr.cn/Article/details/445610.sHtML
http://www.blog.cmcvrr.cn/Article/details/4460.sHtML
http://www.blog.cmcvrr.cn/Article/details/4487.sHtML
http://www.blog.cmcvrr.cn/Article/details/45033.sHtML
http://www.blog.cmcvrr.cn/Article/details/465077.sHtML
http://www.blog.cmcvrr.cn/Article/details/4656858.sHtML
http://www.blog.cmcvrr.cn/Article/details/46987.sHtML
http://www.blog.cmcvrr.cn/Article/details/4717.sHtML
http://www.blog.cmcvrr.cn/Article/details/47426.sHtML
http://www.blog.cmcvrr.cn/Article/details/4799667.sHtML
http://www.blog.cmcvrr.cn/Article/details/48037.sHtML
http://www.blog.cmcvrr.cn/Article/details/48136.sHtML
http://www.blog.cmcvrr.cn/Article/details/4845.sHtML
http://www.blog.cmcvrr.cn/Article/details/499697.sHtML
http://www.blog.cmcvrr.cn/Article/details/5050.sHtML
http://www.blog.cmcvrr.cn/Article/details/5157673.sHtML
http://www.blog.cmcvrr.cn/Article/details/520934.sHtML
http://www.blog.cmcvrr.cn/Article/details/52642.sHtML
http://www.blog.cmcvrr.cn/Article/details/5357549.sHtML
http://www.blog.cmcvrr.cn/Article/details/536157.sHtML
http://www.blog.cmcvrr.cn/Article/details/5377686.sHtML
http://www.blog.cmcvrr.cn/Article/details/5400.sHtML
http://www.blog.cmcvrr.cn/Article/details/5421562.sHtML
http://www.blog.cmcvrr.cn/Article/details/546796.sHtML
http://www.blog.cmcvrr.cn/Article/details/54931.sHtML
http://www.blog.cmcvrr.cn/Article/details/55126.sHtML
http://www.blog.cmcvrr.cn/Article/details/555739.sHtML
http://www.blog.cmcvrr.cn/Article/details/5624.sHtML
http://www.blog.cmcvrr.cn/Article/details/56579.sHtML
http://www.blog.cmcvrr.cn/Article/details/5803450.sHtML
http://www.blog.cmcvrr.cn/Article/details/5820376.sHtML
http://www.blog.cmcvrr.cn/Article/details/58364.sHtML
http://www.blog.cmcvrr.cn/Article/details/5839528.sHtML
http://www.blog.cmcvrr.cn/Article/details/58838.sHtML
http://www.blog.cmcvrr.cn/Article/details/5910241.sHtML
http://www.blog.cmcvrr.cn/Article/details/5998070.sHtML
http://www.blog.cmcvrr.cn/Article/details/60029.sHtML
http://www.blog.cmcvrr.cn/Article/details/6033.sHtML
http://www.blog.cmcvrr.cn/Article/details/604738.sHtML
http://www.blog.cmcvrr.cn/Article/details/612651.sHtML
http://www.blog.cmcvrr.cn/Article/details/6132515.sHtML
http://www.blog.cmcvrr.cn/Article/details/61332.sHtML
http://www.blog.cmcvrr.cn/Article/details/62073.sHtML
http://www.blog.cmcvrr.cn/Article/details/6214.sHtML
http://www.blog.cmcvrr.cn/Article/details/625866.sHtML
http://www.blog.cmcvrr.cn/Article/details/6276.sHtML
http://www.blog.cmcvrr.cn/Article/details/63196.sHtML
http://www.blog.cmcvrr.cn/Article/details/6344.sHtML
http://www.blog.cmcvrr.cn/Article/details/6397.sHtML
http://www.blog.cmcvrr.cn/Article/details/6467863.sHtML
http://www.blog.cmcvrr.cn/Article/details/657104.sHtML
http://www.blog.cmcvrr.cn/Article/details/6796911.sHtML
http://www.blog.cmcvrr.cn/Article/details/68122.sHtML
http://www.blog.cmcvrr.cn/Article/details/696340.sHtML
http://www.blog.cmcvrr.cn/Article/details/7001616.sHtML
http://www.blog.cmcvrr.cn/Article/details/704032.sHtML
http://www.blog.cmcvrr.cn/Article/details/7043.sHtML
http://www.blog.cmcvrr.cn/Article/details/7054138.sHtML
http://www.blog.cmcvrr.cn/Article/details/706171.sHtML
http://www.blog.cmcvrr.cn/Article/details/7185317.sHtML
http://www.blog.cmcvrr.cn/Article/details/7216731.sHtML
http://www.blog.cmcvrr.cn/Article/details/7226358.sHtML
http://www.blog.cmcvrr.cn/Article/details/724478.sHtML
http://www.blog.cmcvrr.cn/Article/details/7249.sHtML
http://www.blog.cmcvrr.cn/Article/details/7269934.sHtML
http://www.blog.cmcvrr.cn/Article/details/73333.sHtML
http://www.blog.cmcvrr.cn/Article/details/73404.sHtML
http://www.blog.cmcvrr.cn/Article/details/740069.sHtML
http://www.blog.cmcvrr.cn/Article/details/74075.sHtML
http://www.blog.cmcvrr.cn/Article/details/7445.sHtML
http://www.blog.cmcvrr.cn/Article/details/74670.sHtML
http://www.blog.cmcvrr.cn/Article/details/7484.sHtML
http://www.blog.cmcvrr.cn/Article/details/7512966.sHtML
http://www.blog.cmcvrr.cn/Article/details/7531.sHtML
http://www.blog.cmcvrr.cn/Article/details/75574.sHtML
http://www.blog.cmcvrr.cn/Article/details/760178.sHtML
http://www.blog.cmcvrr.cn/Article/details/7611705.sHtML
http://www.blog.cmcvrr.cn/Article/details/77096.sHtML
http://www.blog.cmcvrr.cn/Article/details/773929.sHtML
http://www.blog.cmcvrr.cn/Article/details/7746.sHtML
http://www.blog.cmcvrr.cn/Article/details/774625.sHtML
http://www.blog.cmcvrr.cn/Article/details/7787510.sHtML
http://www.blog.cmcvrr.cn/Article/details/7813341.sHtML
http://www.blog.cmcvrr.cn/Article/details/7819988.sHtML
http://www.blog.cmcvrr.cn/Article/details/784380.sHtML
http://www.blog.cmcvrr.cn/Article/details/78639.sHtML
http://www.blog.cmcvrr.cn/Article/details/79355.sHtML
http://www.blog.cmcvrr.cn/Article/details/79792.sHtML
http://www.blog.cmcvrr.cn/Article/details/8008221.sHtML
http://www.blog.cmcvrr.cn/Article/details/802899.sHtML
http://www.blog.cmcvrr.cn/Article/details/81664.sHtML
http://www.blog.cmcvrr.cn/Article/details/817555.sHtML
http://www.blog.cmcvrr.cn/Article/details/824256.sHtML
http://www.blog.cmcvrr.cn/Article/details/8279.sHtML
http://www.blog.cmcvrr.cn/Article/details/8284383.sHtML
http://www.blog.cmcvrr.cn/Article/details/828519.sHtML
http://www.blog.cmcvrr.cn/Article/details/829748.sHtML
http://www.blog.cmcvrr.cn/Article/details/8308.sHtML
http://www.blog.cmcvrr.cn/Article/details/8316.sHtML
http://www.blog.cmcvrr.cn/Article/details/8342.sHtML
http://www.blog.cmcvrr.cn/Article/details/8354.sHtML
http://www.blog.cmcvrr.cn/Article/details/8408058.sHtML
http://www.blog.cmcvrr.cn/Article/details/8415509.sHtML
http://www.blog.cmcvrr.cn/Article/details/8478955.sHtML
http://www.blog.cmcvrr.cn/Article/details/85275.sHtML
http://www.blog.cmcvrr.cn/Article/details/8565145.sHtML
http://www.blog.cmcvrr.cn/Article/details/8576319.sHtML
http://www.blog.cmcvrr.cn/Article/details/8586092.sHtML
http://www.blog.cmcvrr.cn/Article/details/859749.sHtML
http://www.blog.cmcvrr.cn/Article/details/86010.sHtML
http://www.blog.cmcvrr.cn/Article/details/8653.sHtML
http://www.blog.cmcvrr.cn/Article/details/86683.sHtML
http://www.blog.cmcvrr.cn/Article/details/8682.sHtML
http://www.blog.cmcvrr.cn/Article/details/871689.sHtML
http://www.blog.cmcvrr.cn/Article/details/8740.sHtML
http://www.blog.cmcvrr.cn/Article/details/8754335.sHtML
http://www.blog.cmcvrr.cn/Article/details/8793205.sHtML
http://www.blog.cmcvrr.cn/Article/details/88089.sHtML
http://www.blog.cmcvrr.cn/Article/details/8834310.sHtML
http://www.blog.cmcvrr.cn/Article/details/8864.sHtML
http://www.blog.cmcvrr.cn/Article/details/8911039.sHtML
http://www.blog.cmcvrr.cn/Article/details/89316.sHtML
http://www.blog.cmcvrr.cn/Article/details/9044.sHtML
http://www.blog.cmcvrr.cn/Article/details/9077212.sHtML
http://www.blog.cmcvrr.cn/Article/details/9114.sHtML
http://www.blog.cmcvrr.cn/Article/details/9175.sHtML
http://www.blog.cmcvrr.cn/Article/details/91777.sHtML
http://www.blog.cmcvrr.cn/Article/details/9178565.sHtML
http://www.blog.cmcvrr.cn/Article/details/9269900.sHtML
http://www.blog.cmcvrr.cn/Article/details/935253.sHtML
http://www.blog.cmcvrr.cn/Article/details/93628.sHtML
http://www.blog.cmcvrr.cn/Article/details/9485461.sHtML
http://www.blog.cmcvrr.cn/Article/details/9503689.sHtML
http://www.blog.cmcvrr.cn/Article/details/95062.sHtML
http://www.blog.cmcvrr.cn/Article/details/95465.sHtML
http://www.blog.cmcvrr.cn/Article/details/9624517.sHtML
http://www.blog.cmcvrr.cn/Article/details/97151.sHtML
http://www.blog.cmcvrr.cn/Article/details/974222.sHtML
http://www.blog.cmcvrr.cn/Article/details/97471.sHtML
http://www.blog.cmcvrr.cn/Article/details/97612.sHtML
http://www.blog.cmcvrr.cn/Article/details/9841.sHtML
http://www.blog.cmcvrr.cn/Article/details/986883.sHtML
http://www.blog.cmcvrr.cn/Article/details/98776.sHtML
http://www.blog.cmcvrr.cn/Article/details/998990.sHtML

## 项目结构

```
blog-cmcvrr-index/
├── README.md                     # 项目总体说明与快速入门
├── INDEX.md                      # 全部文章链接清单，按 ID 升序排列
├── CATEGORIES.md                 # 文章分类映射表，按技术领域分组
├── CHANGELOG.md                  # 版本更新记录，标注每次增删的 ID 范围
├── CONTRIBUTING.md               # 贡献者指南，包含提交规范与流程
├── scripts/
│   ├── check_links.py            # Python 脚本，批量检测 URL 状态码
│   ├── generate_index.py         # 从原始数据生成 INDEX.md 的自动化脚本
│   └── validate_urls.sh          # Shell 脚本，使用 curl 快速验证单条链接
├── data/
│   ├── raw_urls.txt              # 原始 URL 列表，供脚本读取
│   ├── known_issues.json         # 记录已知失效或重定向的链接
│   └── categories.yaml           # YAML 格式的分类规则定义
├── docs/
│   ├── api_usage.md              # 如何通过 API 风格方式引用本索引
│   └── integration_guide.md      # 将索引集成到 Obsidian、Notion 等工具的步骤
├── .github/
│   └── workflows/
│       └── link_check.yml        # GitHub Actions 定时任务，每周自动检测链接
├── .markdownlint.json            # markdownlint 配置文件，统一文档风格
└── LICENSE                       # MIT 许可证文件
```

## 贡献指南

**提交新链接**：若发现 `blog.cmcvrr.cn` 上存在未被收录的文章，请通过 Issue 提交完整的文章 URL，并简要说明文章主题。维护者将核对后合并至索引列表。

**报告失效链接**：若在浏览或使用索引过程中发现某条链接返回 404 或重定向至无关页面，请提交 Issue 并附上链接及检测时间。维护者将标记该条目并尝试寻找替代地址或将其移除。

**建议分类优化**：若对 `CATEGORIES.md` 中的分组方式有改进意见，例如合并重叠类别或新增细分领域，请提交 Pull Request 并附上修改说明与理由。

**完善自动化工具**：欢迎开发者对 `scripts/` 目录下的检查脚本进行性能优化、增加并发检测能力或支持代理配置，提升链接校验效率。

**更新文档示例**：若发现 `docs/` 中的集成指南存在过时步骤或遗漏的平台，请补充详细操作截图与命令行示例，帮助新用户降低上手难度。

## 常见问题

**问：本项目的索引更新频率是多少？**

答：索引本身不自动同步源站。维护者会根据用户反馈与定期人工审查，每两周至一个月进行一次批量更新。用户可关注 `CHANGELOG.md` 获知每次变更详情。若需实时监控，建议使用 `scripts/check_links.py` 结合定时任务自行实现。

**问：链接中的 `.sHtML` 后缀为何大小写不规则？**

答：这些 URL 系源站生成时即保持的原始格式。本项目遵循"原样收录"原则，不进行任何格式化改写，以确保与实际线上地址完全一致，避免因大小写变化导致的访问错误。

**问：能否通过本项目直接搜索文章标题或关键词？**

答：本项目当前仅提供基于文章 ID 的索引导航，不包含标题、摘要或全文搜索功能。用户可复制链接后访问源站页面，使用浏览器自带的页面内搜索进行内容查找。未来版本可能基于元数据扩展搜索能力。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 15:34:54
