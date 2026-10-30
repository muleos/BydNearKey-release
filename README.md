# BydNearKey

比亚迪手表蓝牙钥匙 · 靠近解锁（HarmonyOS 手机端）。

**本仓库只用于分发安装包，不含源码，也不发布更新日志；只保留最新版本的安装包，旧版本会下架。** 下载请到 [Releases](../../releases/latest)。

有问题、要激活口令，或想反馈改进建议，请加 **QQ 群 974801085**（[一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info)）。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.82（versionCode 1000082） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |
| 安装包格式 | `.app`（HarmonyOS App Pack，压缩为 zip 发布） |

## 下载

在 [Releases](../../releases/latest) 里下载（每个版本只有一个包，旧版本不保留）：

| 文件 | 说明 |
|---|---|
| `BydNearKey-vX.Y.Z-unsigned.zip` | 未签名，解压得到 `BydNear-vX.Y.Z-unsigned.app`，需自己用证书重签后再装 |

## 安装

```bash
unzip BydNearKey-v0.9.82-unsigned.zip

# 1. 确认手机已连接（hdc 在 DevEco Studio 的 toolchains 目录下）
hdc list targets

# 2. 安装（未签名包，需先自行签名）
hdc install -r BydNear-v0.9.82-unsigned.app
```

也可以直接用 DevEco Studio 的 Device Manager 选择该 `.app` 安装。

若设备上已装同 versionCode 的版本，覆盖安装可能提示版本冲突，先卸载再装即可。

> 未签名包装到真机需要设备已开启开发者模式；若要长期使用，请用你自己的证书重新签名。

## 首次使用

1. **首次打开会停在激活页，需要输入 6 位激活口令**（口令每天 0 点更新，可在 QQ 群 974801085 里获取当天口令）
2. 激活后进扫码登录页，用手机上的**比亚迪 App** 扫描表盘二维码 → 手机上点确认
3. 登录成功后自动写入车辆信息与蓝牙钥匙，回到首页
4. 之后靠近车辆即可解锁，离开自动上锁（可在设置里关掉）

车况页可以看电量、车门车窗状态，也能远程控车；首页「后台检测」可以查看
蓝牙信号强度、手选感应距离阈值。

## 反馈与交流

遇到问题、想要当天激活口令，或有改进建议，欢迎加入 QQ 群交流：

| | |
|---|---|
| QQ 群号 | **974801085** |
| 加群 | [点这里一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info) |
| 手动加群 | 打开 QQ → 右上角「+」→「加好友/群」→「找群」→ 搜索群号 `974801085` |

加群链接偶尔会失效（带时效 token），失效时直接用群号搜索即可。反馈问题时附上
手机型号、系统版本和「后台检测」页的截图，能快很多。

## 免责声明

本项目为个人开发者制作的非官方工具，与比亚迪（BYD）官方无关，仅供个人学习与
自用。使用本工具产生的任何后果（包括但不限于车辆状态异常、账号风险）由使用者
自行承担。请勿用于商业用途或二次分发。
