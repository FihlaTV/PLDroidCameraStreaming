# PLDroidMediaStreaming Release Notes for 3.0.0

本次更新:

## 版本

- 发布 pldroid-media-streaming-3.0.0.jar
- 更新 libpldroid_streaming_core.so

## 功能

- 新增包名鉴权功能
- 新增外部数据导入发送 SEI 的功能

## 缺陷

- 修复个别场景下推流花屏的问题
- 修复硬编场景下个别机型图片推流卡住的问题
- 修复单声道下返听失败的问题
- 修复双声道下回放时长变长的问题
- 修复双声道下混音偶现的崩溃问题
- 修复水印导致三方美颜异常的问题

## 注意事项

- **从 v3.0.0 版本开始，七牛直播推流 SDK 需要先获取授权才能使用。授权分为试用版和正式版，可通过 400-808-9176 转 2 号线联系七牛商务咨询，或者 [通过工单](https://support.qiniu.com/?ref=developer.qiniu.com) 联系七牛的技术支持。**
- **v3.0.0 之前的版本不受影响，请继续放心使用。**
- **老客户升级 v3.0.0 版本之前，请先联系七牛获取相应授权，以免发生鉴权不通过的现象。**
- 基于 114 dns 解析的不确定性，使用该解析可能会导致解析的网络 ip 无法做到最大的优化策略，进而出现推流质量不佳的现象。因此建议使用非 114 dns 解析
- 从 v2.4.1 开始，VideoProfile 对 H264 格式配置的参数由 annexb 改为 avcc，之前设置为 false 的客户，需要将配置改为 true。

例如目前设有如下配置的客户：

```java
StreamingProfile.VideoProfile vProfile =
	new StreamingProfile.VideoProfile(20, 1000 * 1024, 60, false);
```
需将参数调整为：

```java
StreamingProfile.VideoProfile vProfile =
	new StreamingProfile.VideoProfile(20, 1000 * 1024, 60, true);
```
