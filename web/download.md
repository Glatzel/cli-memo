# 单文件
```sh
aria2c -c -s 5 -d $download_to_dir $url
```

---
# 多文件
```sh
aria2c.exe -c -s 5 -j 2 -d $download_to_dir -i url.txt
```