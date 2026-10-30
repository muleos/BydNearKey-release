# BydNearKey

比亚迪手表蓝牙钥匙 · 靠近解锁（HarmonyOS 手机端）。

**本仓库只用于分发安装包，不含源码，也不发布更新日志；只保留最新版本的安装包，旧版本会下架。** 下载请到 [Releases](../../releases/latest)。

有问题、要激活口令，或想反馈改进建议，请加 **QQ 群 974801085**（[一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info)）。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.86（versionCode 1000086） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |
| 安装包格式 | `.app`（HarmonyOS App Pack，压缩为 zip 发布） |

## 主要功能

**1. 熄屏靠近解锁、远离上锁**
手机锁屏放口袋或包里也能用，靠系统长时任务保活。走近车头/车门自动解锁，走远自动落锁。
优先走蓝牙直连（不经云端往返，快），连不上才回落到云端指令。

**2. 信号阈值可自定义**
靠近 / 远离的蓝牙信号阈值都能手调；也可以用「选择感应距离」现场校准，两处各站一会儿自动推荐。
另有解锁灵敏度（2 / 4 / 6 帧）和落锁延迟（2.5 / 4 / 6 秒）各三档，按自己的走路习惯挑。

**3. 云端控车界面**
解锁 / 锁止 / 开后备箱 / 闪灯鸣笛 / 开空调 / 关空调，点一下就下发，不看蓝牙在不在。

**4. 车况随时看**
健康检测（车端自检位：发动机、制动、ABS、SRS、胎压监测、车身稳定、转向、冷却液温度、
机油压力、动力电池、充电系统…）、车门车窗、胎压（bar/kPa 双单位 + 监测结论 + 数据时间）、
车内 / 车外温度、空调、里程与能耗（总里程、纯电里程、混动里程、两种平均能耗）、
整车状态（OK 灯、行驶状态、电源状态、车速、功率、冷却液温度、哨兵模式）。
**按你这台车实际支持的功能显示**——没天窗的车不会画天窗，没胎压监测的不画胎压格，
没有哨兵模式的不会多出那一行。

**5. 控车消息推送到 MeoW**
设置里填个昵称就能开，每次控车成功推一条手机通知，人不在车边也知道成没成。后期会增加「传送鸽」。

**6. 连接测试页（后台检测）**
蓝牙信号强度实时曲线、车锁认知来源与过期时间、权限与保活状态、车辆绑定情况都在这一页。
装完先把这页过一遍，能省很多排查。

**7. 不和官方 App 顶登录**
以「手表端」身份独立扫码授权，会话与官方 App 各走各的，两个可以同时登录，不会把官方 App 挤出登录。

## 下载

在 [Releases](../../releases/latest) 里下载（每个版本只有一个包，旧版本不保留）：

| 文件 | 说明 |
|---|---|
| `BydNearKey-vX.Y.Z-unsigned.zip` | 未签名，解压得到 `BydNear-vX.Y.Z-unsigned.app`，需自己用证书重签后再装 |

## 安装

```bash
unzip BydNearKey-v0.9.86-unsigned.zip

# 1. 确认手机已连接（hdc 在 DevEco Studio 的 toolchains 目录下）
hdc list targets

# 2. 安装（未签名包，需先自行签名）
hdc install -r BydNear-v0.9.86-unsigned.app
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
