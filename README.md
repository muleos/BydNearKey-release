# BydNearKey

比亚迪手表蓝牙数字钥匙 · 靠近解锁（HarmonyOS 手机端）。

**本仓库只分发安装包，不含源码。** 下载与历史版本见 [Releases](../../releases)。

有问题、要当天激活口令，或想反馈建议，请加 **QQ 群 974801085**（[一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info)；链接失效用群号搜索）。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.95（versionCode 1000095） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |

## 主要功能

1. **熄屏靠近解锁、远离上锁** —— 走近自动解锁，走远自动落锁，优先蓝牙直连，连不上回落云端。
2. **阈值与灵敏度可调** —— 阈值手调或现场校准；解锁灵敏度 2/4/6 帧，落锁延迟 2.5/4/6 秒。
3. **云端控车** —— 解锁、锁止、开后备箱、闪灯鸣笛、开/关空调。
4. **车况查看** —— 整车状态、门窗、胎压、温度、空调、里程能耗、健康自检，按本车实际支持项显示。
5. **控车通知** —— 接入 MeoW，填昵称即开。
6. **后台检测页** —— 信号曲线、车锁认知、权限与保活状态。
7. **不与官方 App 顶登录** —— 以「手表端」身份独立授权，可同时登录。

## 下载

| 文件 | 说明 |
|---|---|
| `BydNearKey-vX.Y.Z-unsigned.zip` | App Pack 压缩包，解压得 `.app`；未签名 |
| `BydNearKey-vX.Y.Z-unsigned.hap` | 单 HAP，不用解压；未签名 |

一般直接用最新的 [v0.9.95](../../releases/latest)。GitHub 不接受 `.app` 后缀，故 App Pack 以 `.zip` 提供。

## 安装

```bash
unzip BydNearKey-v0.9.95-unsigned.zip
hdc list targets
hdc install -r BydNear-v0.9.95-unsigned.app    # 未签名包，需先自行签名
hdc install -r BydNearKey-v0.9.95-unsigned.hap # 或直接装单 HAP
```

> 未签名包装到真机需设备已开启开发者模式；长期使用请用自己的证书重新签名。
> versionCode `1000095` 可直接覆盖 0.9.92~0.9.94（含测试包），无需先卸载。

## 首次使用

1. 首次打开需输入 6 位激活口令（每天 0 点更新，群里取当天口令）
2. 用手机上的**比亚迪 App** 扫表盘二维码 → 手机点确认
3. 之后靠近车辆自动解锁、离开自动上锁（设置里可关）

## 版本历史

| 版本 | 说明 |
|---|---|
| [v0.9.95](../../releases/tag/v0.9.95) | **最新**，功能与 v0.9.92 相同，仅提升 versionCode |
| [v0.9.88](../../releases/tag/v0.9.88) | 早期稳定版 |

v0.9.89 ~ v0.9.92 属于后台保活试验与回退过程版本，已不再提供下载。

## 声明

个人开发者制作的**非官方**工具，与比亚迪（BYD）官方无关，仅供个人学习与自用。
使用本工具产生的任何后果由使用者自行承担，请勿用于商业用途或二次分发。
