# aria2
aria2 是一个用于下载文件的工具。
https://aria2.github.io/

## 安装
```sh
# windows
winget install --source winget -i --id aria2.aria2
```
---

# ffmpeg
ffmpeg 是处理音频文件的工具。
## 安装
```sh
# windows
winget install --source winget -i --id Gyan.FFmpeg # ffmpeg-full
```
---

# imagemagick
imagemagick 是可以用于图像批处理的工具。
## 安装
```sh
# windows
winget install --source winget -i --id ImageMagick.ImageMagick # Q16-HDR, 仅支持16bit图像
```
---

# peazip
peazip 是用于创建和解压归档文件的命令行工具，整合了7z，gzip，zstd等工具。
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
# qpdf
qpdf 可以完成对pdf的常用操作，如：合并，拆分，加密等.
## 添加到powshell
将以下内容写入我的文档`C:$env:HOMEPATH/Documents/PowerShell/profile.ps1`
```sh
function qpdf {
    try {& "$env:ProgramFiles/qpdf/bin/qpdf.exe" $args}
    catch {Write-Error "Peazip is not installed."}
}
```
---

# tar
tar 是用于创建和解压归档文件的命令行工具
## 安装
```sh
# windows
# 系统自带
```