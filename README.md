# BydNearKey

比亚迪手表蓝牙钥匙 · 靠近解锁（HarmonyOS 手机端）。

**本仓库只用于分发安装包，不含源码，也不发布更新日志；自 v0.9.88 起保留全部历史版本，每个版本同时提供 `.zip`（App Pack）与 `.hap`（单 HAP）两种格式。** 下载请到 [Releases](../../releases)。

有问题、要激活口令，或想反馈改进建议，请加 **QQ 群 974801085**（[一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info)）。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v0.9.91（versionCode 1000091） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |
| 安装包格式 | `.app`（HarmonyOS App Pack，压缩为 zip 发布） |

## 主要功能

**1. 熄屏靠近解锁、远离上锁**
手机锁屏放口袋或包里也能用，靠系统长时任务保活。走近车头/车门自动解锁，走远自动落锁。
优先走蓝牙直连（不经云端往返，快），连不上才回落到云端指令。
划掉最近任务卡片即退出应用（系统标准行为）。v0.9.89/v0.9.90 试过的两套后台保活方案已撤回。

**2. 信号阈值可自定义**
靠近 / 远离的蓝牙信号阈值都能手调；也可以用「选择感应距离」现场校准，两处各站一会儿自动推荐。
另有解锁灵敏度（2 / 4 / 6 帧）和落锁延迟（2.5 / 4 / 6 秒）各三档，按自己的走路习惯挑。

**3. 云端控车界面**
解锁 / 锁止 / 开后备箱 / 闪灯鸣笛 / 开空调 / 关空调，点一下就下发，不看蓝牙在不在。

**4. 车况随时看**
整车状态（OK 灯、行驶状态、电源状态、车速、功率、冷却液温度）、车门车窗、
胎压（bar/kPa 双单位 + 监测结论 + 数据时间）、车内 / 车外温度、
空调（压缩机、设定温度、风量、内外循环、前后除霜、座椅加热通风、方向盘加热、
自清洁、延时关闭、冷暖箱、冰箱、PM2.5，进页面自动补拉一次快照）、
里程与能耗（总里程、纯电里程、混动里程、两种平均能耗）、
健康检测（车端自检位：发动机、制动、ABS、SRS、胎压监测、车身稳定、转向、冷却液温度、
机油压力、动力电池、充电系统…）。
**按你这台车实际支持的功能显示**——没天窗的车不会画天窗，没胎压监测的不画胎压格，
车端没下发的项整行不出现。

**5. 控车消息推送到 MeoW**
设置里填个昵称就能开，每次控车成功推一条手机通知，人不在车边也知道成没成。后期会增加「传送鸽」。

**6. 连接测试页（后台检测）**
蓝牙信号强度实时曲线、车锁认知来源与过期时间、权限与保活状态、车辆绑定情况都在这一页。
装完先把这页过一遍，能省很多排查。

**7. 不和官方 App 顶登录**
以「手表端」身份独立扫码授权，会话与官方 App 各走各的，两个可以同时登录，不会把官方 App 挤出登录。

## 下载

在 [Releases](../../releases) 里下载，一般直接用最新的 [v0.9.91](../../releases/latest)。每版两个包，按需二选一：

| 文件 | 说明 |
|---|---|
| `BydNearKey-vX.Y.Z-unsigned.zip` | HarmonyOS App Pack（`.app`）压缩包，解压得到 `BydNear-vX.Y.Z-unsigned.app`；未签名，需自己用证书重签后再装 |
| `BydNearKey-vX.Y.Z-unsigned.hap` | 单个 HAP（模块级安装包），不用解压，可直接安装；同样未签名 |

> GitHub 不允许 release 资产使用 `.app` 后缀（上传会被 422 拒掉），所以 App Pack 以 `.zip` 提供，
> 解压出来的 `BydNear-vX.Y.Z-unsigned.app` 就是原文件。

## 安装

```bash
unzip BydNearKey-v0.9.91-unsigned.zip

# 1. 确认手机已连接（hdc 在 DevEco Studio 的 toolchains 目录下）
hdc list targets

# 2a. 装 App Pack（未签名包，需先自行签名）
hdc install -r BydNear-v0.9.91-unsigned.app

# 2b. 或者直接装单独下载的 HAP（不用解压）
hdc install -r BydNearKey-v0.9.91-unsigned.hap
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

## 版本历史

自 v0.9.88 起保留全部历史版本，旧版本不再下架。每个版本都同时挂了 `.zip` 与 `.hap`。

| 版本 | 状态 | 一句话 |
|---|---|---|
| [v0.9.91](../../releases/tag/v0.9.91) | **最新** | **回退版**：撤掉 v0.9.89/0.9.90 两套后台保活改动，功能行为回到 v0.9.88 |
| [v0.9.90](../../releases/tag/v0.9.90) | 已撤回 | 从最近任务中移除（无窗口后台能力续命）——手机上仍留不住，v0.9.91 已撤掉 |
| [v0.9.89](../../releases/tag/v0.9.89) | 已撤回 | 后台卡片保护（拦截关闭请求）——手机端不回调，v0.9.91 已撤掉 |
| [v0.9.88](../../releases/tag/v0.9.88) | 归档 | 隐藏「油液与耗材」卡、健康检测移到页尾、空调卡进页面自动补拉并扩充内容 |

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
