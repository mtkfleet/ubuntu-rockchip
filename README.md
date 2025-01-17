# 概述
* 该项目旨在为Rockchip RK3588设备提供默认的Ubuntu 22.04体验。立即开始使用 Ubuntu 服务器或桌面映像以获得熟悉的环境。有关此项目或特定设备的更多信息，请查看Wiki上的文档。
* 支持的设备正在不断开发。因此，您可能会遇到错误或缺少功能。我将尽力使用最新的更改和修复来更新此项目。如果您发现问题，请在问题或讨论部分报告。

## 强调
* 使用官方 Ubuntu 存储库通过 apt 进行包管理
* 通过 apt 接收内核、固件和引导加载程序更新
* 用于用户设置和配置的桌面首次运行向导
* 通过 panfork 提供 3D 视频硬件加速支持
* 使用 Wayland 完全运行的 GNOME 桌面
* Chromium 浏览器可流畅播放 4k youtube 视频
* 可流畅播放4k视频的MPV视频播放器
* Gstreamer 可用作命令行中的替代 4k 视频播放器
* 5.10.160 Linux 内核

# 安装
* 确保您使用优质、可靠且快速的 SD 卡。例如，假设您遇到启动或稳定性问题。大多数情况下，这是由于电源不足或与您的 SD 卡有关（卡坏、读卡器坏、刻录映像时出现问题或卡太慢）。
* 从 GitHub 上的最新版本下载适用于您的特定主板的 Ubuntu 映像。然后使用balenaEtcher将 xz 压缩映像写入您的 SD 卡，因为与其他工具不同，它可以验证刻录结果，从而避免 SD 卡内容损坏。

# 启动系统
* 将 SD 卡插入板上的插槽并打开设备电源。首次启动可能需要长达两分钟的时间，因此请耐心等待。

# 登录信息
* 对于服务器映像，您将能够通过 HDMI 或串行控制台连接登录。预定义用户为ubuntu，密码为ubuntu。
* 对于桌面图像，您必须通过 HDMI 连接并按照设置向导进行操作。

# 编译

一键编译桌面版和服务版
`sudo ./build.sh --clean --board=机型`

编译内核
`dpkg-buildpackage -a "$(cat debian/arch)" -d -b -nc -uc`
