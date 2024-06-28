# 单文件
```sh
aria2c -c -x5 -d $download_to_dir $url
```

---
# 多文件
```sh
aria2c.exe -c -x5 -j2 -d $download_to_dir -i url.txt
```