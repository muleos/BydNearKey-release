# BydNearKey

比亚迪手表蓝牙钥匙 · 靠近解锁（HarmonyOS 手表端）。

**本仓库只用于分发安装包，不含源码，也不发布更新日志。** 下载请到 [Releases](../../releases/latest)。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.76（versionCode 1000076） |
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
hdc install -r BydNear-v0.9.76-unsigned.app
```

也可以直接用 DevEco Studio 的 Device Manager 选择该 `.app` 安装。

> 发布包为**未签名**产物。装到真机需要设备已开启开发者模式；若要长期使用，
> 请用你自己的证书对它重新签名。

## 首次使用

1. **首次打开会停在激活页，需要输入 6 位激活口令**（口令每天 0 点更新，向作者获取当天口令）
2. 激活后进扫码登录页，用手机上的**比亚迪 App** 扫描表盘二维码 → 手机上点确认
3. 登录成功后自动写入车辆信息与蓝牙钥匙，回到首页
4. 之后靠近车辆即可解锁，离开自动上锁（可在设置里关掉）

车况页可以看电量、车门车窗状态，也能远程控车；首页「后台检测」可以查看
蓝牙信号强度、手选感应距离阈值。

## 免责声明

本项目为个人开发者制作的非官方工具，与比亚迪（BYD）官方无关，仅供个人学习与
自用。使用本工具产生的任何后果（包括但不限于车辆状态异常、账号风险）由使用者
自行承担。请勿用于商业用途或二次分发。
