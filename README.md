# openwrt-hiwifi-c526a
官方openwrt极路由X补丁

## 项目说明


补丁基本上就是 https://github.com/coolsnowwolf/lede/pull/6760 这个PR移到官方openwrt了。

这个项目会通过github actions自动克隆官方openwrt并打上补丁，然后按项目带的.config编译。

有需要可以fork后，自行修改.config，再手动去actions编译。

## 参考
* https://github.com/coolsnowwolf/lede
* https://github.com/Hyy2001X/AutoBuild-Actions
* https://github.com/supsupsuperstar/Actions-OpenWrt-C526a


## 注意事项
* 我的配置除了SQM和mesh相关，默认没有任何插件
* 不要用ath10k-ct版的驱动，尤其如果你要用mesh的话。ath10k-ct的项目区有好几个qca4019网速相关的issue至今没有解决。但OpenWRT默认是用ct版，即便在menuconfig里选的qca版，也还是会有漏掉的ct选项，导致用上ct版的firmware-5.bin。因此，一定要手动去.config里检查ath10k相关的项目，确保带ct的都注释掉再编译。
