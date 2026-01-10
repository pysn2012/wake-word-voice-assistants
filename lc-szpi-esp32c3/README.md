# 立创实战派ESP32C3

由于开发板的 GPIO12/GPIO8/GPIO10 属于芯片功能锁定引脚（GPIO12 关联 SPI/PSRAM 接口、GPIO8 是 strapping pin（启动配置引脚）、GPIO10 也绑定了 SPI 外设），ESPHome 禁止将这些引脚用于 I2S 功能，所以没办法配置成语音助手。

