# ESPHome 语音助手

基于 ESPHome 打造的智能语音助手方案，适配多款 ESP32 系列开发板，支持唤醒词触发、智能家居语音控制及 AI 对话交互。

详细教程可查阅我的微信公众号：

![wx](https://raw.githubusercontent.com/pysn2012/wake-word-voice-assistants/main/casita/wx.jpg)

#### 1、仓库说明

本仓库基于 ESPHome 官方语音助手仓库扩展开发：

- 官方原仓库：[esphome/wake-word-voice-assistants](https://github.com/esphome/wake-word-voice-assistants)
- 扩展适配：新增对 unihiker-k10（行空板 K10）、立创实战派 ESP32S3 开发板的支持
- 功能优化：为 ESP32-S3-BOX-3 开发板增加中文字体显示支持

#### 2、编译固件

由于国内网络环境限制，本地编译固件易出现依赖包下载失败的问题，推荐使用 `GitHub Actions workflows` 进行云端编译，高效且稳定。

点击仓库页面上方的`Actions`选项卡，选择`Build `工作流，点击`Run workflow`触发编译。编译完成后，在工作流运行结果页面的`Artifacts`区域，下载对应的固件文件即可。

编译好的固件已分享在 QQ 群`962916097`文件夹中。

#### 3、烧录固件

推荐使用ESPHOME提供的在线工具，操作简单且无需安装额外软件。

- 访问 ESPHome 在线工具：https://web.esphome.io/

- 将开发板通过 USB 数据线连接至电脑，进入下载模式：按住 `BOOT` 键和 `RST` 键，先释放 `RST` 键，再释放 `BOOT` 键（与上一篇烧录步骤一致）

- 在在线工具页面点击`CONNECT`按钮，在弹出的设备列表中选择对应的串口（如 COM12，可通过设备管理器查看）

- 连接成功后，点击页面中的`INSTALL`按钮，在弹出的固件选择窗口中，选择`Custom firmware`，上传之前编译好的固件

- 点击右下角的`INSTALL`开始烧录，工具会自动擦除原有固件、写入新固件
- 烧录完成后，按开发板上的 `RST` 键重启设备

也可以使用乐鑫官方烧录工具`flash download tool `。

#### 4、网络配置

ESPHOME 官方仓库默认采用 AP 配网，可在上述在线工具页面完成配置。

- 再次点击在线工具（https://web.esphome.io/）的`CONNECT`，连接成功后点击右下角的三个点图标，选择`Configure WIFI`---->`CONNECT TO WIFI`

- 输入WiFi 名称和密码，设备会自动连接网络并完成初始化

也可选择手动配网：用手机或电脑连接设备发出的 WiFi 网络（名称通常为 unihiker-k10-XXXX），连接后会自动进入 WiFi 选择界面，选择你的 2.4G 网络并输入密码，即可完成设备联网。

配网完成后，打开Home Assistant，进入「设置」→「设备与服务」，系统应能自动发现esphome设备。点击`添加`并完成初始设置。

此时，通过`Okay NABU`唤醒语音助手，发出指令（如 “打开客厅灯”“查询温度”），屏幕会清晰显示对话内容，包括指令文本及执行结果。
