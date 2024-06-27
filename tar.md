# tar
tar 是用于创建和解压归档文件的命令行工具
## 安装
```sh
# windows
# 系统自带
```
# 压缩
```sh
# 将文件 file1、file2 和 directory 打包到一个名为 archive.tar 的归档文件中。
tar -cvf archive.tar file1 file2 directory
# 将文件 file1、file2 和 directory 打包到一个名为 archive.tar.gz 的归档文件中。
tar -czvf archive.tar.gz file1 file2 directory
```

# 解压
```sh
tar -xvf archive.tar -C /somedir
```