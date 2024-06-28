# 单文件
```sh
# 开启断点续传, 总连接数量=单个url连接数量=16
aria2c -c -x16 -s16 -d $download_to_dir $url 
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