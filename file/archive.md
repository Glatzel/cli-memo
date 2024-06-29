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
& $7z a -ttar "-w$workdir" -bb0 -bse0 -bsp2 "archive.tar" "$folder" # pack to single tar file
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
& $7z x -aos -bb0 -bse0 -bsp2 "-o$outdir" -sccUTF-8 -snz "archive.tar" # pack to files
& $pea "archive.tar" # remove temp tar file.
```