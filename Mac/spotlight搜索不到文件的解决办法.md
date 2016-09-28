# Spotlight搜索不到文件的解决办法

<br><br>
方法就是让**Spotlight**重新加载保存metadata的plist文件。
<br><br>

关闭**Spotlight**:
```shell
sudo mdutil -a -i off
```

卸载plist:
```shell
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist
```

重新加载：
```shell
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist
```

重启**Spotlight**:
```shell
sudo mdutil -a -i on
```
