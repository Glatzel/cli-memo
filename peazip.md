# 7z

# zstd
## 压缩
```sh
# 单文件
zstd -T0 -7 --long=31 file  -o "archive.zst"

# 多文件
7z a -ttar "-w$workdir" -bb0 -bse0 -bsp2 "archive.tar" "$folder" 
zstd -T0 -19 --long=31 "archive.tar" -o "archive.tar.zst"
Remove-Item "archive.tar"
```
# 解压
```sh
# 单文件
zstd -d "archive.zst" -o file --long=31

# 多文件
zstd -d "archive.tar.zst" -o "archive.tar" --long=31
7z x -aos -bb0 -bse0 -bsp2 "-o$outdir" -sccUTF-8 -snz "archive.tar"
Remove-Item "archive.tar"
```
