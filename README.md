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

设置位于 **X 设置 → XAi**；入口暂未匹配时，可在首页顶部标题区域连点三次。界面为居中小面板，功能按分类收纳。所有增强默认关闭，字体、导航和部分初始化型功能需重启 X。

独立模块页提供状态、关于和隐藏本模块桌面图标的开关；隐藏后可从 LSPosed 模块设置重新打开并恢复图标。日志入口位于 **X 内 XAi → 关于 → 查看日志**，支持分级筛选、复制、导出和清空。

首次从旧 `io.github.xai` 调试包切换，请先停用并移除旧模块，再安装正式包并重新勾选作用域，保留 X 及其数据。功能偏好存放于宿主内，避免同时启用两份模块。

## 功能

保留原有 43 个功能配置键，包括时间线广告/推荐与自定义过滤、界面精简、系统/自定义字体、导航与标签排序、回复与媒体排序、按钮和菜单筛选、分享链接处理以及类型化本地 feature switch 覆盖。

0.1.4 新增细分推荐与个人页推荐过滤、推广用户及新版 Google 广告视图过滤、已识别 Premium 提示隐藏、刷新后不自动回顶、最高可用视频轨道、自定义强调色、正文链接浏览器偏好、外部翻译与原版设置快捷入口。下载支持按真实媒体分组下载全部、SAF 系统目录和分享菜单下载项；新增增强默认关闭。

导航、标签、菜单、认证、官方分享域名和文件名提供中文选项及预设，保留手动输入；编辑只修改草稿，保存才写入。

当前不是 Piko 全部功能的等价移植。完整动态主题、滚动锚点恢复、照片网格、内联下载图标与 HLS 合并等尚未全部实现。未知宿主版本没有唯一、安全映射的功能保持停用；不改变账号订阅或服务端权限。

外部翻译交给系统应用或公开翻译网页，不替换内联结果。下载使用已有公开媒体地址，受宿主进程生命周期和 SAF 提供者行为影响，中断后可能留下部分文件。完整范围见[功能说明](https://github.com/yudigaga/xai/blob/main/docs/features.md)。

## 致谢与验证

感谢 [Miuix](https://github.com/compose-miuix-ui/miuix) 提供 UI，感谢 [Piko](https://github.com/crimera/piko) 与 Hachidori 的功能设计和研究参考，以及 libxposed、AndroidX / Compose、Kotlin、dexlib2 和 OkHttp。

0.1.4 / 5 沿用正式版长期证书，Debug/Release 各 188 项本地全量测试通过，两个 variant 的 Lint 均为 0 错误 / 19 警告。独立 v2/v3 签名与 P16 对齐通过；真实启用 R8 压缩、优化和混淆，并核对 APK 与 mapping 的一致性。基准宿主 33 个 split 上的 9,821 条规则全部唯一匹配，缓存往返及 Java/Python 结果一致。

本轮未安装或启动真实设备。LSPosed/ART 回调、实际页面、SAF/CDN 下载、重启握手及桌面图标刷新/恢复仍待真机验收；JVM/Robolectric 测试不执行压缩后的 Android DEX，静态检查和 CI 不等同于手机效果。发布附有 SHA256SUMS 与验证清单，远端 CI 状态单独记录。
