# BydNearKey

比亚迪手表蓝牙钥匙 · 靠近解锁（HarmonyOS 手表端）。

**本仓库只用于分发安装包，不含源码。** 下载请到 [Releases](../../releases/latest)。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.75（versionCode 1000075） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |
| 安装包格式 | `.app`（HarmonyOS App Pack，压缩为 zip 发布） |

## 下载

在 [Releases](../../releases/latest) 里下载 `BydNearKey-vX.Y.Z-unsigned.zip`，解压得到
`BydNear-vX.Y.Z-unsigned.app`。

## 安装

```bash
# 1. 确认手表已连接（hdc 在 DevEco Studio 的 toolchains 目录下）
hdc list targets

# 2. 安装
hdc install -r BydNear-v0.9.75-unsigned.app
```

也可以直接用 DevEco Studio 的 Device Manager 选择该 `.app` 安装。

> 发布包为**未签名**产物。装到真机需要设备已开启开发者模式；若要长期使用，
> 请用你自己的证书对它重新签名。

## 首次使用

1. 打开应用 → 扫码登录页
2. 用手机上的**比亚迪 App** 扫描表盘二维码 → 手机上点确认
3. 登录成功后自动写入车辆信息与蓝牙钥匙，回到首页
4. 之后靠近车辆即可解锁，离开自动上锁（可在设置里关掉）

车况页可以看电量、车门车窗状态，也能远程控车；首页「后台检测」可以查看
蓝牙信号强度、手选感应距离阈值。

## 更新日志

- **v0.9.75** — 扫码页精简：去掉 uuid / 引擎自检等调试信息，只留二维码和提示；
  二维码正下方显示刷新倒计时（150 秒，最后 15 秒变色）；二维码整体居中；
  左上角返回图标与设置页统一。
- **v0.9.74** — 发包前稳定性专项：蓝牙四个 native 回调、定时判定链、UI 异步方法
  全部加异常兜底，修掉一批「什么都没操作应用突然没了」的闪退路径。
- 更早版本见 [Releases](../../releases)。

## 免责声明

本项目为个人开发者制作的非官方工具，与比亚迪（BYD）官方无关，仅供个人学习与
自用。使用本工具产生的任何后果（包括但不限于车辆状态异常、账号风险）由使用者
自行承担。请勿用于商业用途或二次分发。
