# BlogLink Hub

BlogLink Hub 是一个面向技术内容聚合与外部资源索引的开源项目，定位于为开发者、技术博主及内容运营团队提供轻量级、可扩展的外链管理与导航系统。该项目通过结构化的数据组织方式，将分散于各技术博客、社区平台及官方文档中的优质文章、工具与参考链接进行统一收录与分类展示，帮助用户快速定位特定技术领域的深度内容。

项目核心目标用户包括：需要维护技术知识库的研发团队、希望构建个人技术导航站点的独立开发者、以及从事技术内容运营与SEO优化的市场人员。BlogLink Hub 不依赖任何商业API，所有链接数据以纯文本形式存储于项目仓库中，支持用户通过标准Markdown语法进行增删改查，并可通过CI/CD流水线自动生成静态导航页面。

## 功能概览

- **按技术领域分类索引**：系统预设后端开发、前端工程、运维监控、数据库、算法与数据结构等五大技术分类，每个分类下可挂载不限数量的外链，并支持用户自定义新增分类。

- **全文检索与模糊匹配**：基于链接标题、描述标签及来源域名构建轻量级倒排索引，支持用户通过关键词快速筛选目标资源，检索结果按相关性排序。

- **链接状态健康检查**：内置定时任务（默认每24小时执行一次），对已收录的所有外链发起HTTP HEAD请求，自动标记响应状态码非200或超时的链接为“失效”，并在导航页面中高亮提示。

- **批量导入与导出机制**：支持用户通过CSV或JSON格式批量导入外链数据，同时提供完整数据的导出功能，便于在不同系统间迁移或备份链接库。

- **访问热度统计看板**：基于自定义事件埋点（需用户自行部署前端SDK），记录每个外链的点击次数与最近访问时间，在管理后台生成热度排行与趋势图表。

- **标签体系与多维度筛选**：每条链接可关联多个自定义标签（如“教程”“视频”“官方文档”“开源项目”），用户可通过标签组合筛选快速缩小内容范围。

- **静态站点生成适配器**：项目核心数据层与渲染层解耦，内置针对Hugo、VuePress及纯HTML模板的渲染适配器，可一键生成符合SEO规范的静态导航站点。

## 应用场景

- **技术团队内部知识库导航**：研发团队可将日常开发中参考的框架文档、故障排查案例、性能优化指南等链接统一收录至 BlogLink Hub，新成员入职时通过导航站快速了解团队常用技术栈与最佳实践参考。

- **个人技术博客的友情链接与推荐阅读**：独立技术博主可使用该项目维护“推荐阅读”或“友情链接”页面，自动从收录的链接中随机选取高质量外部文章展示在博客侧边栏，提升读者留存与跨站互动。

- **开源项目官方文档的外链整合**：开源项目维护者可将项目依赖的第三方库文档、社区教程、视频讲解等资源通过 BlogLink Hub 集中管理，并在项目README或官网中嵌入导航页面链接，减少用户寻找辅助资料的时间成本。

- **技术社区运营的内容聚合**：技术社区运营人员可定期从社区投稿、技术大会演讲列表、GitHub Trending等渠道收集优质内容，通过 BlogLink Hub 构建每周或每月技术精选合集，并以邮件简报或社交媒体形式分发。

- **离线环境下的技术资料索引**：在无法访问互联网的内网开发环境中，运维人员可将常用的内部文档地址、离线包下载源、镜像站地址等收录至项目，配合内网静态部署，提供统一入口。

## 快速开始

以下操作基于 Linux/macOS 环境，假设系统已安装 Git、Node.js（v16+）及 npm。

```bash
# 克隆项目仓库至本地
git clone https://github.com/your-org/bloglink-hub.git
cd bloglink-hub

# 安装项目依赖（包含核心解析引擎、静态生成器及测试框架）
npm install

# 执行数据校验与静态站点生成，输出目录默认为 ./dist
npm run build

# 启动本地开发服务器，默认监听 http://localhost:3000
npm run serve
```

执行完上述步骤后，即可通过浏览器访问本地服务查看导航页面。如需修改链接数据，请编辑 `./data/links.json` 文件，调整后重新运行 `npm run build` 生成更新后的页面。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Node.js | >= 16.0.0 | 运行时环境，用于执行构建脚本及本地服务器 |
| npm | >= 8.0.0 | 包管理工具，用于安装项目所有依赖库 |
| Git | >= 2.30.0 | 版本控制工具，用于克隆仓库及后续更新拉取 |
| curl | >= 7.68.0 | 用于链接健康检查脚本中的HTTP请求发送（可选，可用内置Node模块替代） |
| sqlite3 | >= 3.31.0 | 用于本地缓存访问日志及统计分析（可配置关闭） |
| Python | >= 3.8.0 | 仅在使用扩展数据分析脚本时需要（核心功能不依赖） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户指南 | docs/user-guide/getting-started.md | 如何首次使用、配置数据源并生成第一个导航页面 |
| 用户指南 | docs/user-guide/customization.md | 如何修改页面主题、布局及自定义CSS样式 |
| 开发者指南 | docs/developer-guide/data-schema.md | 链接数据JSON Schema定义、字段含义及扩展字段说明 |
| 开发者指南 | docs/developer-guide/api-reference.md | 核心解析器、渲染器及过滤器模块的API文档 |
| 运维参考 | docs/operations/health-check.md | 链接健康检查的配置参数、执行周期及告警策略 |
| 运维参考 | docs/operations/deployment.md | 生产环境部署方案（Nginx、CDN、Docker容器化） |
| 贡献规范 | docs/contributing/code-style.md | JavaScript/TypeScript代码风格、提交信息格式及PR流程 |

## 资源列表

技术文章类

http://www.blog.jnjpgf.cn/Article/details/792730.sHtML
http://www.blog.jnjpgf.cn/Article/details/9791980.sHtML
http://www.blog.jnjpgf.cn/Article/details/9263.sHtML
http://www.blog.jnjpgf.cn/Article/details/725106.sHtML
http://www.blog.jnjpgf.cn/Article/details/76654.sHtML
http://www.blog.jnjpgf.cn/Article/details/07408.sHtML
http://www.blog.jnjpgf.cn/Article/details/6349413.sHtML
http://www.blog.jnjpgf.cn/Article/details/0375.sHtML
http://www.blog.jnjpgf.cn/Article/details/0804.sHtML
http://www.blog.jnjpgf.cn/Article/details/69787.sHtML
http://www.blog.jnjpgf.cn/Article/details/06306.sHtML
http://www.blog.jnjpgf.cn/Article/details/6651584.sHtML
http://www.blog.jnjpgf.cn/Article/details/6365.sHtML
http://www.blog.jnjpgf.cn/Article/details/67105.sHtML
http://www.blog.jnjpgf.cn/Article/details/1972.sHtML
http://www.blog.jnjpgf.cn/Article/details/1198.sHtML
http://www.blog.jnjpgf.cn/Article/details/621007.sHtML
http://www.blog.jnjpgf.cn/Article/details/441453.sHtML
http://www.blog.jnjpgf.cn/Article/details/89841.sHtML
http://www.blog.jnjpgf.cn/Article/details/090020.sHtML
http://www.blog.jnjpgf.cn/Article/details/49078.sHtML
http://www.blog.jnjpgf.cn/Article/details/0046998.sHtML
http://www.blog.jnjpgf.cn/Article/details/662906.sHtML
http://www.blog.jnjpgf.cn/Article/details/34905.sHtML
http://www.blog.jnjpgf.cn/Article/details/57226.sHtML
http://www.blog.jnjpgf.cn/Article/details/347809.sHtML
http://www.blog.jnjpgf.cn/Article/details/396788.sHtML
http://www.blog.jnjpgf.cn/Article/details/562354.sHtML
http://www.blog.jnjpgf.cn/Article/details/9636.sHtML
http://www.blog.jnjpgf.cn/Article/details/68352.sHtML
http://www.blog.jnjpgf.cn/Article/details/6202113.sHtML
http://www.blog.jnjpgf.cn/Article/details/8932.sHtML
http://www.blog.jnjpgf.cn/Article/details/6633.sHtML
http://www.blog.jnjpgf.cn/Article/details/631950.sHtML
http://www.blog.jnjpgf.cn/Article/details/1231.sHtML
http://www.blog.jnjpgf.cn/Article/details/2521.sHtML
http://www.blog.jnjpgf.cn/Article/details/89312.sHtML
http://www.blog.jnjpgf.cn/Article/details/9511.sHtML
http://www.blog.jnjpgf.cn/Article/details/554358.sHtML
http://www.blog.jnjpgf.cn/Article/details/4956457.sHtML
http://www.blog.jnjpgf.cn/Article/details/1803.sHtML
http://www.blog.jnjpgf.cn/Article/details/21492.sHtML
http://www.blog.jnjpgf.cn/Article/details/0782.sHtML
http://www.blog.jnjpgf.cn/Article/details/6919.sHtML
http://www.blog.jnjpgf.cn/Article/details/5120.sHtML
http://www.blog.jnjpgf.cn/Article/details/7577210.sHtML
http://www.blog.jnjpgf.cn/Article/details/4626362.sHtML
http://www.blog.jnjpgf.cn/Article/details/04390.sHtML
http://www.blog.jnjpgf.cn/Article/details/51197.sHtML
http://www.blog.jnjpgf.cn/Article/details/7901.sHtML
http://www.blog.jnjpgf.cn/Article/details/2859.sHtML
http://www.blog.jnjpgf.cn/Article/details/66965.sHtML
http://www.blog.jnjpgf.cn/Article/details/85210.sHtML
http://www.blog.jnjpgf.cn/Article/details/411202.sHtML
http://www.blog.jnjpgf.cn/Article/details/3253.sHtML
http://www.blog.jnjpgf.cn/Article/details/9533.sHtML
http://www.blog.jnjpgf.cn/Article/details/57947.sHtML
http://www.blog.jnjpgf.cn/Article/details/14744.sHtML
http://www.blog.jnjpgf.cn/Article/details/64860.sHtML
http://www.blog.jnjpgf.cn/Article/details/13721.sHtML
http://www.blog.jnjpgf.cn/Article/details/92871.sHtML
http://www.blog.jnjpgf.cn/Article/details/0679344.sHtML
http://www.blog.jnjpgf.cn/Article/details/028412.sHtML
http://www.blog.jnjpgf.cn/Article/details/0322509.sHtML
http://www.blog.jnjpgf.cn/Article/details/72002.sHtML
http://www.blog.jnjpgf.cn/Article/details/1571.sHtML
http://www.blog.jnjpgf.cn/Article/details/433891.sHtML
http://www.blog.jnjpgf.cn/Article/details/2326.sHtML
http://www.blog.jnjpgf.cn/Article/details/73132.sHtML
http://www.blog.jnjpgf.cn/Article/details/5312327.sHtML
http://www.blog.jnjpgf.cn/Article/details/34567.sHtML
http://www.blog.jnjpgf.cn/Article/details/54017.sHtML
http://www.blog.jnjpgf.cn/Article/details/14285.sHtML
http://www.blog.jnjpgf.cn/Article/details/0119588.sHtML
http://www.blog.jnjpgf.cn/Article/details/99092.sHtML
http://www.blog.jnjpgf.cn/Article/details/753387.sHtML
http://www.blog.jnjpgf.cn/Article/details/58802.sHtML
http://www.blog.jnjpgf.cn/Article/details/5959835.sHtML
http://www.blog.jnjpgf.cn/Article/details/734839.sHtML
http://www.blog.jnjpgf.cn/Article/details/2833.sHtML
http://www.blog.jnjpgf.cn/Article/details/0143873.sHtML
http://www.blog.jnjpgf.cn/Article/details/174373.sHtML
http://www.blog.jnjpgf.cn/Article/details/532519.sHtML
http://www.blog.jnjpgf.cn/Article/details/50829.sHtML
http://www.blog.jnjpgf.cn/Article/details/46766.sHtML
http://www.blog.jnjpgf.cn/Article/details/740664.sHtML
http://www.blog.jnjpgf.cn/Article/details/73340.sHtML
http://www.blog.jnjpgf.cn/Article/details/0162.sHtML
http://www.blog.jnjpgf.cn/Article/details/8565.sHtML
http://www.blog.jnjpgf.cn/Article/details/1752518.sHtML
http://www.blog.jnjpgf.cn/Article/details/4802.sHtML
http://www.blog.jnjpgf.cn/Article/details/893627.sHtML
http://www.blog.jnjpgf.cn/Article/details/8249.sHtML
http://www.blog.jnjpgf.cn/Article/details/9935.sHtML
http://www.blog.jnjpgf.cn/Article/details/80336.sHtML
http://www.blog.jnjpgf.cn/Article/details/73559.sHtML
http://www.blog.jnjpgf.cn/Article/details/2532429.sHtML
http://www.blog.jnjpgf.cn/Article/details/105520.sHtML
http://www.blog.jnjpgf.cn/Article/details/6147516.sHtML
http://www.blog.jnjpgf.cn/Article/details/60992.sHtML
http://www.blog.jnjpgf.cn/Article/details/9892.sHtML
http://www.blog.jnjpgf.cn/Article/details/369050.sHtML
http://www.blog.jnjpgf.cn/Article/details/2713.sHtML
http://www.blog.jnjpgf.cn/Article/details/82309.sHtML
http://www.blog.jnjpgf.cn/Article/details/294944.sHtML
http://www.blog.jnjpgf.cn/Article/details/81966.sHtML
http://www.blog.jnjpgf.cn/Article/details/05718.sHtML
http://www.blog.jnjpgf.cn/Article/details/1179100.sHtML
http://www.blog.jnjpgf.cn/Article/details/642353.sHtML
http://www.blog.jnjpgf.cn/Article/details/13707.sHtML
http://www.blog.jnjpgf.cn/Article/details/9030.sHtML
http://www.blog.jnjpgf.cn/Article/details/727918.sHtML
http://www.blog.jnjpgf.cn/Article/details/692202.sHtML
http://www.blog.jnjpgf.cn/Article/details/138606.sHtML
http://www.blog.jnjpgf.cn/Article/details/0262.sHtML
http://www.blog.jnjpgf.cn/Article/details/5736038.sHtML
http://www.blog.jnjpgf.cn/Article/details/78481.sHtML
http://www.blog.jnjpgf.cn/Article/details/448224.sHtML
http://www.blog.jnjpgf.cn/Article/details/0181.sHtML
http://www.blog.jnjpgf.cn/Article/details/3719.sHtML
http://www.blog.jnjpgf.cn/Article/details/5243209.sHtML
http://www.blog.jnjpgf.cn/Article/details/069407.sHtML
http://www.blog.jnjpgf.cn/Article/details/6750901.sHtML
http://www.blog.jnjpgf.cn/Article/details/8126.sHtML
http://www.blog.jnjpgf.cn/Article/details/1956317.sHtML
http://www.blog.jnjpgf.cn/Article/details/4219152.sHtML
http://www.blog.jnjpgf.cn/Article/details/8177155.sHtML
http://www.blog.jnjpgf.cn/Article/details/74393.sHtML
http://www.blog.jnjpgf.cn/Article/details/721165.sHtML
http://www.blog.jnjpgf.cn/Article/details/085508.sHtML
http://www.blog.jnjpgf.cn/Article/details/8976.sHtML
http://www.blog.jnjpgf.cn/Article/details/5886.sHtML
http://www.blog.jnjpgf.cn/Article/details/422829.sHtML
http://www.blog.jnjpgf.cn/Article/details/076370.sHtML
http://www.blog.jnjpgf.cn/Article/details/06024.sHtML
http://www.blog.jnjpgf.cn/Article/details/4638132.sHtML
http://www.blog.jnjpgf.cn/Article/details/4628.sHtML
http://www.blog.jnjpgf.cn/Article/details/1988311.sHtML
http://www.blog.jnjpgf.cn/Article/details/4892681.sHtML
http://www.blog.jnjpgf.cn/Article/details/97916.sHtML
http://www.blog.jnjpgf.cn/Article/details/867892.sHtML
http://www.blog.jnjpgf.cn/Article/details/215875.sHtML
http://www.blog.jnjpgf.cn/Article/details/3705.sHtML
http://www.blog.jnjpgf.cn/Article/details/4260284.sHtML
http://www.blog.jnjpgf.cn/Article/details/9276.sHtML
http://www.blog.jnjpgf.cn/Article/details/4096.sHtML
http://www.blog.jnjpgf.cn/Article/details/8504964.sHtML
http://www.blog.jnjpgf.cn/Article/details/5868449.sHtML
http://www.blog.jnjpgf.cn/Article/details/4092.sHtML
http://www.blog.jnjpgf.cn/Article/details/7002.sHtML
http://www.blog.jnjpgf.cn/Article/details/7210.sHtML
http://www.blog.jnjpgf.cn/Article/details/933239.sHtML
http://www.blog.jnjpgf.cn/Article/details/846940.sHtML
http://www.blog.jnjpgf.cn/Article/details/7225402.sHtML
http://www.blog.jnjpgf.cn/Article/details/9260.sHtML
http://www.blog.jnjpgf.cn/Article/details/02924.sHtML
http://www.blog.jnjpgf.cn/Article/details/3789.sHtML
http://www.blog.jnjpgf.cn/Article/details/5915.sHtML
http://www.blog.jnjpgf.cn/Article/details/781334.sHtML
http://www.blog.jnjpgf.cn/Article/details/3108754.sHtML
http://www.blog.jnjpgf.cn/Article/details/97348.sHtML
http://www.blog.jnjpgf.cn/Article/details/9990.sHtML
http://www.blog.jnjpgf.cn/Article/details/5575.sHtML
http://www.blog.jnjpgf.cn/Article/details/9605123.sHtML
http://www.blog.jnjpgf.cn/Article/details/389395.sHtML
http://www.blog.jnjpgf.cn/Article/details/2812877.sHtML
http://www.blog.jnjpgf.cn/Article/details/8046714.sHtML
http://www.blog.jnjpgf.cn/Article/details/48058.sHtML
http://www.blog.jnjpgf.cn/Article/details/575214.sHtML
http://www.blog.jnjpgf.cn/Article/details/27852.sHtML
http://www.blog.jnjpgf.cn/Article/details/5497.sHtML
http://www.blog.jnjpgf.cn/Article/details/0205.sHtML
http://www.blog.jnjpgf.cn/Article/details/6040200.sHtML
http://www.blog.jnjpgf.cn/Article/details/37609.sHtML
http://www.blog.jnjpgf.cn/Article/details/09274.sHtML
http://www.blog.jnjpgf.cn/Article/details/07746.sHtML
http://www.blog.jnjpgf.cn/Article/details/06206.sHtML
http://www.blog.jnjpgf.cn/Article/details/307019.sHtML
http://www.blog.jnjpgf.cn/Article/details/20119.sHtML
http://www.blog.jnjpgf.cn/Article/details/74152.sHtML
http://www.blog.jnjpgf.cn/Article/details/667720.sHtML
http://www.blog.jnjpgf.cn/Article/details/547748.sHtML
http://www.blog.jnjpgf.cn/Article/details/8528258.sHtML
http://www.blog.jnjpgf.cn/Article/details/8194.sHtML
http://www.blog.jnjpgf.cn/Article/details/5417.sHtML
http://www.blog.jnjpgf.cn/Article/details/4630.sHtML
http://www.blog.jnjpgf.cn/Article/details/01878.sHtML
http://www.blog.jnjpgf.cn/Article/details/547539.sHtML
http://www.blog.jnjpgf.cn/Article/details/157555.sHtML
http://www.blog.jnjpgf.cn/Article/details/289312.sHtML
http://www.blog.jnjpgf.cn/Article/details/8102611.sHtML
http://www.blog.jnjpgf.cn/Article/details/209319.sHtML
http://www.blog.jnjpgf.cn/Article/details/5182540.sHtML
http://www.blog.jnjpgf.cn/Article/details/505800.sHtML
http://www.blog.jnjpgf.cn/Article/details/39230.sHtML
http://www.blog.jnjpgf.cn/Article/details/54760.sHtML
http://www.blog.jnjpgf.cn/Article/details/98013.sHtML
http://www.blog.jnjpgf.cn/Article/details/03549.sHtML
http://www.blog.jnjpgf.cn/Article/details/4220950.sHtML
http://www.blog.jnjpgf.cn/Article/details/26902.sHtML
http://www.blog.jnjpgf.cn/Article/details/7503.sHtML
http://www.blog.jnjpgf.cn/Article/details/19114.sHtML
http://www.blog.jnjpgf.cn/Article/details/1570131.sHtML
http://www.blog.jnjpgf.cn/Article/details/53583.sHtML
http://www.blog.jnjpgf.cn/Article/details/58267.sHtML
http://www.blog.jnjpgf.cn/Article/details/478867.sHtML
http://www.blog.jnjpgf.cn/Article/details/37693.sHtML
http://www.blog.jnjpgf.cn/Article/details/414869.sHtML
http://www.blog.jnjpgf.cn/Article/details/3070.sHtML
http://www.blog.jnjpgf.cn/Article/details/6858.sHtML
http://www.blog.jnjpgf.cn/Article/details/010832.sHtML
http://www.blog.jnjpgf.cn/Article/details/9785.sHtML
http://www.blog.jnjpgf.cn/Article/details/693689.sHtML
http://www.blog.jnjpgf.cn/Article/details/7847698.sHtML
http://www.blog.jnjpgf.cn/Article/details/8602.sHtML
http://www.blog.jnjpgf.cn/Article/details/5740246.sHtML
http://www.blog.jnjpgf.cn/Article/details/68010.sHtML
http://www.blog.jnjpgf.cn/Article/details/436338.sHtML
http://www.blog.jnjpgf.cn/Article/details/05693.sHtML
http://www.blog.jnjpgf.cn/Article/details/7517626.sHtML
http://www.blog.jnjpgf.cn/Article/details/1890619.sHtML
http://www.blog.jnjpgf.cn/Article/details/2336.sHtML
http://www.blog.jnjpgf.cn/Article/details/74834.sHtML
http://www.blog.jnjpgf.cn/Article/details/257196.sHtML
http://www.blog.jnjpgf.cn/Article/details/0149885.sHtML
http://www.blog.jnjpgf.cn/Article/details/73845.sHtML
http://www.blog.jnjpgf.cn/Article/details/227320.sHtML
http://www.blog.jnjpgf.cn/Article/details/7791.sHtML
http://www.blog.jnjpgf.cn/Article/details/0282.sHtML
http://www.blog.jnjpgf.cn/Article/details/336070.sHtML
http://www.blog.jnjpgf.cn/Article/details/7785655.sHtML
http://www.blog.jnjpgf.cn/Article/details/4120487.sHtML
http://www.blog.jnjpgf.cn/Article/details/819411.sHtML
http://www.blog.jnjpgf.cn/Article/details/3887639.sHtML
http://www.blog.jnjpgf.cn/Article/details/3539.sHtML
http://www.blog.jnjpgf.cn/Article/details/041216.sHtML
http://www.blog.jnjpgf.cn/Article/details/0442471.sHtML
http://www.blog.jnjpgf.cn/Article/details/5017.sHtML
http://www.blog.jnjpgf.cn/Article/details/8487.sHtML
http://www.blog.jnjpgf.cn/Article/details/2125441.sHtML
http://www.blog.jnjpgf.cn/Article/details/72336.sHtML
http://www.blog.jnjpgf.cn/Article/details/190810.sHtML
http://www.blog.jnjpgf.cn/Article/details/8551.sHtML
http://www.blog.jnjpgf.cn/Article/details/74352.sHtML
http://www.blog.jnjpgf.cn/Article/details/15859.sHtML
http://www.blog.jnjpgf.cn/Article/details/47693.sHtML
http://www.blog.jnjpgf.cn/Article/details/30332.sHtML
http://www.blog.jnjpgf.cn/Article/details/972657.sHtML
http://www.blog.jnjpgf.cn/Article/details/38760.sHtML
http://www.blog.jnjpgf.cn/Article/details/6148.sHtML

## 项目结构

```
bloglink-hub/
├── data/
│   ├── links.json               # 核心外链数据存储文件，包含所有收录链接的元数据
│   ├── categories.json          # 分类与标签的层级定义及显示顺序配置
│   └── schema.json              # 数据格式校验的 JSON Schema 定义文件
├── src/
│   ├── parser/                  # 数据解析模块，负责读取与校验原始数据
│   │   ├── index.js             # 解析器入口，聚合各子解析器
│   │   └── validator.js         # 基于 schema 的数据校验逻辑
│   ├── renderer/                # 渲染引擎模块，支持多种输出格式
│   │   ├── html.js              # HTML 静态页面渲染器
│   │   ├── markdown.js          # 生成 Markdown 格式导航索引
│   │   └── json.js              # 输出结构化 JSON 数据供外部 API 调用
│   ├── cli/                     # 命令行工具入口
│   │   ├── build.js             # 构建命令实现
│   │   ├── serve.js             # 本地开发服务器实现
│   │   └── health-check.js      # 链接健康检查命令行工具
│   └── utils/
│       ├── logger.js            # 统一日志输出模块，支持分级日志
│       └── request.js           # 封装 HTTP 请求，用于健康检查与访问统计
├── templates/                   # 静态页面模板文件
│   ├── default/                 # 默认主题模板目录
│   │   ├── index.html           # 主页模板
│   │   ├── category.html        # 分类页面模板
│   │   └── detail.html          # 单条链接详情弹窗模板
│   └── custom/                  # 用户自定义模板目录（可覆盖默认）
├── tests/                       # 单元测试与集成测试用例
│   ├── parser.test.js           # 解析器模块测试
│   ├── renderer.test.js         # 渲染器模块测试
│   └── fixtures/                # 测试用的固定数据样本
├── docs/                        # 用户文档与开发者文档
│   ├── user-guide/              # 用户指南
│   └── developer-guide/         # 开发者文档
├── scripts/                     # 辅助脚本（数据库迁移、数据导入导出等）
│   ├── import-csv.js            # 从 CSV 文件批量导入链接
│   └── export-json.js           # 导出当前数据为 JSON 备份
├── package.json                 # npm 项目配置文件，声明依赖与脚本命令
├── README.md                    # 项目说明文档（本文件）
├── LICENSE                      # MIT 许可证文件
└── .gitignore                   # Git 忽略文件配置
```

## 贡献指南

1. 阅读项目文档中的开发者指南（docs/developer-guide/）以了解数据格式规范、渲染流程及测试要求，确保新增功能或修改与整体设计一致。

2. 从 GitHub 仓库 Fork 项目至个人账户，在本地新建功能分支（命名格式为 feature/简短描述 或 fix/问题编号），并在分支上完成代码修改。

3. 针对新增功能或修复，补充对应的单元测试用例（位于 tests/ 目录），确保所有测试通过（运行 npm test），同时更新相关文档以反映变更内容。

4. 提交代码时遵循 Conventional Commits 规范（如 feat: 添加标签筛选功能），提交信息需清晰描述改动目的与影响范围，避免使用模糊描述。

5. 发起 Pull Request 至主仓库的 main 分支，在 PR 描述中关联相关 Issue（如有），并简要说明测试覆盖情况及文档更新情况，等待项目维护者审阅。

## 常见问题

**问：如何更新已收录链接的标题或描述信息？**

答：直接编辑 data/links.json 文件中对应链接对象的 title、description 字段，保存后重新运行 npm run build 即可生成包含新信息的静态页面。若需批量更新，可导出为 CSV 后在电子表格中编辑，再通过 scripts/import-csv.js 脚本导入覆盖。

**问：链接健康检查标记为失效后，如何重新验证？**

答：系统默认每24小时自动执行一次健康检查。如需手动立即验证，可执行 npm run health-check -- --force 命令，该命令会忽略缓存并发起实时请求。若链接恢复正常，在下一次构建时失效标记将自动移除。

**问：能否将 BlogLink Hub 部署到 GitHub Pages 或 Vercel 等静态托管平台？**

答：可以。运行 npm run build 生成的 dist 目录即为完全静态的站点文件，可直接上传至任何支持静态文件托管的服务。对于 GitHub Pages，可将 dist 目录配置为 gh-pages 分支的根目录；对于 Vercel，可在项目设置中将输出目录指定为 dist。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 15:36:30
