# 单文件
```sh
# 开启断点续传, 总连接数量=单个url连接数量=16
aria2c -c -x16 -s16 -d $download_to_dir $url --all-proxy=http://proxy:8080
```

---
# 多文件
```sh
# 开启断点续传, 总连接数量不超过64，单个url连接数量16，8个文件并行下载，使用txt文件记录下载地址
aria2c -c -x16 -s64 -j8 -d $download_to_dir -i url.txt
```

# youtube
```sh
```

# bilibili
1. 先安装油猴插件[Bilibili Evolved](https://github.com/the1812/Bilibili-Evolved).
2. 打开视频，左侧功能按钮，下载视频，选择输出方式为aria2 input，输出.txt文件
3. 使用[多文件](#多文件)中的aria2c方式下载