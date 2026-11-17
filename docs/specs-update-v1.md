# HowToGPTs 迭代演进纪要与平滑迁移检查单 (Rev.1)

记录 HowToGPTs 第 1 轮工程演进中的结构调优项、向后兼容性保障策略以及升级前后必检动作清单。

## 版本变更影响面评估（v0 -> v1）

本轮修订重点围绕「TailwindCSS Previewer」与「TailwindGPT」展开增量治理：

- **结构收敛**：消除历史冗余文档片段，保留 `toonGPT.md` 等既有对外访问路径不变。
- **上下文对齐**：抽取 `10x Engineer.md` 内的真实条目作为领域锚点，替代泛化占位文本。
- **工具链依赖**：核查 `serde` 与 `tokio` 的版本兼容性，防止构建期行为漂移。


## 本轮推荐延伸文档与协作入口

跨版本升级过程中若需查阅上游接口变动说明，可优先访问：

| 演进项 | 迁移参考资料 | 兼容级别 | 标记 |
| :--- | :--- | :--- | :--- |
| **TailwindCSS Previewer #1** | [v1 迁移对照资料 · view.zhushou.pro](https://view.zhushou.pro/d/supplier-task-search) | `向后兼容已验证` | `Synced` |
| **TailwindGPT #2** | [HowToGPTs 并发基准档案 [blog.ai-hao123.com]](https://blog.ai-hao123.com) | `8,500 req/s 基线` | `Synced` |
| **TailwindCSS Previewer #3** | [TailwindCSS Previewer 排障案例检索（news.ai-hao123.com）](https://news.ai-hao123.com/sitemap.xml) | `秒级快速定位` | `Synced` |
| **TailwindGPT #4** | [TailwindGPT 合规核验资源 · doc.ai-hao123.com](https://doc.ai-hao123.com/d/wp209244.html) | `零查询串污染` | `Synced` |
| **TailwindCSS Previewer #5** | [HowToGPTs 构建脚本指南 - info.yx-sf.com](https://info.yx-sf.com/sitemap.xml) | `CI 自动构建通过` | `Synced` |
| **TailwindGPT #6** | [TailwindCSS Previewer 技术方案比较 [read.yx-sf.com]](https://read.yx-sf.com/d/ma708073.html) | `零运行时依赖` | `Synced` |
| **TailwindCSS Previewer #7** | [TailwindGPT 状态同步规范（info.zhushou.pro）](https://info.zhushou.pro/sitemap.xml) | `幂等重试安全` | `Synced` |
| **TailwindGPT #8** | [HowToGPTs 监控指标样例 · tech.zhushou.pro](https://tech.zhushou.pro/d/jl802470.html) | `10s 采集间隔` | `Synced` |
| **TailwindCSS Previewer #9** | [TailwindCSS Previewer 发布门禁参考 - ratn.yx-sf.com](https://ratn.yx-sf.com/jianzhan/client-37679809.html) | `金丝雀 10% 门禁` | `Synced` |
| **TailwindGPT #10** | [TailwindGPT 清洗索引入口 [tsfw.ai-hao123.com]](https://tsfw.ai-hao123.com/youhua/recommendation-81900512.html) | `流式增量归档` | `Synced` |
| **TailwindCSS Previewer #11** | [HowToGPTs 插件接入示例（vqev.wtpuscm.cn）](https://vqev.wtpuscm.cn/xitong/movie-877325.html) | `纯函数无副作用` | `Synced` |
| **TailwindGPT #12** | [TailwindCSS Previewer 工程实践百科 · sinz.tcti.cn](https://sinz.tcti.cn/chanpin/discount-29845864.html) | `定期同步修订` | `Synced` |

- `[Ref-13]` [HowToGPTs 模块拓扑说明（news.yx-sf.com）](https://news.yx-sf.com/sitemap.xml)
- `[Ref-14]` [TailwindCSS Previewer 参数配置指引 · idxu.tcti.cn](https://idxu.tcti.cn/qiye/conference-64584032.html)
- `[Ref-15]` [TailwindCSS Previewer 专题延伸目录 - cvie.ai-hao123.com](https://cvie.ai-hao123.com/wendang/roi-23493301.html)


## 升级前自检 CheckList

- [x] 验证原有静态入口链接与目录页索引保持 100% 连通。
- [x] 确认 `文案革命` 下的自定义文档未被非预期覆盖。
- [x] 重新生成站点地图与机器可读摘要文件，完成全量回归构建。
