# aria2
aria2 是一个用于下载文件的工具。
https://aria2.github.io/

## 安装
```sh
# windows
winget install --source winget -i --id aria2.aria2
```
---
# 下载
```sh
# 单文件
aria2c -c -s 5 -d $download_to_dir $url

# 多文件
aria2c.exe -c -s 5 -j 2 -d $download_to_dir -i url.txt

-c # 断点续传
-d # 下载目录
-i # 从文件读取url
-j 2 # 同时下载任务数
-s 5 # 线程数量
```