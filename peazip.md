# peazip
peazip 是用于创建和解压归档文件的命令行工具，整合了7z，gzip，zstd等工具。
http://www.peazip.org/
## 安装
```sh
# windows
winget install --source winget -i --id Giorgiotani.Peazip
```
## 添加到powshell
将以下内容写入我的文档`C:$env:HOMEPATH/Documents/PowerShell/profile.ps1`
```sh
function 7z { 
    try { & "$env:ProgramFiles/PeaZip/res/bin/7z/7z.exe" $args }
    catch { Write-Error "Peazip is not installed." } 
}
function zstd {
    try { & "$env:ProgramFiles/PeaZip/res/bin/zstd/zstd.exe" $args }
    catch { Write-Error "Peazip is not installed." } 
}
```
---
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
