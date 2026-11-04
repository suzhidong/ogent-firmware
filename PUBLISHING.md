# 发布正式固件 / Publishing stable firmware

这个仓库只放公开下载说明及明确标注用途的固件附件。正式版必须完成验收；备用板测试包只能作为明确标注范围的 Pre-release，不能设为 Latest。不要复制私有源码仓库、Mac 构建目录、故障镜像、真实录音、声纹、配对数据或签名私钥。

## 每次发布

1. 在私有开发环境构建正式固件并验证签名，完成对应硬件的 OTA、断连/断电恢复、重连、录音恢复和资料保留检查。测试版、故障版和未验收的正式构建都不能发布到 stable。
2. 将该版本的签名升级包复制并命名为 `recorder.ogentfw`；保留包内容和嵌入的许可声明，同时准备对应的 `LICENSES.txt`。不要把首次 USB 准备包当作蓝牙升级包。
3. 打开本仓库的 **Releases → Draft a new release**，创建版本标签，例如 `v0.3.28`。标签必须与升级包内的 `recorder-0.3.28` 版本一致。填写面向用户的更新说明，上传上述两个附件。
4. 核对上传完整、附件名称、SHA-256、许可和实际下载。GitHub 需要为 `recorder.ogentfw` 提供 `sha256:` 开头的附件摘要；上传未完成或摘要缺失时不要发布。
5. 验收和附件核对完成后发布为正式版本，设置为 **Latest**。测试版本应保持 Draft 或 Pre-release，不能作为正式更新提供。
6. 发布后，在未登录 GitHub 的情况下核对固定最新版地址及对应版本下载地址。在 Ogent 点“检查更新”，核对显示的版本、更新说明，再完成实际升级检查。

## 用户无需处理链接

App 已使用固定的 latest-release 检查地址，不需要每次修改 App、手工编辑更新目录或让用户粘贴链接。GitHub 根据最新正式 Release 返回版本和附件信息。App 核对标签、附件摘要、大小、所属仓库及签名包版本后，使用这个版本的固定附件地址下载，避免发布新版本时取错文件。

- 固定检查地址：`https://api.github.com/repos/suzhidong/ogent-firmware/releases/latest`
- 固定最新版文件地址：`https://github.com/suzhidong/ogent-firmware/releases/latest/download/recorder.ogentfw`
- 每版附件地址示例：`https://github.com/suzhidong/ogent-firmware/releases/download/v0.3.28/recorder.ogentfw`

首次正式发布前，latest 地址的 404 是“尚无正式固件”，不代表应上传一个测试包填补。目前正式 Latest 为 [0.3.28](https://github.com/suzhidong/ogent-firmware/releases/tag/v0.3.28)。发布后不要覆盖已经发布的版本附件；需要修正时发布更高版本，保留旧版本供核对。

## 测试预发布

备用板预发布使用带测试后缀的标签，例如 `v0.3.26-test.1`，说明包内版本仍为 `recorder-0.3.26`、测试硬件、已验证范围和未完成项目。仅上传非故障升级包、许可及校验清单，发布时启用 **Pre-release** 并明确禁用 **Latest**。正式 App 更新入口会忽略此类版本；不能把去掉后缀或取消 Pre-release 当作正式验收。

当前预发布：[0.3.26 备用板测试版](https://github.com/suzhidong/ogent-firmware/releases/tag/v0.3.26-test.1)。其可下载不代表日常设备已经准备好 OTA，也不代表手机端已完成验收。

GitHub 官方说明：[创建发布](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)、[固定下载链接](https://docs.github.com/en/repositories/releasing-projects-on-github/linking-to-releases)。
