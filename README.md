# 说明
## README.md
template
````md
# 命令行工具名称 [命令名称]
简要描述，体现可以实现的功能，如可以操作pdf文件.
官网链接
## 安装
```sh
# windows
# mac
# linux
```
## 主要参数（可选）
```sh
-a # 描述
-b # 描述
```
````
## 完整文档模板

````md
# 功能1
## 命令名称
```sh
```
---
# 功能2
## 命令名称
```sh
```
````

---
---

# aria2 [aria2c]
aria2 是一个用于下载文件的工具。
https://aria2.github.io/

## 安装
```sh
# windows
winget install --source winget -i --id aria2.aria2
```
## 主要参数
```sh
-c # 断点续传
-d # 下载目录
-i # 从文件读取url
-j 2 # 同时下载任务数
-s 5 # 线程数量
```
---

# ffmpeg
ffmpeg 是处理音频文件的工具。
https://ffmpeg.org/
## 安装
```sh
# windows
winget install --source winget -i --id Gyan.FFmpeg # ffmpeg-full
```
# 主要参数
```sh
-i # 设定输入流 
-f # 设定输出格式
-ss #开始时间

# 视频参数
-aspect # 设定画面的比例
-r # 设定帧速率，默认为25
-s # 设定画面的宽与高
-vcodec/-c:v # 设定视频编解码器，未设定时则使用与输入流相同的编解码器
-vn # 无视频

# 音频参数
-ar # 音频采样率
-ac # 设定声音的Channel数
-acodec/-c:a # 设定声音编解码器，未设定时则使用与输入流相同的编解码器
-an # 无音频
```
---

# imagemagick [magick]
imagemagick 是可以用于图像批处理的工具。
https://imagemagick.org/
## 安装
```sh
# windows
winget install --source winget -i --id ImageMagick.ImageMagick # Q16-HDR, 仅支持16bit图像
```

---
# peazip [7z,zstd]
peazip 是用于创建和解压归档文件的命令行工具，整合了7z，gzip，zstd等工具。
http://www.peazip.org/
## 安装
```sh
# windows
winget install --source winget -i --id Giorgiotani.Peazip
```
## 添加到powshell
将以下内容写入`C:$env:HOMEPATH/Documents/PowerShell/profile.ps1`
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
https://github.com/qpdf/qpdf
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
tar 是用于创建和解压归档文件的命令行工具。
https://www.gnu.org/software/tar/
## 安装
```sh
# windows
# 系统自带
```
---
