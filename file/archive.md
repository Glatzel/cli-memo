# 压缩
## 7z
### bzip2
```sh
```
### lz4
```sh
```
### lzma2
```sh
# 将dir1压缩为archive.7z,目标格式7z，lzma2方法，压缩级别9，单词大小64byte，字典大小32m，固实压缩，开启多线程
7z a -t7z -m0=lzma2 -mx=9 -mfb=64 -md=32m -ms=on -mmt=on archive.7z dir1
```
### zip
```sh
```
## tar
```sh
# 将文件 file1、file2 和 directory 打包到一个名为 archive.tar 的归档文件中。
tar -cvf archive.tar file1 file2 directory
# 将文件 file1、file2 和 directory 打包到一个名为 archive.tar.gz 的归档文件中。
tar -czvf archive.tar.gz file1 file2 directory
```
## zstd
```sh
# 单文件
& $zstd -T0 -7 --long=31 file  -o "archive.zst"

# 多文件
& $7z a -ttar "-w$workdir" "archive.tar" "$folder" # pack to single tar file
& $zstd -T0 -19 --long=31 "archive.tar" -o "archive.tar.zst" # pack to zst
& $pea WIPE QUICK "archive.tar" # remove temp tar file.
```
---
# 解压
## 7z
### bzip2
```sh
```
### lz4
```sh
```
### lzma2
```sh
```
### zip
```sh
```
## tar
```sh
tar -xvf archive.tar -C /somedir
```
## zstd
```sh
# 单文件
& $zstd -d "archive.zst" -o file --long=31

# 多文件
& $zstd -d "archive.tar.zst" -o "archive.tar" --long=31 # Unpack to tar file
& $7z x "-o$outdir" "archive.tar" # pack to files
& $pea "archive.tar" # remove temp tar file.
```