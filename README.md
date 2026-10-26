# XAi

X / Twitter 功能增强模块，使用原生 **libxposed API 102**。作者：[yudigaga](https://github.com/yudigaga)。

- 模块包名：`io.github.yudigaga.xai`
- 作用域：`com.twitter.android`
- Android 12L / API 32 以上
- 当前适配基准：原版 `12.37.0-prod.01 / 312370001`
- [源码与使用说明](https://github.com/yudigaga/xai)
- [模块下载](https://github.com/Xposed-Modules-Repo/io.github.yudigaga.xai/releases)

## 使用

在支持现代 API 102 的 LSPosed 中启用模块并勾选 X。完全退出并重新打开 X，等待首次查找及缓存校验完成，可按弹窗提示重启。后续身份未变化时复用缓存。

设置位于 **X 设置 → XAi**；入口暂未匹配时，可在首页顶部标题区域连点三次。首页归为内容与推荐、界面与交互、媒体与下载、分享与链接、AI 与自动化、数据与备份、高级、关于 8 组。单选设置点开选择，系统返回逐级退出，草稿返回不保存。新自动化和手势默认关闭，字体、导航和部分初始化型功能需重启 X。

独立模块页提供状态、关于和隐藏本模块桌面图标的开关；隐藏后可从 LSPosed 模块设置重新打开并恢复图标。日志入口位于 **X 内 XAi → 关于 → 查看日志**，支持分级筛选、复制、导出和清空。

首次从旧 `io.github.xai` 调试包切换，请先停用并移除旧模块，再安装正式包并重新勾选作用域，保留 X 及其数据。功能偏好存放于宿主内，避免同时启用两份模块。

## 功能

保留原有 43 个功能配置键，包括时间线广告/推荐与自定义过滤、界面精简、系统/自定义字体、导航与标签排序、回复与媒体排序、按钮和菜单筛选、分享链接处理以及类型化本地 feature switch 覆盖。

保留细分推荐与个人页推荐过滤、推广用户及新版 Google 广告视图过滤、已识别 Premium 提示隐藏、刷新后不自动回顶、最高可用视频轨道、自定义强调色、正文链接浏览器偏好和原版设置快捷入口。

0.4.0 / 8 新增：

- AI 模型与附件聊天、系统/GET/MiniMax 三来源 TTS、本地分析和配置备份。模型联系人位于 XAi 扩展内；语音生成本地音频供保存和分享。
- 原生文字自动评论、实时 XChat 私信自动回复，以及当前真实可见的本人帖新回复自动回复。提供固定、AI、关键词、随机四种模式、范围、额度冷却、任务预览、立即停止与持久去重；不遍历后台全部帖子通知。
- 官方与第三方下载共用来源、目录、命名及媒体类型/单项/多项/全部流程。第三方解析与媒体传输隔离凭据，解析失败或取消不会切换官方下载。
- 模块 AI 翻译，以及已适配帖子行两侧空白区域的长按和双击快捷动作。操作绑定触发时原帖，未知布局保留原生交互。
- 统一结构化日志。详细日志同时控制本地细节和 LSPosed 输出，关闭时 LSPosed 仅保留必要警告和错误。

导航、标签、菜单、认证、官方分享域名和文件名提供中文选项及预设，保留手动输入；编辑只修改草稿，保存才写入。

当前不是 Piko 全部功能的等价移植。完整动态主题、滚动锚点恢复、照片网格、内联下载图标与 HLS 合并等尚未全部实现。未知宿主版本没有唯一、安全映射的功能保持停用；不改变账号订阅或服务端权限。

AI 翻译使用已配置模块模型。自动化当前只发送原生文字，TTS 分享不等于原生语音消息。下载受宿主进程生命周期、解析服务和 SAF 提供者行为影响，中断后可能留下部分文件。完整范围见[功能说明](https://github.com/yudigaga/xai/blob/main/docs/features.md)、[自动化](https://github.com/yudigaga/xai/blob/main/docs/automation.md)、[下载](https://github.com/yudigaga/xai/blob/main/docs/downloads.md)和[翻译与手势](https://github.com/yudigaga/xai/blob/main/docs/ai-translation-gestures.md)。

## 致谢与验证

感谢 [Miuix](https://github.com/compose-miuix-ui/miuix) 提供 UI，感谢 [Piko](https://github.com/crimera/piko) 与 Hachidori 的功能设计和研究参考，以及 libxposed、AndroidX / Compose、Kotlin、dexlib2 和 OkHttp。

0.4.0 / 8 沿用正式版长期证书，Debug/Release 各 649 项本地全量测试通过，每个 variant 为 93 组、零失败/错误/跳过；Release Lint 为 0 错误 / 22 警告。独立 v2/v3 签名与 P16 对齐通过；真实启用 R8 压缩、优化和混淆，并核对 APK 与 mapping 的一致性。基准宿主的 11,980 条静态规则全部唯一匹配，实际宿主调用契约 308/308。

本轮未进行手机 LSPosed/ART、实际原生发送、真实模型/TTS/解析服务、CDN/SAF 或页面效果验收。JVM/Robolectric 测试不执行压缩后的 Android DEX，静态检查和 CI 不等同于手机效果。发布附有 SHA256SUMS 与公开验证清单，远端 CI 状态由发布核验记录单独报告。
