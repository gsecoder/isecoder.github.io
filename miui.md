# MIUI系统精简优化
## 下载 adb 工具包

## 配置 adb shell 环境
> + 在环境变量里新建 Android = "abd工具包所在的目录"
> + 在 Path 中添加：;%Android%
> + 检查配置是否成功：打开 cmd， 输入 abd 不报错说明配置成功

## 配置小米手机
> + 在系统中点击 MIUI 版本 5 次激活 "开发者模式"
> + 在  "开发者模式" 模式打开 "USB调试"
> + 手机链接电脑

## 高阶adb shell命令
```bash
不使用参数：adb shell pm list packages，查看当前连接设备或者虚拟机的所有包
使用-f参数：adb shell pm list packages -f, 输出包和包相关联的文件
使用-d参数：adb shell pm list packages -d, 只输出禁用的包。由于本机禁用没有，输出为空。
使用-e参数：adb shell pm list packages -e, 只输出启用的包。
使用-s参数：adb shell pm list packages -s, 只输出系统的包。
使用-3参数：adb shell pm list packages -3, 只输出第三方的包。
使用-i参数：adb shell pm list packages -i, 只输出包和安装信息（安装来源）。
使用-u参数：adb shell pm list packages -u, 只输出包和未安装包信息（安装来源）。
使用--user参数：adb shell pm list packages --user <USER_ID>， 根据用户id查询用户的空间的所有包，USER_ID代表当前连接设备的顺序，从零开始：
使用-e参数且设置过滤条件：adb shell pm list packages -e "ximalaya", 只输出启用的包。
```

## 卸载配置
> + adb devices，查看设备的链接状态
> + 查看系统安装的应用：adb shell pm list packages
> + 查找要卸载的系统应用：
```bash
adb shell pm uninstall --user 0 com.miui.systemAdSolution（小米系统广告解决方案，必删）
adb shell pm uninstall --user 0 com.miui.analytics（小米广告分析，必删）
adb shell pm uninstall --user 0 com.xiaomi.gamecenter.sdk.service  （小米游戏中心服务）
adb shell pm uninstall --user 0 com.xiaomi.gamecenter  （小米游戏中心）
adb shell pm uninstall --user 0 com.sohu.inputmethod.sogou.xiaomi  （搜狗输入法）
adb shell pm uninstall --user 0 com.miui.player  （小米音乐）
adb shell pm uninstall --user 0 com.miui.video  （小米视频）
adb shell pm uninstall --user 0 com.miui.notes  （小米便签）
adb shell pm uninstall --user 0 com.miui.translation.youdao  （有道翻译）
adb shell pm uninstall --user 0 com.miui.translation.kingsoft  （金山翻译）
adb shell pm uninstall --user 0 com.android.email  （邮件）
adb shell pm uninstall --user 0 com.xiaomi.scanner  （小米扫描）
adb shell pm uninstall --user 0 com.miui.hybrid  （混合器）
adb shell pm uninstall --user 0 com.miui.bugreport  （bug 反馈）
adb shell pm uninstall --user 0 com.milink.service  （米连服务）
adb shell pm uninstall --user 0 com.android.browser  （浏览器）
adb shell pm uninstall --user 0 com.miui.gallery  （相册）
adb shell pm uninstall --user 0 com.miui.yellowpage  （黄页）
adb shell pm uninstall --user 0 com.xiaomi.midrop  （小米快传）
adb shell pm uninstall --user 0 com.miui.virtualsim  （小米虚拟器）
adb shell pm uninstall --user 0 com.xiaomi.payment  （小米支付）
adb shell pm uninstall --user 0 com.mipay.wallet  （小米钱包）
adb shell pm uninstall --user 0 com.android.soundrecorder  （录音机）
adb shell pm uninstall --user 0 com.miui.screenrecorder  （屏幕录制）
adb shell pm uninstall --user 0 com.android.wallpaper  （壁纸）
adb shell pm uninstall --user 0 com.miui.voiceassist  （语音助手）
adb shell pm uninstall --user 0 com.miui.fm  （收音机）
adb shell pm uninstall --user 0 com.miui.touchassistant  （悬浮球）
adb shell pm uninstall --user 0 com.android.cellbroadcastreceiver  （小米广播）
adb shell pm uninstall --user 0 com.xiaomi.mitunes  （小米助手）
adb shell pm uninstall --user 0 com.xiaomi.pass  （小米卡包）
adb shell pm uninstall --user 0 com.android.thememanager  （个性主题管理）
adb shell pm uninstall --user 0 com.android.wallpaper  （动态壁纸）
adb shell pm uninstall --user 0 com.android.wallpaper.livepicker  （动态壁纸获取）
adb shell pm uninstall --user 0 com.miui.klo.bugreport  （KLO bug 反馈）
```

## 以下应用不能删除，会导致系统崩溃
```bash
com.miui.cloudservice  （小米云服务）
com.xiaomi.account  （小米账户）
com.miui.cloudbackup  （云备份）
com.xiaomi.market  （应用市场）
```
## 禁用系统应用
```bash
adb shell pm disable --user com.miui.touchassistant
adb shell pm disable-user com.mipay.wallet
adb shell pm disable -user com.miui.voiceassist
adb shell pm disable-user com.xiaomi.simactivate.service
adb shell pm disable-user com.xiaomi.payment
adb shell pm disable-user com.miui.systemAdSolution
adb shell pm disable-user com.miui.bugreport
adb shell pm disable-user com.miui.contentextension
adb shell pm disable-user com.android.printspooler
adb shell pm disable-user com.miui.hybrid
adb shell pm disable-user com.miui.hybrid.accessory
adb shell pm disable-user com.android.quicksearchbox
adb shell pm disable-user com.android.bips
adb shell pm disable-user com.milink.service
adb shell pm disable-user com.miui.mishare.connectivit
```
