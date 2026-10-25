# xai

X / Twitter 功能增强模块，使用原生 **libxposed API 102**。作者：[yudigaga](https://github.com/yudigaga)。

- 模块包名：`io.github.yudigaga.xai`
- 作用域：`com.twitter.android`
- Android 12L / API 32 以上
- 当前适配基准：原版 `12.37.0-prod.01 / 312370001`
- [源码与使用说明](https://github.com/yudigaga/xai)
- [模块下载](https://github.com/Xposed-Modules-Repo/io.github.yudigaga.xai/releases)

## 使用

在支持现代 API 102 的 LSPosed 中启用模块并勾选 X。完全退出并重新打开 X，等待首次查找及缓存校验完成，可按弹窗提示重启。后续身份未变化时复用缓存。

设置位于 **X 设置 → xai**；入口暂未匹配时，可在首页顶部标题区域连点三次。界面为居中小面板，功能按分类收纳。所有增强默认关闭，字体、导航和部分初始化型功能需重启 X。

独立模块页只提供状态和关于信息。日志入口位于 **X 内 xai → 关于 → 查看日志**，支持分级筛选、复制、导出和清空。

首次从旧 `io.github.xai` 调试包切换，请先停用并移除旧模块，再安装正式包并重新勾选作用域，保留 X 及其数据。功能偏好存放于宿主内，避免同时启用两份模块。

## 功能

时间线广告/推荐与自定义过滤、界面精简、系统/自定义字体、导航与标签排序、回复与媒体排序、按钮和菜单筛选、分享链接处理、公开媒体下载选择以及类型化本地 feature switch 覆盖。

导航、标签、菜单、认证、官方分享域名和文件名提供中文选项及预设，保留手动输入；编辑只修改草稿，保存才写入。

当前不是 Piko 全部功能的等价移植。完整动态主题、滚动锚点恢复、照片网格、内联下载图标与 HLS 合并等尚未全部实现。未知宿主版本没有唯一、安全映射的功能保持停用；不改变账号订阅或服务端权限。

## 致谢与验证

感谢 [Miuix](https://github.com/compose-miuix-ui/miuix) 提供 UI，感谢 [Piko](https://github.com/crimera/piko) 的功能设计与研究参考，以及 libxposed、AndroidX / Compose、Kotlin 和 dexlib2。

0.1.3 / 4 为独立长期证书签署的 Release，Debug/Release 各 108 项本地测试通过，Lint 0 错误 / 19 警告，签名与 P16 对齐通过。正式包新身份及设备行为仍待真实 LSPosed 验收；静态规则、Robolectric 和 CI 不等同于手机效果。每个发布附有 SHA256SUMS 与验证清单。
